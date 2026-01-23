# IOWarp: Advanced Data Management Platform for AI-Augmented Scientific Workflows
GRC-ledFunded[Open Source](https://github.com/iowarp)[Tutorial](https://grc.iit.edu/docs/category/iowarp)
**IOWarp** is a $5 million NSF-funded platform (Award #2411318, 2024-2029) that provides proven infrastructure for intelligent I/O orchestration in scientific computing. IOWarp is a comprehensive data management platform designed to address the unique challenges in scientific workflows that integrate simulation, analytics, and Artificial Intelligence (AI). IOWarp builds on existing storage infrastructures, optimizing data flow and providing a scalable, adaptable platform for managing diverse data needs in modern scientific workflows, particularly those augmented by AI.
* * *
## Project Scope and Vision[​](https://grc.iit.edu/research/projects/iowarp/#project-scope-and-vision "Direct link to Project Scope and Vision")
### Project Goals[​](https://grc.iit.edu/research/projects/iowarp/#project-goals "Direct link to Project Goals")
IOWarp focuses on:
  * Enhancing data exchange and transformation across scientific workflows.
  * Reducing data access latency with advanced storage systems.
  * Developing an open-source, community-driven framework that supports adaptability and innovation.


### Vision[​](https://grc.iit.edu/research/projects/iowarp/#vision "Direct link to Vision")
IOWarp envisions a **modular and flexible architecture** that adapts to the data demands of scientific research, particularly in High-Performance Computing (HPC). This platform aligns with NSF's focus on sustainable, adaptable solutions that can support next-generation scientific workflows.
* * *
## Key Challenges in Scientific Data Management[​](https://grc.iit.edu/research/projects/iowarp/#key-challenges-in-scientific-data-management "Direct link to Key Challenges in Scientific Data Management")
  1. **Data Heterogeneity** : Managing a variety of data formats across workflow stages.
  2. **Data Scale** : Addressing the rapidly increasing volume and velocity of data.
  3. **Data Access Speed** : Overcoming limitations in I/O speed for real-time analytics.
  4. **Data Integrity** : Ensuring quality and consistency across storage and access points.
  5. **Resource Utilization** : Optimizing storage and compute resources to reduce costs and environmental impact.
  6. **Interoperability** : Enabling seamless data transfer across workflow stages and computing paradigms.


* * *
## From Current State to IOWarp: The Transformation[​](https://grc.iit.edu/research/projects/iowarp/#from-current-state-to-iowarp-the-transformation "Direct link to From Current State to IOWarp: The Transformation")
IOWarp transforms how scientific data flows through modern HPC systems by introducing intelligent orchestration across the entire storage hierarchy.
![Current State: Traditional PFS Architecture](https://grc.iit.edu/assets/images/PFS-HourGlass-d9970f7403fca51f21c2df23efa62fe9.jpg)
#### Current State
_Traditional parallel file system architecture with limited data management capabilities_
![Future State: IOWarp-Enhanced Architecture](https://grc.iit.edu/assets/images/IoWarp-HourGlass-f7ca9f9079d4bbb54f4293be63cd75ab.jpg)
#### Future State with IOWarp
_IOWarp-enhanced architecture with intelligent data orchestration and AI integration_
**Traditional systems** rely on manual data management and static storage hierarchies, leading to inefficient data movement and underutilized resources. **IOWarp** introduces intelligent, automated data orchestration that adapts to workflow demands, dramatically improving performance and resource utilization.
* * *
## Architecture[​](https://grc.iit.edu/research/projects/iowarp/#architecture "Direct link to Architecture")
### Modular Architecture[​](https://grc.iit.edu/research/projects/iowarp/#modular-architecture "Direct link to Modular Architecture")
IOWarp's architecture comprises several core components designed to handle various aspects of data flow, integrity, and interoperability.
![IOWarp Architecture](https://grc.iit.edu/assets/images/architecture-e617975df18d96f006ab5e082d352852.svg)
### Technical Architecture[​](https://grc.iit.edu/research/projects/iowarp/#technical-architecture "Direct link to Technical Architecture")
This section describes the core components of IOWarp's data management platform and their functionality within scientific workflows.
#### Content Assimilation Engine (CAE)[​](https://grc.iit.edu/research/projects/iowarp/#content-assimilation-engine-cae "Direct link to Content Assimilation Engine \(CAE\)")
The **Content Assimilation Engine (CAE)** transforms diverse format-specific data into IOWarp's unified data representation format, **Content** , optimized for data transfer. The CAE:
  * Integrates with data sources (e.g., Globus, S3, PFS).
  * Applies data layout and semantic tagging, preserving context across workflow stages.
  * Exports data back to repositories post-processing, ensuring data longevity.


#### Content Transfer Engine (CTE)[​](https://grc.iit.edu/research/projects/iowarp/#content-transfer-engine-cte "Direct link to Content Transfer Engine \(CTE\)")
The **Content Transfer Engine (CTE)** manages efficient data flow across workflow stages and storage systems.
![Content Transfer Engine with LabIOS](https://grc.iit.edu/assets/images/cte-labios-ed2213ea4b6006e8d1a5c630c285f6d3.jpg)
_CTE architecture with LabIOS integration for multi-tiered storage management_
Key features include:
  * **Multi-tiered I/O** : Supports interactions with advanced storage hardware, including NVMe SSDs and CXL-powered devices.
  * **GPU Direct I/O** : Directly transfers data between GPUs for faster model training and inference.
  * **Secure Transfer Protocols** : Ensures data security during transfers.


#### Content Exploration Interface (CEI)[​](https://grc.iit.edu/research/projects/iowarp/#content-exploration-interface-cei "Direct link to Content Exploration Interface \(CEI\)")
The **Content Exploration Interface (CEI)** enables advanced data querying and retrieval, incorporating tools like:
![Content Exploration Interface Architecture](https://grc.iit.edu/assets/images/architecture%20\(2\)-ce4c91d084e364c52206b2af25a0e842.png)
_CEI architecture showing natural language query processing and integration_
  * **WarpGPT** : A language model-driven interface for complex scientific queries, capable of handling anomaly detection, mathematical operations, and user-defined extensions.
  * **FAIR Compliance** : Implements principles to support Findable, Accessible, Interoperable, and Reusable data within scientific workflows.


#### Platform Plugins Interface (PPI)[​](https://grc.iit.edu/research/projects/iowarp/#platform-plugins-interface-ppi "Direct link to Platform Plugins Interface \(PPI\)")
The **Platform Plugins Interface (PPI)** extends IOWarp's functionality, allowing integration with external services, such as:
  * **Global Schedulers** (e.g., Slurm): For resource and task allocation.
  * **Workflow Managers** (e.g., Pegasus): For task orchestration and system telemetry.
  * **Custom Libraries** : Allows integration with libraries for data tracing, encryption, and transformations.


* * *
### High-Level Data Flow in IOWarp[​](https://grc.iit.edu/research/projects/iowarp/#high-level-data-flow-in-iowarp "Direct link to High-Level Data Flow in IOWarp")
The data flow within IOWarp follows an organized pipeline from acquisition and transformation to storage and retrieval. Here's a typical data path:
  1. **Data Ingestion** via the **Content Assimilation Engine**.
  2. **Data Storage Optimization** through the **Content Transfer Engine** and hardware-optimized storage.
  3. **Data Retrieval** using the **Content Exploration Interface** , with support for complex, low-latency queries.


* * *
### API Descriptions[​](https://grc.iit.edu/research/projects/iowarp/#api-descriptions "Direct link to API Descriptions")
#### Core APIs[​](https://grc.iit.edu/research/projects/iowarp/#core-apis "Direct link to Core APIs")
  1. **Repository Connection API** : Manages connection to external data sources.
     * Example Methods: `link/unlink`, `upload/download`.
  2. **Content Management API** : Allows querying, editing, and locating content based on metadata and tags.
     * Example Methods: `queryContent`, `editContent`.
  3. **Content Exploration API** : Supports advanced data operations with low-latency retrieval.
     * Example Methods: `processQuery`, `executeDAG`.
  4. **AI/ML Integration APIs** : Facilitates data exchange for training and inference tasks within AI frameworks like TensorFlow or PyTorch.
     * Example Methods: `defineDataset`, `prefetchToGPU`.


* * *
## Towards Agentic-Driven Scientific Workflows[​](https://grc.iit.edu/research/projects/iowarp/#towards-agentic-driven-scientific-workflows "Direct link to Towards Agentic-Driven Scientific Workflows")
Modern scientific computing is evolving towards **agentic-driven workflows** , where AI agents autonomously orchestrate complex computational tasks, interact with scientific data, and manage HPC resources through natural language interfaces. IOWarp is at the forefront of this transformation, providing the infrastructure and tools necessary to enable intelligent, automated scientific discovery.
Our work on agentic-driven scientific workloads includes the development of **Warpio CLI** and integration with **Model Context Protocols (MCPs)** , enabling researchers to interact with HPC systems, scientific data formats, and computational workflows using natural language and AI-powered assistance.
![Warpio CLI Interface](https://grc.iit.edu/assets/images/warpio-screenshot-d62875cf3c66a78e821881c99fbaf0d2.png)
_Warpio CLI: Command-line interface for agentic scientific workflows_
### AI Agents for Scientific Computing[​](https://grc.iit.edu/research/projects/iowarp/#ai-agents-for-scientific-computing "Direct link to AI Agents for Scientific Computing")
Following Anthropic's November 2024 release of the Model Context Protocol (MCP), IOWarp has pioneered the integration of AI agents into scientific computing environments. These agents can:
  * **Understand Scientific Data** : Parse and analyze data from formats like HDF5, Adios BP5, NetCDF
  * **Orchestrate Workflows** : Submit jobs, manage resources, and coordinate multi-step computational pipelines
  * **Generate Insights** : Perform data analysis, create visualizations, and answer scientific queries
  * **Ensure Reproducibility** : Track provenance and enable replay of complex workflows


### Model Context Protocols for Science[​](https://grc.iit.edu/research/projects/iowarp/#model-context-protocols-for-science "Direct link to Model Context Protocols for Science")
![Warpio accessing National Data Platform](https://grc.iit.edu/assets/images/ndp-claude-bc05fe3dee681f5757e812b38a66a68f.png)
_Warpio accessing the National Data Platform to download and analyze the latest EarthScope seismological datasets_
IOWarp provides a growing collection of **scientific MCPs** available at [github.com/iowarp/iowarp-mcps](https://github.com/iowarp/iowarp-mcps). Some examples include:
  * **Adios MCP** : Analyze and query Adios BP5 files from simulations like LAMMPS, WRF, and more
  * **HDF5 MCP** : Explore HDF5 datasets, read metadata, and extract scientific data
  * **Jarvis MCP** : Automated application deployment, environment management, and orchestration
  * **Slurm MCP** : Job scheduling, resource allocation, and queue management
  * **System Monitoring MCPs** : Real-time performance metrics and resource utilization tracking


### Scientific Application Examples[​](https://grc.iit.edu/research/projects/iowarp/#scientific-application-examples "Direct link to Scientific Application Examples")
IOWarp supports a wide range of scientific applications through its flexible architecture and scientific MCPs, enabling researchers to interact with complex data using natural language.
#### LAMMPS Molecular Dynamics Simulation[​](https://grc.iit.edu/research/projects/iowarp/#lammps-molecular-dynamics-simulation "Direct link to LAMMPS Molecular Dynamics Simulation")
![Atom Trajectory Visualization](https://grc.iit.edu/assets/images/atom_1000_trajectory-6f9c190b460785dc1fdcc7c0cbfdc33c.png)
_Atom trajectory analysis from LAMMPS simulation_
![Detailed Atom Analysis](https://grc.iit.edu/assets/images/atom_1000_crop-d7f54b743cc6c13b8306adccdfadce64.png)
_Detailed single-atom trajectory over time_
**Dataset** : LAMMPS molecular dynamics simulation output stored in Adios BP5 format with atom position data over time.
**Execution** : Agents used **Adios-MCP** , which provides AI systems with the ability to read and query Adios BP5 files, to analyze the simulation data and generate visualizations.
**Prompt** : _"Can you write me a python script that plots the trajectory of a single atom over time. The atom of choice should be a parameter to the script. The output should be a PNG image with the results. Please run the script for atom 23."_
**Result** : The Adios-MCP enabled the agent to automatically read the BP5 file structure, extract position data for the specified atom, generate Python visualization code, execute the script, and produce the trajectory visualization. This eliminates the need for researchers to manually parse the Adios file format or write custom analysis scripts.
#### Pipe Flow Data Visualization via ParaView-MCP[​](https://grc.iit.edu/research/projects/iowarp/#pipe-flow-data-visualization-via-paraview-mcp "Direct link to Pipe Flow Data Visualization via ParaView-MCP")
![Pipe flow isosurface and orthogonal slices](https://grc.iit.edu/assets/images/paraview_pipe-bb405e19452dab94bdf296566fea5118.png)
_3D flow visualization combining isosurface and orthogonal slice planes generated through natural language commands_
**Dataset** : Incompact3d pipe flow simulation (data.bp5) with pressure and velocity fields.
**Execution** : Agents used **ParaView-MCP** , a service that connects AI systems to the ParaView visualization engine, to load the dataset and generate the 3D visualization.
**Prompt** : _"Explore the pipe flow data. Generate an isosurface of pressure at pp=0.1 plus three orthogonal slice planes (X, Y, Z)."_
**Result** : Produced a combined 3D flow visualization without manual setup, highlighting internal flow structures. The ParaView-MCP enabled researchers to create complex visualizations through natural language, eliminating the need for manual ParaView configuration, Python scripting, or format conversion. The agent automatically:
  * Loaded the BP5 simulation data
  * Generated a pressure isosurface at the specified threshold
  * Created three orthogonal cutting planes
  * Composed the final visualization showing both surface and volumetric flow features


This demonstrates how IOWarp's MCP ecosystem transforms scientific visualization from a multi-step manual process into a conversational workflow, allowing researchers to focus on interpreting results rather than configuring visualization pipelines.
* * *
### System Observability & Monitoring[​](https://grc.iit.edu/research/projects/iowarp/#system-observability--monitoring "Direct link to System Observability & Monitoring")
IOWarp provides comprehensive observability features for tracking system performance and resource utilization in real-time.
![IOWarp Observability Dashboard](https://grc.iit.edu/assets/images/observability-51aa6e076a168a8b2d5ff81ffbac090e.png)
_Real-time observability dashboard for monitoring IOWarp performance and resource utilization_
Features include:
  * **Real-time Metrics** : Performance tracking across all storage tiers
  * **Resource Monitoring** : DRAM, NVMe, GPU memory, and PFS utilization
  * **Workflow Visualization** : End-to-end workflow execution and bottleneck identification
  * **Reproducibility Tracking** : Full provenance capture for agentic workflows


* * *
### Performance Results & Benchmarks[​](https://grc.iit.edu/research/projects/iowarp/#performance-results--benchmarks "Direct link to Performance Results & Benchmarks")
We evaluated ContextWarp (IOWarp's agentic framework) across multiple dimensions to understand the performance, correctness, and reliability of AI-driven scientific workflows. Experiments were conducted on Chameleon Cloud using compute nodes with 40GB A100 GPUs.
### Agentic Workflow Performance: EarthScope Dataset Analysis[​](https://grc.iit.edu/research/projects/iowarp/#agentic-workflow-performance-earthscope-dataset-analysis "Direct link to Agentic Workflow Performance: EarthScope Dataset Analysis")
**Experiment** : Automated download and visualization of seismological data from the National Data Platform using AI agents.
**Setup** : Claude Code with Sonnet 4 model, with and without IOWarp Context (MCPs and machine configuration).
**Task** : _"Use the ndp mcp to find the latest dataset of the earthscope organization, find the url of the geojson and csv they contain, and download them. The geojson is metadata, the csv contains seismograph data. Plot a figure containing the data of each axis on their own subfigure."_
**Results** :
  * **With IOWarp Context** : Successfully completed in **2 minutes** with correct tool selection and visualization
  * **Without IOWarp Context** : Failed to execute (agent could not identify correct tools or access methods)
  * **Manual Process** : ~**15 minutes** (login, search, download, build visualization script)
  * **Speedup** : **7.5x faster** than manual workflow


This demonstrates that IOWarp Context (MCPs + system prompts) is essential for enabling AI agents to interact with scientific infrastructure effectively.
### Agent Configuration Performance: Jarvis IOR Deployment[​](https://grc.iit.edu/research/projects/iowarp/#agent-configuration-performance-jarvis-ior-deployment "Direct link to Agent Configuration Performance: Jarvis IOR Deployment")
We compared eight agent-model combinations deploying the IOR parallel I/O benchmark using [**Jarvis**](https://github.com/grc-iit/jarvis-cd) (IOWarp's deployment automation system) across five distinct prompts to assess performance and correctness tradeoffs.
![Average Deployment Duration by Agent-Model Configuration](https://grc.iit.edu/assets/images/duration_chart_w_OC-544a177f8989f42c6c389f6c6b4f25b9.png)
_Execution time comparison across different agent and model configurations_
**Execution Time Results** (average across 5 prompts):
  * **OpenCode + Devstral** (local LLM for execution): **24.8 seconds** (fastest)
  * **Cursor + GPT-4o** : **37.7 seconds**
  * **Gemini CLI + Gemini 2.5 Pro** : **85.9 seconds**
  * **Claude Code + Sonnet 4** : **109.2 seconds**


**Key Finding** : Agents using small, self-hosted LLMs for execution (like Devstral) with large cloud models only for planning achieved competitive or superior performance compared to using large models for all operations. This validates IOWarp's split planning-execution design for efficiency, cost reduction, and data security.
### Tool Call Success Rates[​](https://grc.iit.edu/research/projects/iowarp/#tool-call-success-rates "Direct link to Tool Call Success Rates")
![IOR Tool Call Success Rate Comparisons](https://grc.iit.edu/assets/images/figure_ior_performance_test-e9418e89004d413b240e916f2993c66c.png)
_Success rates for correctly identifying and invoking scientific tools across agent-model combinations_
### Robustness Across Diverse Prompts[​](https://grc.iit.edu/research/projects/iowarp/#robustness-across-diverse-prompts "Direct link to Robustness Across Diverse Prompts")
![Robustness Evaluation Across 20 Prompt Variations](https://grc.iit.edu/assets/images/config_success_rates-1d7fb3d9dbe14d75caea8a032515736f.png)
_Configuration success rates when tested with 20 different prompt styles ranging from simple to highly detailed_
**Robustness Test** : 20 prompts with varying detail levels for IOR deployment, from simple (_"Deploy ior with 8 processes using the deployment agent"_) to detailed bash scripts.
**Configuration Success Rates** (20 prompts):
  * **Claude Code + Sonnet 4** : **100%**
  * **Gemini CLI + Gemini 2.5 Pro** : **100%**
  * **OpenCode CLI + Gemini 2.5 Pro** : **100%**
  * **OpenCode CLI + Devstral-2hl** : **100%**
  * **Cursor + GPT-5** : Lower success rate (struggled with parameter synonyms like "nprocs" vs "number of processes")


**Key Finding** : IOWarp's agentic design is highly resilient to changes in prompt phrasing and information granularity. Configurations using local LLMs for execution achieved 100% success, demonstrating that the split plan-execution architecture effectively balances cost, security, and reliability.
* * *
### Demonstrations[​](https://grc.iit.edu/research/projects/iowarp/#demonstrations "Direct link to Demonstrations")
#### IOWarp-MCP Demo[​](https://grc.iit.edu/research/projects/iowarp/#iowarp-mcp-demo "Direct link to IOWarp-MCP Demo")
Full workflow showcase from scheduling to deployment, data collection, and analysis using IOWarp MCPs with Claude Code.
#### IOWarp Reproducibility Demo[​](https://grc.iit.edu/research/projects/iowarp/#iowarp-reproducibility-demo "Direct link to IOWarp Reproducibility Demo")
Showcase of IOWarp's reproducibility visualizer for agentic workflows, enabling full provenance tracking and replay.
#### IOWarp-MCP Adios Demo[​](https://grc.iit.edu/research/projects/iowarp/#iowarp-mcp-adios-demo "Direct link to IOWarp-MCP Adios Demo")
Showcase of IOWarp Adios MCP providing full analysis of a BP5 file generated by LAMMPS, demonstrating natural language queries on scientific data.
* * *
## Publications[​](https://grc.iit.edu/research/projects/iowarp/#publications "Direct link to Publications")
Authors | Title | Venue | Type | Date | Links  
---|---|---|---|---|---  
H. Devarajan,   
A. Kougkas,   
H. Zheng,   
V. Vishwanath,   
X.-H. Sun | [Stimulus: Accelerate Data Management for Scientific AI applications in HPC](https://grc.iit.edu/publications/devarajan-2022-stimulus-4b4c) | The 22nd IEEE/ACM International Symposium on Cluster, Cloud and Internet Computing (CCGRID'22), May 16-19, 2022 | Conference | May, 2022 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/stimulus2022.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/stimulus2022.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/stimulus2022.pdf)  
J. Cernuda,   
H. Devarajan,   
L. Logan,   
K. Bateman,   
N. Rajesh,   
J. Ye,   
A. Kougkas,   
X.-H. Sun | [HFlow: A Dynamic and Elastic Multi-Layered Data Forwarder](https://grc.iit.edu/publications/cernuda-2021-hflow-2f5b) | The 2021 IEEE International Conference on Cluster Computing (CLUSTER'21), September 7-10, 2021 | Conference | September, 2021 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/cernuda2021HFlow.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/cernuda2021HFlow.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/cernuda2021HFlow.pdf)  
N. Rajesh,   
H. Devarajan,   
J. Cernuda,   
K. Bateman,   
L. Logan,   
J. Ye,   
A. Kougkas,   
X.-H. Sun | [Apollo: An ML-assisted Real-Time Storage Resource Observer](https://grc.iit.edu/publications/rajesh-2021-apollo-dbd8) | The 30th ACM International Symposium on High-Performance Parallel and Distributed Computing (HPDC'21), June 21-25, 2021 | Conference | June, 2021 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/rajesh2021apollo.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/rajesh2021apollo.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/rajesh2021apollo.pdf)  
H. Devarajan,   
H. Zheng,   
A. Kougkas,   
X.-H. Sun,   
V. Vishwanath | [DLIO: A Data-Centric Benchmark for Scientific Deep Learning Applications](https://grc.iit.edu/publications/devarajan-2021-dlio-0272) | The 2021 IEEE/ACM International Symposium in Cluster, Cloud, and Internet Computing (CCGrid'21), May 17 - 20, 2021 Best paper award | Conference | May, 2021 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/devarajan2021dlio.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/devarajan2021dlio.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/devarajan2021dlio.pdf),   
[video](https://youtu.be/_rRhQBaHVs8)  
H. Devarajan,   
A. Kougkas,   
X.-H. Sun | [HReplica: A Dynamic Data Replication Engine with Adaptive Compression for Multi-Tiered Storage](https://grc.iit.edu/publications/devarajan-2020-hreplica-44a8) | The 2020 IEEE International Conference on Big Data (Big Data'20), December 10-13, 2020 | Conference | December, 2020 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/devarajan2020HReplica.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/devarajan2020HReplica.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/devarajan2020HReplica.pdf)  
H. Devarajan,   
A. Kougkas,   
X.-H. Sun | [A Dynamic Multi-Tiered Storage System for Extreme Scale Computing](https://grc.iit.edu/publications/devarajan-2020-dynamic-multi-ef19) | The International Conference for High Performance Computing, Networking, Storage and Analysis (SC'20) | Poster | November, 2020 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/devarajan2020dynamic.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/devarajan2020dynamic.txt),   
[extended abstract](http://cs.iit.edu/~scs/assets/files/devarajan2020dynamic-abstract.pdf),   
[poster](http://cs.iit.edu/~scs/assets/files/devarajan2020dynamic-poster.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/devarajan2020dynamic-slides.pdf)  
H. Devarajan,   
A. Kougkas,   
K. Bateman,   
X.-H. Sun | [HCL: Distributing Parallel Data Structures in Extreme Scales](https://grc.iit.edu/publications/devarajan-2020-hcl-d2f4) | IEEE International Conference on Cluster Computing (CLUSTER'20), Sept. 14-17, 2020 | Conference | September, 2020 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/hcl.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/hcl.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/devarajan2020hcl.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/hcl-slides.pdf)  
H. Devarajan,   
A. Kougkas,   
L. Logan,   
X.-H. Sun | [HCompress: Hierarchical Data Compression for Multi-Tiered Storage Environments](https://grc.iit.edu/publications/devarajan-2020-hcompress-70f7) | IEEE International Parallel and Distributed Processing Symposium (IPDPS'20), May 18-22, 2020 | Conference | May, 2020 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/hcompress2020.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/hcompress2020.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/hcompress.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/hcompress_ipdps.pdf)  
H. Devarajan,   
A. Kougkas,   
X.-H. Sun | [HFetch: Hierarchical Data Prefetching for Scientific Workflows in Multi-Tiered Storage Environments](https://grc.iit.edu/publications/devarajan-2020-hfetch-46e9) | IEEE International Parallel and Distributed Processing Symposium (IPDPS'20), May 18-22, 2020 | Conference | May, 2020 |  [BibTeX](http://www.cs.iit.edu/~scs/http://cs.iit.edu/~scs/assets/files/HFetch.bib),   
[citation](http://www.cs.iit.edu/~scs/http://cs.iit.edu/~scs/assets/files/HFetch.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/hfetch_conference_proceedings.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/hfetch_ipdps.pdf)  
A. Kougkas,   
H. Devarajan,   
X.-H. Sun | [I/O Acceleration via Multi-Tiered Data Buffering and Prefetching](https://grc.iit.edu/publications/kougkas-2020-io-acceleration-4458) | Journal of Computer Science and Technology (JCST'20), vol 35. no 1. pp 92-120 | Journal | January, 2020 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/IOaccel.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/IOaccel.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/IOaccel.pdf)  
H. Devarajan,   
A. Kougkas,   
X.-H. Sun | [HFetch: Hierarchical Data Prefetching in Multi-Tiered Storage Environments](https://grc.iit.edu/publications/devarajan-2019-hfetch-980e) | The International Conference for High Performance Computing, Networking, Storage and Analysis (SC'19) Best Poster Nominee, Ph.D Forum | Poster | November, 2019 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/hfetchposter2019.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/hfetchposter2019.txt),   
[extended abstract](http://cs.iit.edu/~scs/assets/files/hfetch_extended_abstract.pdf),   
[poster](http://cs.iit.edu/~scs/assets/files/hetch_poster.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/hetch_ppt.pdf)  
A. Kougkas,   
H. Devarajan,   
J. Lofstead,   
X.-H. Sun | [LABIOS: A Distributed Label-Based I/O System](https://grc.iit.edu/publications/kougkas-2019-labios-8411) | The 28th International Symposium on High-Performance Parallel and Distributed Computing (HPDC'19), Phoenix, USA 2019. pp. 13-24. Karsten Schwan Best Paper Award | Conference | June, 2019 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/kougkas2019labios.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/kougkas2019labios.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/kougkas2019labios.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/labios_slides.pdf)  
H. Devarajan,   
A. Kougkas,   
X.-H. Sun | [An Intelligent, Adaptive, and Flexible Data Compression Framework](https://grc.iit.edu/publications/devarajan-2019-intelligent--e9fd) | IEEE/ACM International Symposium in Cluster, Cloud, and Grid Computing (CCGrid'19), Larnaca, Cyprus2019. pp. 82-91. | Conference | May, 2019 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/devarajan2019intelligent.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/devarajan2019intelligent.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/devarajan2019intelligent.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/ares_ccgrid.pdf)  
H. Devarajan,   
A. Kougkas,   
P. Challa,   
X.-H. Sun | [Vidya: Performing Code-Block I/O Characterization for Data Access Optimization](https://grc.iit.edu/publications/devarajan-2018-vidya-e65b) | The IEEE International Conference on High Performance Computing, Data, and Analytics 2018 (HiPC'18), Bengaluru, India2018. pp. 255-264. | Conference | December, 2018 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/devarajan2018vidya.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/devarajan2018vidya.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/devarajan2018vidya_paper.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/vidya.pdf)  
A. Kougkas,   
H. Devarajan,   
X.-H. Sun,   
J. Lofstead | [Harmonia: An Interference-Aware Dynamic I/O Scheduler for Shared Non-Volatile Burst Buffers](https://grc.iit.edu/publications/kougkas-2018-harmonia-5ca9) | The IEEE International Conference on Cluster Computing 2018 (Cluster'18), Belfast, UK2018. pp. 290-301. | Conference | September, 2018 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/kougkas2018harmonia.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/kougkas2018harmonia.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/kougkas2018harmonia.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/Harmonia_slides.pdf)  
A. Kougkas,   
H. Devarajan,   
X.-H. Sun | [Hermes: A Heterogeneous-Aware Multi-Tiered Distributed I/O Buffering System](https://grc.iit.edu/publications/kougkas-2018-hermes-25f4) | The 27th ACM International Symposium on High-Performance Parallel and Distributed Computing (HPDC), Tempe, AZ, USA, 2018. pp. 219-230 | Conference | June, 2018 |  [BibTeX](http://cs.iit.edu/~scs/assets/files/kougkas2018hermes.bib),   
[citation](http://cs.iit.edu/~scs/assets/files/kougkas2018hermes.txt),   
[PDF](http://cs.iit.edu/~scs/assets/files/Hermes.pdf),   
[slides](http://cs.iit.edu/~scs/assets/files/Hermes_slides.pdf)  
* * *
## Resources & Links[​](https://grc.iit.edu/research/projects/iowarp/#resources--links "Direct link to Resources & Links")
  * **GitHub Organization** : [github.com/iowarp](https://github.com/iowarp/)
  * **IOWarp MCPs** : [github.com/iowarp/iowarp-mcps](https://github.com/iowarp/iowarp-mcps)
  * **Documentation** : [IOWarp Tutorial](https://grc.iit.edu/docs/iowarp/index)


* * *
## Collaborators[​](https://grc.iit.edu/research/projects/iowarp/#collaborators "Direct link to Collaborators")
![HDF Group](https://grc.iit.edu/assets/images/hdfgroup-7ae19c2833834b7a087622ef6c67a889.jpg)
**HDF Group**
![University of Utah](https://grc.iit.edu/assets/images/utah-6fa3cfed642448f57e766d820b68fa70.jpg)
**University of Utah**
### Deployment Partners[​](https://grc.iit.edu/research/projects/iowarp/#deployment-partners "Direct link to Deployment Partners")
IOWarp is deployed and being evaluated at leading national laboratories:
  * **Argonne National Laboratory** - Advanced computing research and leadership computing facilities
  * **Lawrence Livermore National Laboratory** - High-performance computing systems and simulation science
  * **NERSC (National Energy Research Scientific Computing Center)** - DOE scientific computing facility


* * *
## Sponsor[​](https://grc.iit.edu/research/projects/iowarp/#sponsor "Direct link to Sponsor")
![National Science Foundation](https://grc.iit.edu/assets/images/nsf-fb7efe9286a9b499c5907d82af3e70fd.png)
National Science Foundation
Award #2411318 (2024-2029)
**$5 Million**
Gnosis Research Center
  * Stuart Building   
Room 112i and 010   
10 W. 31st Street   
Chicago, Illinois 60616 
  * Email: grc@illinoistech.edu   
Phone: [+1 312 567 6885](tel:3125676885)


Featured Projects
  * [IOWarp](https://grc.iit.edu/research/projects/iowarp)
  * [ChronoLog](https://grc.iit.edu/research/projects/chronolog)
  * [LABIOS](https://grc.iit.edu/research/projects/labios)
  * [Coeus](https://grc.iit.edu/research/projects/coeus)
  * [Hermes](https://grc.iit.edu/research/projects/hermes)


Tutorials
  * [Linux Introduction](https://grc.iit.edu/docs/category/linux-introduction)
  * [Installing HPC Software](https://grc.iit.edu/docs/category/installing-hpc-software)
  * [Important Environment Variables](https://grc.iit.edu/docs/category/important-environment-variables)
  * [C++ Introduction](https://grc.iit.edu/docs/category/c-introduction)
  * [Ares User Guide](https://grc.iit.edu/docs/category/ares-research-cluster)


Links
  * [GRC Careers](https://grc.iit.edu/careers)
  * [GRC GitHub](https://github.com/grc-iit)
  * [GRC LinkedIn](https://www.linkedin.com/company/gnosis-research-center/)
  * [GRC X](https://twitter.com/grc_iit)
  * [GRC YouTube](https://www.youtube.com/channel/UCNtEyAt4_ckpIbX-gSv8sww)
  * [Illinois Tech](https://www.iit.edu/)
  * [SCS Lab](http://cs.iit.edu/~scs/)


Copyright © 2026 Gnosis Research Center (GRC).
