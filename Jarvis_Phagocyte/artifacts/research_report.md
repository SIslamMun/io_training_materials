# Jarvis-CD: A Unified Platform for High-Performance Computing Deployment and Orchestration

## Key Points
*   **Unified Deployment Platform:** Jarvis-CD is a specialized tool designed to automate the deployment of complex High-Performance Computing (HPC) applications, specifically targeting storage systems and benchmarks.
*   **Three-Tier Package Architecture:** The system categorizes software into **Services** (long-running daemons), **Applications** (finite tasks), and **Interceptors** (environment modifiers for I/O routing), allowing for flexible pipeline construction.
*   **Complex Configuration Management:** It addresses the "configuration space" problem in HPC by abstracting hardware details through a **Resource Graph** and managing state via a three-directory system (`CONFIG_DIR`, `PRIVATE_DIR`, `SHARED_DIR`).
*   **AI-Driven Orchestration:** As a core component of the **IOWarp** ecosystem, Jarvis-CD integrates with AI agents via the Model Context Protocol (MCP), enabling Large Language Models (LLMs) to autonomously deploy and optimize benchmarks like IOR with significant time savings compared to manual methods.
*   **Grid Search Testing:** The platform includes native support for pipeline testing, allowing researchers to define parameter sweeps (grid searches) using `loop` and `vars` syntax to rigorously evaluate system performance across different configurations.

---

## 1. Introduction

High-Performance Computing (HPC) environments are characterized by their complexity and heterogeneity. Deploying storage systems, benchmarks, and scientific applications across distributed nodes requires managing intricate configuration spaces, dependencies, and hardware specificities. **Jarvis-CD** (Continuous Delivery/Deployment) emerges as a unified platform designed to mitigate these challenges. Developed as part of the **IOWarp** project at the Illinois Institute of Technology's Gnosis Research Center, Jarvis-CD provides a structured framework for wrapping applications into standardized "packages" and orchestrating them into "deployment pipelines" [1].

The platform is particularly focused on the needs of storage researchers and system administrators who must frequently deploy, benchmark, and tear down complex storage hierarchies (e.g., OrangeFS, Hermes). By abstracting the deployment logic into reusable Python classes and providing a robust utility library (`jarvis-util`), Jarvis-CD enables reproducible and portable workflows. Furthermore, recent advancements have integrated Jarvis-CD into AI-driven scientific workflows, where AI agents utilize Jarvis as a tool to autonomously provision resources and execute benchmarks, demonstrating a paradigm shift in how scientific infrastructure is managed [2, 3].

This report details the architecture, configuration mechanisms, deployment strategies, and use cases of Jarvis-CD, drawing primarily from official documentation, GitHub repositories, and associated research publications.

---

## 2. System Architecture

The architecture of Jarvis-CD is designed to separate the definition of an application's behavior from the specifics of the infrastructure it runs on. It is built upon a layered approach, with the core logic residing in the `jarvis-cd` framework, supported by the low-level utilities of `jarvis-util`.

### 2.1. The `jarvis-util` Foundation
At the base of the architecture lies **`jarvis-util`**, a Python library that provides the essential primitives for system interaction. It serves as the execution engine for Jarvis-CD, handling the complexities of running commands across different environments (local, SSH, MPI) [4, 5].

*   **Shell Execution Wrappers:** `jarvis-util` contains wrappers for executing shell commands. It abstracts the differences between local execution and remote execution, allowing developers to write deployment logic that is agnostic to the underlying transport mechanism.
*   **MPI and PSSH Support:** The library includes specific support for Message Passing Interface (MPI) and Parallel SSH (PSSH), which are critical for multi-node HPC deployments. It provides data structures like `Exec` and `PsshExecInfo` to manage these executions programmatically within Python [6].
*   **Output Collection:** It includes functionality to capture standard output (stdout) and standard error (stderr) from executed binaries, which is essential for monitoring the status of deployments and collecting benchmark results [5].

### 2.2. Package Architecture
Jarvis-CD treats every piece of software it manages as a **Package** (`pkg`). These packages are Python classes that inherit from a common `Pkg` base class. The architecture distinguishes between three fundamental types of packages, each serving a distinct role in a deployment pipeline [6].

#### 2.2.1. Services
**Services** represent long-running processes that typically operate as daemons. Examples include file system servers (like OrangeFS servers) or database instances.
*   **Lifecycle:** Services are designed to run indefinitely until explicitly stopped.
*   **Management:** Jarvis-CD manages the lifecycle of services, ensuring they are started before dependent applications and stopped cleanly after benchmarks complete.
*   **Interface:** Services implement `start` and `stop` methods. The `stop` method is crucial for resource cleanup in shared HPC environments [6].

#### 2.2.2. Applications (Apps)
**Applications** represent finite tasks that execute and then terminate upon completion. These are typically the scientific workloads or benchmarks being run.
*   **Lifecycle:** An application runs until it finishes its task.
*   **Automation:** Unlike services, applications do not typically require a manual stop command, as they exit naturally.
*   **Interface:** They share the same interface as services but are semantically distinct in how the pipeline manager handles their termination [6].

#### 2.2.3. Interceptors
**Interceptors** are a specialized package type unique to systems research and I/O profiling. They are designed to modify the environment of downstream applications to inject logic, typically via `LD_PRELOAD` or similar mechanisms.
*   **Function:** They route system and library calls (e.g., POSIX `write` or `read`) to custom functions, enabling features like transparent buffering or I/O tracing.
*   **Interface:** Interceptors implement a `modify_env` method. Unlike apps and services, they do not "run" in the traditional sense; instead, they alter the environment variables (specifically `LD_PRELOAD`) for the applications that follow them in the pipeline [6].
*   **Examples:** The Hermes MPI-IO interceptor is a prime example, which intercepts MPI-IO calls to redirect data to a hierarchical storage buffer [6].

### 2.3. The `Pkg` Base Class
All packages inherit from the `Pkg` class, which standardizes their interaction with the Jarvis runtime. This base class initializes critical variables and defines the methods that developers must implement [6].

**Key Attributes:**
*   **`pkg_dir`:** The directory containing the package's Python class file. This is often used to store template configuration files (e.g., XML configs for OrangeFS) that are too complex to generate purely in code.
*   **`config`:** A dictionary storing configuration parameters specific to the package (e.g., port numbers, file paths). These are persisted in a YAML file (`{pkg_id}.yaml`).
*   **`env` & `mod_env`:** Dictionaries representing the environment variables. `env` is the base environment, while `mod_env` includes modifications (like `LD_PRELOAD`) introduced by interceptors.
*   **`global_id` & `pkg_id`:** Unique identifiers for the package instance within the broader Jarvis ecosystem and the specific pipeline, respectively.

**Key Methods:**
*   **`_init`:** Initializes global variables.
*   **`_configure_menu`:** Defines command-line arguments and options available to the user for this package.
*   **`configure`:** The core setup method. It updates `self.config` and generates necessary configuration files (e.g., writing a `server.conf` file to the shared directory).
*   **`start` / `stop`:** Methods to launch and terminate the binary.
*   **`clean`:** Removes intermediate data and logs produced during execution.

---

## 3. Configuration Spaces

One of the primary motivations for Jarvis-CD is the management of "complex configuration spaces" [1]. HPC applications often require precise coordination of file paths, network addresses, and environment variables across multiple nodes. Jarvis-CD addresses this through a structured directory model and hardware introspection.

### 3.1. The Three-Directory Model
To manage state across distributed systems, Jarvis-CD enforces a strict separation of data based on its visibility and persistence requirements. When initializing a Jarvis configuration (`jarvis init`), the user defines three critical directories [5, 7]:

1.  **`CONFIG_DIR`:**
    *   **Purpose:** Stores metadata for packages and pipelines.
    *   **Scope:** Accessible by the current user (e.g., `~/.jarvis`).
    *   **Content:** Contains the YAML configuration files that define how packages are set up and how pipelines are constructed.

2.  **`SHARED_DIR`:**
    *   **Purpose:** Stores data that must be visible and identical across all nodes in the cluster.
    *   **Scope:** Must be on a shared file system (e.g., NFS, Lustre).
    *   **Use Case:** Storing hostfiles, shared configuration files, and aggregated logs.

3.  **`PRIVATE_DIR`:**
    *   **Purpose:** Stores data that is local to each specific machine.
    *   **Scope:** Local storage (e.g., `/tmp` or local NVMe).
    *   **Use Case:** Some distributed file systems (like OrangeFS) require local state directories on each server that are *not* shared with others. This directory ensures that node-specific data remains isolated.

### 3.2. The Resource Graph
To automate configuration, Jarvis-CD needs to understand the underlying hardware. It employs a **Resource Graph**, which is a snapshot of the system's network and storage topology [5].
*   **Introspection:** The command `jarvis rg build` scans the nodes listed in the hostfile to discover available resources.
*   **Network & Storage:** It identifies valid network interfaces (IPs, fabrics) and storage devices (mount points, capacities).
*   **Dependency:** Packages rely on this graph to auto-configure. For example, the Hermes I/O buffering system uses the Resource Graph to automatically select the fastest available storage tiers (RAM, NVMe, SSD) and valid network transports for buffering, removing the need for the user to manually specify these paths [5].

### 3.3. Environment Management
Jarvis-CD maintains a strict environment context for each pipeline.
*   **`env` Dictionary:** A Python dictionary representing the environment variables (key-value pairs). This is stored as a YAML file to ensure persistence across pipeline runs [6].
*   **Pipeline Isolation:** Each pipeline maintains its own environment dictionary to prevent conflicts between different deployments.
*   **Dynamic Modification:** Interceptors modify this environment dynamically. The `mod_env` dictionary captures these changes (e.g., prepending a library to `LD_PRELOAD`) without permanently altering the base configuration, allowing for clean rollbacks and modular composition of features [6].

---

## 4. Deployment Mechanisms

Jarvis-CD orchestrates deployment through the concept of **Pipelines**. A pipeline is a directed graph of packages connected together to form a complete workflow.

### 4.1. Pipeline Construction
A pipeline is constructed by appending packages in a specific sequence. The order matters, particularly for interceptors and services.
*   **Creation:** `jarvis ppl create [name]` initializes a new pipeline.
*   **Appending:** `jarvis ppl append [pkg]` adds a package to the pipeline.
*   **Example Workflow:** A typical I/O benchmarking pipeline might consist of:
    1.  **Service:** `hermes` (starts the buffering daemon).
    2.  **Interceptor:** `hermes_mpiio` (intercepts MPI-IO calls).
    3.  **Application:** `gray_scott` (a simulation that performs I/O) [6].

### 4.2. Hostfile Management
Deployment across multiple nodes is managed via hostfiles, structured similarly to MPI hostfiles.
*   **Definition:** A text file listing the hostnames or IP addresses of the nodes.
*   **Active Hostfile:** The user sets an active hostfile using `jarvis hostfile set [path]`.
*   **Updates:** Jarvis does not automatically detect changes to the hostfile content. If the hostfile changes, the pipeline must be updated explicitly using `jarvis ppl update` to propagate the new node list to all packages [5].

### 4.3. Execution and Testing
Jarvis-CD provides robust tools for running and testing pipelines.

#### 4.3.1. Execution
Pipelines are executed using commands like `jarvis ppl run`, `start`, `stop`, or `clean`. The `jarvis-util` library handles the actual process spawning, utilizing MPI or PSSH as configured by the package [6].

#### 4.3.2. Grid Search and Pipeline Tests
For research purposes, simply running a pipeline once is rarely sufficient. Jarvis-CD includes a **Pipeline Testing** framework that supports grid searches to explore configuration spaces [8].
*   **Configuration File:** Tests are defined in a YAML format that specifies the pipeline structure and the variables to sweep.
*   **`vars` Section:** Defines lists of values for specific package parameters (e.g., `mm_kmeans_df.window_size: [16m, 64m, 128m]`).
*   **`loop` Section:** Defines how to iterate over these variables.
    *   **Coupled Variables:** Variables listed in the same sub-list (e.g., `[pkg.var1, pkg.var2]`) are iterated together. They must have lists of the same length.
    *   **Independent Variables:** Variables in separate sub-lists are iterated as a Cartesian product (nested loops).
*   **`repeat`:** Specifies the number of times to run each configuration to gather statistical averages.
*   **Output:** Results are stored in a specified output directory, facilitating the analysis of performance trends across the parameter sweep [8].

---

## 5. Use Cases and Integration

The versatility of Jarvis-CD is demonstrated through its application in benchmarking and its integration into modern AI-driven workflows.

### 5.1. Automated IOR Benchmark Deployment
One of the most documented use cases is the deployment of the **IOR (Interleaved or Random)** parallel I/O benchmark. This benchmark is notoriously difficult to configure manually due to its many parameters and dependencies on MPI and storage systems.

*   **Manual vs. Automated:** Research indicates that manual configuration of an HPC pipeline for IOR typically takes 5–10 minutes for a human expert. Using Jarvis-CD, this process is reduced to approximately 42–61 seconds [3, 9].
*   **AI Agent Integration:** In the **IOWarp** project, Jarvis-CD is exposed as a tool to AI agents via the **Model Context Protocol (MCP)**. This allows an LLM (e.g., Claude, GPT-4) to receive a high-level prompt like "Deploy IOR on 4 nodes" and autonomously execute the necessary Jarvis commands (`jarvis ppl create`, `append`, `run`) [2, 9].
*   **Performance Results:** Experiments comparing different agent-model combinations (e.g., Cursor + GPT-4o, Claude Code + Sonnet 4) showed that agents using Jarvis could deploy the benchmark correctly and significantly faster than manual methods. For instance, the "OpenCode + Devstral" combination achieved a deployment time of 24.8 seconds [2].

### 5.2. Storage System Deployment
Jarvis-CD is explicitly designed to deploy complex storage systems.
*   **Hermes:** The documentation references Hermes, a hierarchical buffering system. Jarvis manages the deployment of the Hermes daemon (Service) and its interceptors, using the Resource Graph to configure buffering paths automatically [5, 6].
*   **OrangeFS:** The platform handles the setup of parallel file systems like OrangeFS, managing the creation of complex XML configuration files and ensuring that per-node state is correctly stored in the `PRIVATE_DIR` [5, 6].

### 5.3. AI-Driven Scientific Workflows (IOWarp)
Jarvis-CD serves as the "actuator" in the **IOWarp** architecture, which aims to create an AI-driven scientific workflow.
*   **Role:** While IOWarp provides the intelligence and context management (via MCPs), Jarvis-CD provides the execution mechanism. It translates the AI's intent into concrete system commands.
*   **Reproducibility:** By codifying the deployment steps into Jarvis packages and pipelines, the workflow becomes reproducible. The **IOWarp-Observer** component can track the provenance of these agentic workflows, ensuring that scientific results generated by AI-orchestrated benchmarks are traceable and verifiable [2, 9].

---

## 6. Conclusion

Jarvis-CD represents a significant advancement in the management of HPC software stacks. By formalizing the concepts of Services, Applications, and Interceptors into a unified object-oriented framework, it tames the complexity of deploying distributed storage systems. Its three-directory configuration model and Resource Graph abstraction allow it to adapt to diverse hardware environments without manual reconfiguration. Furthermore, its seamless integration with the IOWarp ecosystem and the Model Context Protocol positions it as a critical enabler for the next generation of self-driving laboratories and AI-assisted scientific discovery, where the speed and reliability of automated deployment are paramount.

---

## References

### Publications

#### Conference Papers
[1] "Jarvis: Towards a Shared, User-Friendly, and Reproducible, I/O Infrastructure" (Cernuda et al.). The International Parallel Data Systems Workshop (PDSW'24), 2024. URL: https://grc.iit.edu/members/jaime-cernuda/ [10]
[2] "Towards an AI-driven scientific workflow" (Islam et al.). 21st IEEE International Conference on eScience (eScience '25), 2025. URL: http://cs.iit.edu/~scs/assets/files/islam2025aidriven.pdf [3]
[3] "Towards an AI-driven scientific workflow (Poster)" (Islam et al.). eScience '25, 2025. URL: http://cs.iit.edu/~scs/assets/files/islam2025aidriven_poster.pdf [9]

### Code & Tools
[9] grc-iit/jarvis-cd - Jarvis-cd is a unified platform for deploying various applications. URL: https://github.com/grc-iit/jarvis-cd [1]
[11] iowarp/runtime-deployment - Fork of Jarvis-CD for the IOWarp platform. URL: https://github.com/iowarp/runtime-deployment [12]
[13] grc-iit/jarvis-util - Utilities library for shell execution and MPI/PSSH in Python. URL: https://github.com/grc-iit/jarvis-util [4]
[5] iowarp/ppi-jarvis-util - IOWarp fork of the jarvis-util library. URL: https://github.com/iowarp/ppi-jarvis-util [14]

### Documentation
[12] "Jarvis-CD Index." Gnosis Research Center Documentation. URL: https://grc.iit.edu/docs/jarvis/jarvis-cd/index/ [5, 7]
[15] "Building a Package." Jarvis-CD Documentation. URL: https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/ [6]
[16] "Pipeline Tests." Jarvis-CD Documentation. URL: https://grc.iit.edu/docs/jarvis/jarvis-cd/pipeline-tests/ [8]
[17] "WRF Package." Jarvis-CD Documentation. URL: https://grc.iit.edu/docs/jarvis/jarvis-cd/packages/wrf/ [18]
[19] "IOWarp Deployment." Gnosis Research Center Documentation. URL: https://grc.iit.edu/docs/iowarp/deployment/jarvis/ [7]

### Websites & Other Resources
[20] "IOWarp Project Page." Gnosis Research Center. URL: https://grc.iit.edu/research/projects/iowarp/ [2]