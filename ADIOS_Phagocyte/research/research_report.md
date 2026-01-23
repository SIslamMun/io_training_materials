# The Adaptable IO System (ADIOS): Architecture, Best Practices, and Advanced Features

**Key Points**
*   **Unified Framework:** ADIOS2 is a high-performance I/O framework designed for exascale computing, decoupling the I/O strategy from the application code through a publish/subscribe API.
*   **Adaptable Engines:** It supports various "engines" (e.g., BP5 for files, SST for streaming, DataMan for WAN) that can be switched at runtime without recompiling, allowing seamless transition between file-based I/O and in situ coupling.
*   **Performance:** The default BP5 file format optimizes metadata management and memory consumption, supporting asynchronous I/O and aggregation strategies that scale to thousands of nodes.
*   **Advanced Features:** ADIOS2 integrates operator-based data transformations (compression), GPU-aware I/O (CUDA/Kokkos), and campaign management for organizing scientific workflows.

The Adaptable Input/Output System version 2 (ADIOS2) represents a paradigm shift in high-performance computing (HPC) data management. Developed as part of the U.S. Department of Energy's Exascale Computing Project (ECP), ADIOS2 addresses the widening gap between compute capabilities and storage bandwidth. Unlike traditional I/O libraries that treat data movement as a file-centric operation, ADIOS2 abstracts data movement as a stream of self-describing data steps. This abstraction allows applications to "publish" data and "subscribe" to it, with the underlying transport mechanism—whether it be a parallel file system, a wide-area network, or shared memory—determined at runtime via configuration. This report provides an exhaustive analysis of the ADIOS2 architecture, its diverse engine ecosystem, advanced features like in situ staging and GPU integration, and best practices for performance tuning.

## 1. Introduction and Design Philosophy

The primary motivation behind ADIOS2 is the "I/O Wall" problem, where the ability to generate data outpaces the ability to store it. Traditional approaches, such as writing one file per process or using collective MPI-IO to a single shared file, often fail to scale on pre-exascale and exascale systems due to metadata contention and locking overheads [1, 2].

ADIOS2 was built from the ground up in C++11 to replace ADIOS1, focusing on modularity, sustainability, and performance. It serves as a unified framework that can transport groups of self-describing variables and attributes across different media types [3, 4]. The framework is designed to be:
*   **Adaptable:** Allowing users to switch between file I/O, data staging, and stream processing via runtime configuration (XML/YAML) without changing source code [4].
*   **Step-based:** Reflecting the iterative nature of scientific simulations, data is produced and consumed in "steps," facilitating both streaming and random-access patterns [4].
*   **Extreme Scale:** Capable of handling petabytes of data in single runs on the world's largest supercomputers, such as Frontier and Aurora [1, 4].

## 2. Software Architecture

The internal architecture of ADIOS2 follows a layered abstraction model that maps closely to the Open Systems Interconnection (OSI) model, ensuring separation of concerns between the application interface, data presentation, and transport mechanics [5].

### 2.1 Core Components
ADIOS2 employs a factory pattern where the top-level `ADIOS` object serves as the factory for other components. The hierarchy is as follows:

1.  **ADIOS:** The root object owned by the application. It initializes the library, manages the MPI communicator (or serial context), and parses runtime configuration files [6, 7].
2.  **IO:** Created by the `ADIOS` object, the `IO` component acts as a container for defining variables, attributes, and engine parameters. It represents a logical group of I/O operations. An application can have multiple `IO` objects (e.g., one for checkpointing, one for visualization) [7, 8].
3.  **Variable:** Represents the data payload. Variables are typed, N-dimensional arrays (global or local) or single values. They hold the metadata (name, shape, type) and the data pointer. ADIOS2 supports "Global Arrays," where multiple MPI ranks contribute blocks to a single logical array, and "Local Arrays" for process-local data [8, 9].
4.  **Attribute:** Represents static metadata associated with variables or the dataset as a whole. Attributes are typically small, constant values (e.g., units, time steps) [8, 10].
5.  **Engine:** The heavy lifter of the framework. The `Engine` executes the actual I/O tasks (Put/Get) and manages system resources. It implements the specific transport logic (e.g., writing to a BP file, sending data via RDMA). Engines are polymorphic and selected at runtime [7, 8].
6.  **Operator:** A component that applies transformations to data, such as compression (ZFP, SZ, MGARD) or encryption, before it is handled by the Engine [8, 11].

### 2.2 The Factory Pattern and Polymorphism
The factory pattern allows ADIOS2 to decouple the API from the implementation. When an application calls `io.Open("file.bp", Mode::Write)`, ADIOS2 instantiates the appropriate Engine subclass (e.g., `BP5Writer`) based on the configuration. This design enables the "adaptable" nature of the system; changing the engine type in the configuration file from "BP5" to "SST" switches the application from writing files to streaming data over the network without recompilation [6, 12].

### 2.3 Language Bindings
While the core library is written in C++11, ADIOS2 provides bindings for:
*   **C:** For legacy compatibility and ABI stability.
*   **Fortran:** Supporting standard Fortran 90+ arrays.
*   **Python:** Offering both a "Full API" (mirroring C++) for power users and a "High-Level API" for simplified, Pythonic access (similar to `open()`) [3, 7].

## 3. Engine Ecosystem

The Engine is the mechanism by which ADIOS2 interacts with storage or networks. ADIOS2 provides a rich set of engines tailored for different use cases.

### 3.1 BP5 Engine (Binary Pack 5)
BP5 is the default file-based engine in ADIOS2 (since version 2.9). It is a complete redesign of the previous BP4 format, optimized for high-concurrency writing and reading [13, 14].

*   **Architecture:** BP5 writes data into a directory (e.g., `simulation.bp/`) containing:
    *   `data.M`: The actual data files.
    *   `md.idx`: A global index file.
    *   `mm.0`: A metadata file (specific to BP5) [14].
*   **Key Features:**
    *   **Reduced Memory Footprint:** BP5 uses a list of memory chunks rather than a single contiguous buffer (as in BP4), avoiding expensive reallocations and memory copies. It can often use user memory directly for I/O (zero-copy) [14, 15].
    *   **Metadata Aggregation:** It employs a two-level or selective metadata aggregation strategy, significantly reducing the memory overhead of collecting metadata on large rank counts [14, 16].
    *   **Append Capability:** BP5 supports appending multiple steps to the same file efficiently and allows readers to filter steps, enabling restart capabilities where a simulation resumes from the last valid checkpoint [14, 17].
    *   **Burst Buffer Support:** It supports writing to node-local burst buffers and draining to the parallel file system asynchronously [2, 18].

### 3.2 SST Engine (Sustainable Staging Transport)
The SST engine is designed for **in situ** coupling and data staging. It allows direct data streaming from a producer (writer) to a consumer (reader) via the network, bypassing the file system entirely [12, 19].

*   **Control and Data Planes:** SST separates control messages (metadata, connection management) from data transport.
    *   **Control Plane:** Uses the EVPath library for managing metadata and reader availability.
    *   **Data Plane:** Supports multiple transport backends, including **UCX** (Unified Communication X) for RDMA over InfiniBand/RoCE, **MPI** for coupling within a single MPI job, and **TCP** for WAN or generic Ethernet [2, 16, 20].
*   **Rendezvous:** SST uses a "rendezvous" file (or screen output) to establish the initial connection between decoupled writer and reader applications. Parameters like `RendezvousReaderCount` control how the writer waits for readers [14, 21].
*   **Flow Control:** It supports various queuing policies (e.g., `Block`, `Discard`) to handle speed mismatches between producers and consumers [21, 22].

### 3.3 DataMan Engine
DataMan is specialized for Wide Area Network (WAN) data transfer and real-time streams. It is optimized for scenarios where data needs to be moved between geographically distributed resources (e.g., from an experimental facility to a supercomputer) [11, 12].
*   **Features:** It supports lossy compression and "fast mode" (sacrificing reliability for speed) to maintain high throughput over WANs [11].

### 3.4 Other Engines
*   **HDF5 Engine:** Allows ADIOS2 to read/write HDF5 files, providing interoperability with the HDF5 ecosystem [8].
*   **Inline Engine:** Enables zero-copy data exchange when the writer and reader share the same process memory space (tight coupling) [20].
*   **Null Engine:** Discards all data; useful for benchmarking computation without I/O overhead [8].

## 4. Data Model and File Format

ADIOS2's data model is self-describing, meaning the file (or stream) contains all necessary information to interpret the data (types, dimensions, names) without external schema files.

### 4.1 Variables and Shapes
*   **Global Arrays:** The most common data structure in HPC. A global array has a global dimension (e.g., $1000 \times 1000$) but is distributed across MPI ranks. Each rank writes a local block (e.g., $100 \times 100$) defined by `Start`, `Count`, and `Shape` [8, 9].
*   **Local Arrays:** Arrays that are not stitched together globally. Each block is independent, which is useful for data that varies in size per process (e.g., particle lists) [7].
*   **Joined Arrays:** A specialized form where one dimension is the sum of local dimensions from all writers, useful for aggregating lists [7].

### 4.2 BP5 Directory Structure
A BP5 dataset is a directory (e.g., `mydata.bp/`) rather than a single file. This directory contains:
*   `md.idx`: The index table, allowing fast lookups of variables and steps.
*   `mm.0`: Metadata management file.
*   `data.0`, `data.1`, ...: The actual binary data files. The number of data files is controlled by the `NumAggregators` parameter (sub-filing), decoupling the number of files from the number of MPI ranks [14, 23].

## 5. Advanced Features

### 5.1 In Situ and In Transit Analytics
ADIOS2 facilitates "in situ" (processing data where it is generated) and "in transit" (moving data to staging nodes for processing) workflows.
*   **Coupling:** Using the SST engine, a simulation can stream data to an analysis code (e.g., visualization with ParaView/Catalyst) running on a separate allocation. This avoids the latency of writing to disk [24, 25].
*   **Staging:** Data can be moved to "staging nodes" (intermediate compute nodes) for aggregation, reduction, or compression before final storage or analysis. This pipeline approach hides I/O costs behind computation [26, 27].

### 5.2 Operator-Based Compression
ADIOS2 integrates compression libraries as "Operators." These can be applied to variables to reduce data volume significantly.
*   **Supported Compressors:**
    *   **Lossless:** Blosc (default in BP5), BZip2 [11, 16].
    *   **Lossy:** ZFP, SZ, MGARD. These allow users to trade precision for massive reduction ratios (often 10x-100x) [11].
*   **Usage:** Operators are attached to variables via `AddOperation()`. Parameters like `accuracy` (for lossy) can be tuned. For example, MGARD allows preserving specific "Quantities of Interest" (QoIs) with guaranteed error bounds [26, 28].
*   **Performance:** Studies on WRF and XGC simulations show that using compression can reduce write times by 50% or more and improve time-to-solution by reducing I/O bottlenecks [2, 27, 29].

### 5.3 GPU-Aware I/O
As HPC systems become GPU-centric (e.g., Summit, Frontier), moving data between GPU and CPU memory becomes a bottleneck.
*   **Functionality:** ADIOS2 supports passing GPU pointers (CUDA or Kokkos views) directly to `Put()` and `Get()`.
*   **Mechanism:** Users specify `SetMemorySpace(MemorySpace::GPU)`. ADIOS2 handles the data movement, potentially using GPU-Direct technologies if supported by the backend, or efficiently copying to host buffers if necessary [26, 30, 31].
*   **Kokkos Integration:** ADIOS2 can be built with Kokkos support (`-DADIOS2_USE_Kokkos=ON`), allowing it to accept `Kokkos::View` objects directly [30].

### 5.4 Campaign Management
A newer feature in ADIOS2 is "Campaign Management," which organizes data from multiple related runs (e.g., a parameter sweep or a checkpoint series) into a logical collection.
*   **Archive Files:** It produces `.ACA` campaign archive files that capture metadata about the collection, facilitating data discovery and management across the scientific lifecycle [32].

### 5.5 Derived Variables
ADIOS2 supports defining "Derived Variables" that are calculated on-the-fly from existing variables during the read process. This reduces storage requirements by storing only primary data and computing secondary quantities (e.g., magnitude of a velocity vector) only when needed [8].

## 6. Best Practices and Performance Tuning

To achieve optimal performance with ADIOS2, developers must tune configuration parameters and adhere to API best practices.

### 6.1 Aggregation and Sub-filing
Writing one file per process is non-scalable. ADIOS2 uses aggregators to collect data from multiple ranks and write to a smaller number of files.
*   **NumAggregators:** Controls the number of output files. The default is often one per compute node (shared memory aggregation). Increasing this may improve bandwidth on parallel file systems like Lustre or GPFS if the default count is too low to saturate the OSTs [2, 23].
*   **AggregatorRatio:** Alternatively, specifies the ratio of processes to aggregators [23].

### 6.2 Buffering and Memory Management
*   **Deferred vs. Sync:** Prefer `Put(..., Mode::Deferred)`. This allows ADIOS2 to buffer data and perform I/O asynchronously or in batches at `EndStep()`. `Mode::Sync` forces immediate data handling, which often requires an extra memory copy [15, 33].
*   **BufferChunkSize (BP5):** BP5 manages memory in chunks. Increasing `BufferChunkSize` (default 128MB) can improve performance for large variables by reducing the number of `write()` system calls [15].
*   **MaxShmSize:** For shared memory aggregation, ensuring this buffer is large enough (default 4GB) prevents fallback to slower mechanisms [17].

### 6.3 API Usage
*   **C++11 Bindings:** Use the C++11 API (`adios2.h`) for modern features. Avoid `using namespace adios2` to prevent naming conflicts [34].
*   **Type Consistency:** Ensure the types defined in `DefineVariable<T>` match the application data types exactly (e.g., `int32_t` vs `int`) to avoid casting overheads or errors [33].
*   **Python:** Use the High-Level API for analysis scripts and simple I/O. Use the Full API only when fine-grained control over steps and memory is required [3, 34].

### 6.4 XML Configuration
Externalize engine parameters into an `adios2.xml` or `adios2.yaml` file. This allows changing the engine (e.g., from BP5 to SST) or tuning parameters (e.g., `NumAggregators`) without recompiling the code, which is critical for deploying the same binary in different workflow configurations [7, 8].

## 7. Case Studies

### 7.1 Weather Research and Forecasting (WRF)
Integration of ADIOS2 into the WRF model demonstrated a **10x improvement** in I/O performance compared to the legacy MPI-IO/PnetCDF backend. By utilizing the BP5 engine and node-local burst buffers, WRF could write history files significantly faster. Furthermore, the SST engine enabled in situ analysis pipelines, allowing weather data to be processed concurrently with the simulation [2, 18, 29].

### 7.2 Fusion Energy (XGC)
The XGC fusion code utilizes ADIOS2 for high-volume data output (petabytes per run). ADIOS2's compression operators (MGARD) were used to construct a compression pipeline that runs on staging nodes. This setup achieved high compression ratios while guaranteeing error bounds on critical "Quantities of Interest" (QoIs), effectively decoupling the compression overhead from the main simulation loop [26, 27, 28].

## 8. Conclusion

ADIOS2 stands as a critical infrastructure component for the exascale era. Its architecture, centered on the separation of the logical I/O stream from the physical transport, provides the flexibility needed to navigate complex storage hierarchies and heterogeneous workflows. By leveraging engines like BP5 and SST, and features like operator-based compression and GPU-aware I/O, scientists can maximize throughput and minimize time-to-insight. As HPC systems continue to evolve, ADIOS2's adaptable nature ensures that applications remain performant and sustainable.

## References

### Publications

#### Peer-Reviewed Journals
[35] "ADIOS 2: The Adaptable Input Output System. A framework for high-performance data management" (Godoy et al.). SoftwareX, 2020. DOI: 10.1016/j.softx.2020.100561 | https://doi.org/10.1016/j.softx.2020.100561

#### Conference Papers
[28] "Online and Scalable Data Compression Pipeline with Guarantees on Quantities of Interest" (Banerjee et al.). IEEE 19th International Conference on e-Science, 2023. DOI: 10.1109/e-Science58273.2023.10254934 | https://ieeexplore.ieee.org/document/10254934/
[19] "Streaming Data in HPC Workflows Using ADIOS" (Podhorszki et al.). 2025. https://www.osti.gov/biblio/3002190

#### arXiv & Preprints
[2] "Accelerating WRF I/O Performance with ADIOS2 and Network-based Streaming" (Laufer et al.). arXiv:2304.06603, 2023. DOI: 10.48550/arXiv.2304.06603 | https://arxiv.org/abs/2304.06603
[22] "SST: The Sustainable Staging Transport" (Eisenhauer et al.). arXiv:2410.00178, 2024. https://arxiv.org/pdf/2410.00178

#### Blog Posts & Technical Articles
[24] "In Situ – In Transit Hybrid Analysis using Catalyst, ADIOS2 and ParaView" (Kitware). Kitware Blog, 2024. https://www.kitware.com/in-situ-in-transit-hybrid-analysis-using-catalyst-adios2-and-paraview/
[1] "Adaptable IO System Delivers the Data" (ORNL). OLCF News, 2024. https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/
[13] "ADIOS 2.8 software release with new file format" (ORNL). ORNL Research Highlight, 2022. https://www.ornl.gov/research-highlight/adios-28-software-release-new-file-format

### Code & Tools
[3] ADIOS2 - The Adaptable Input Output System version 2. https://github.com/ornladios/ADIOS2
[36] ADIOS2.jl - Julia bindings for ADIOS2. https://github.com/eschnett/ADIOS2.jl

### Documentation
[8] "ADIOS 2 Documentation." ReadTheDocs. https://adios2.readthedocs.io/
[7] "Components Overview." ADIOS2 Documentation. https://adios2.readthedocs.io/en/latest/components/components.html
[14] "Supported Engines." ADIOS2 Documentation. https://adios2.readthedocs.io/en/latest/engines/engines.html
[14] "BP5 Engine." ADIOS2 Documentation. https://adios2.readthedocs.io/en/latest/engines/engines.html
[30] "GPU-aware I/O." ADIOS2 Documentation. https://adios2.readthedocs.io/en/latest/advanced/gpu_aware.html
[32] "Campaign Management." ADIOS2 Documentation. https://adios2.readthedocs.io/en/latest/advanced/campaign_management.html

### Video & Multimedia
[20] "ADIOS Tutorial SC23" (Podhorszki et al.). SC23 Tutorial Slides, 2023. https://users.nccs.gov/~pnorbert/ADIOS_tutorial_SC23.pdf
[26] "ADIOS OLCF Presentation" (Klasky et al.). OLCF Presentation, 2024. https://www.olcf.ornl.gov/wp-content/uploads/ADIOS_OLCF_July2024.pdf

### Websites & Other Resources
[6] "ADIOS Components." Cornell Virtual Workshop. https://cvw.cac.cornell.edu/parallel-io-libraries/adios/components
[37] "ADIOS Project Page." Exascale Computing Project. https://www.exascaleproject.org/research-project/adios/