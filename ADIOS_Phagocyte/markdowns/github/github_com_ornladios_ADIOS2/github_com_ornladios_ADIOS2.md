# ADIOS2

> Next generation of ADIOS developed in the Exascale Computing Program

## Repository Info

- **Stars:** 317
- **Forks:** 146
- **Language:** C++
- **License:** Apache License 2.0
- **Topics:** adios, cmake, ecp, exascale, exascale-computing, hdf5, high-performance-computing, hpc, io
- **Source:** `https://github.com/ornladios/ADIOS2`
- **Branch:** `master`
- **Commit:** `7a21e4ef2f5d`
- **Last Commit:** 2026-01-22 21:30:05 -0500
- **Commits:** 1
- **Extracted:** 2026-01-23T02:37:18.360280


## Directory Structure

```
ADIOS2/
├── .e4s/
│   └── e4s.yaml
├── .github/
│   ├── actions/
│   │   └── save-context-artifacts/
│   │       └── action.yml
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── new_release.md
│   ├── workflows/
│   │   ├── backport.yml
│   │   ├── everything.yml
│   │   ├── external.yml
│   │   ├── pypackaging.yml
│   │   ├── scorecard-analysis.yml
│   │   └── stale.yml
│   └── dependabot.yml
├── .gitlab/
│   ├── config/
│   │   ├── ccache.cmake
│   │   ├── dynamic_pipeline.yml.in
│   │   ├── generate_pipelines.py
│   │   ├── kokkos.sh
│   │   └── SpackCIBridge.py
│   ├── gitlab-ci-ascent.yml
│   ├── gitlab-ci-frontier.yml
│   └── gitlab-ci-spack.yml
├── bindings/
│   ├── C/
│   │   ├── adios2/
│   │   │   └── c/
│   │   ├── adios2_c.h
│   │   └── CMakeLists.txt
│   ├── CXX/
│   │   ├── adios2/
│   │   │   └── cxx/
│   │   ├── adios2.h
│   │   ├── CMakeLists.txt
│   │   └── cxx11_wrapper.h.in
│   ├── Fortran/
│   │   ├── f2c/
│   │   │   ├── adios2_f2c_adios.cpp
│   │   │   ├── adios2_f2c_adios_mpi.cpp
│   │   │   ├── adios2_f2c_attribute.cpp
│   │   │   ├── adios2_f2c_common.h
│   │   │   ├── adios2_f2c_engine.cpp
│   │   │   ├── adios2_f2c_io.cpp
│   │   │   ├── adios2_f2c_io_mpi.cpp
│   │   │   ├── adios2_f2c_operator.cpp
│   │   │   └── adios2_f2c_variable.cpp
│   │   ├── modules/
│   │   │   ├── contains/
│   │   │   ├── adios2_adios_init_mod.F90
│   │   │   ├── adios2_adios_init_mpi_smod.F90
│   │   │   ├── adios2_adios_init_serial_smod.F90
│   │   │   ├── adios2_adios_mod.f90
│   │   │   ├── adios2_attribute_data_mod.f90
│   │   │   ├── adios2_attribute_mod.f90
│   │   │   ├── adios2_engine_begin_step_mod.f90
│   │   │   ├── adios2_engine_get_mod.f90
│   │   │   ├── adios2_engine_mod.f90
│   │   │   ├── adios2_engine_put_mod.f90
│   │   │   ├── adios2_functions_allocate_mod.f90
│   │   │   ├── adios2_functions_mod.f90
│   │   │   ├── adios2_io_define_attribute_mod.f90
│   │   │   ├── adios2_io_define_derived_variable_mod.f90
│   │   │   ├── adios2_io_define_variable_mod.f90
│   │   │   ├── adios2_io_mod.f90
│   │   │   ├── adios2_io_open_mod.F90
│   │   │   ├── adios2_io_open_mpi_smod.F90
│   │   │   ├── adios2_io_open_serial_smod.F90
│   │   │   ├── adios2_mod.f90
│   │   │   ├── adios2_operator_mod.f90
│   │   │   ├── adios2_parameters_mod.f90
│   │   │   ├── adios2_variable_max_mod.f90
│   │   │   ├── adios2_variable_min_mod.f90
│   │   │   └── adios2_variable_mod.f90
│   │   └── CMakeLists.txt
│   ├── Matlab/
│   │   ├── test/
│   │   │   ├── heat.bp.dir/
│   │   │   ├── heat.bp
│   │   │   ├── test1_read.m
│   │   │   ├── test1_read.py
│   │   │   ├── test1_read_hl.py
│   │   │   ├── test1_write.py
│   │   │   ├── test1_write_hl.py
│   │   │   └── TestADIOSRead.m
│   │   ├── adios.m
│   │   ├── adiosclose.m
│   │   ├── adiosclosec.c
│   │   ├── adiosload.m
│   │   ├── adiosopen.m
│   │   ├── adiosopenc.c
│   │   ├── adiosread.m
│   │   ├── adiosreadc.c
│   │   ├── HOWTO-debug.txt
│   │   ├── Makefile
│   │   └── README.txt
│   ├── Python/
│   │   ├── test/
│   │   │   ├── __init__.py
│   │   │   └── simple_read_write.py
│   │   ├── __init__.py.in
│   │   ├── CMakeLists.txt
│   │   ├── py11ADIOS.cpp
│   │   ├── py11ADIOS.h
│   │   ├── py11ADIOSMPI.cpp
│   │   ├── py11Attribute.cpp
│   │   ├── py11Attribute.h
│   │   ├── py11Engine.cpp
│   │   ├── py11Engine.h
│   │   ├── py11glue.cpp
│   │   ├── py11IO.cpp
│   │   ├── py11IO.h
│   │   ├── py11IOMPI.cpp
│   │   ├── py11Operator.cpp
│   │   ├── py11Operator.h
│   │   ├── py11Query.cpp
│   │   ├── py11Query.h
│   │   ├── py11types.h
│   │   ├── py11Variable.cpp
│   │   ├── py11Variable.h
│   │   ├── py11VariableDerived.cpp
│   │   ├── py11VariableDerived.h
│   │   └── usercustomize.py.in
│   └── CMakeLists.txt
├── cmake/
│   ├── install/
│   │   ├── packaging/
│   │   │   └── CMakeLists.txt
│   │   ├── post/
│   │   │   ├── adios2-config-dummy/
│   │   │   ├── adios2-config.post.sh.in
│   │   │   ├── adios2-config.pre.sh.in
│   │   │   ├── CMakeLists.txt
│   │   │   └── generate-adios2-config.sh.in
│   │   └── pre/
│   │       └── CMakeLists.txt
│   ├── Internal/
│   │   └── FloatRepresentationTable.cmake
│   ├── upstream/
│   │   ├── FindMPI/
│   │   │   ├── fortranparam_mpi.f90.in
│   │   │   ├── libver_mpi.c
│   │   │   ├── libver_mpi.f90.in
│   │   │   ├── mpiver.f90.in
│   │   │   ├── test_mpi.c
│   │   │   └── test_mpi.f90.in
│   │   ├── FindPython/
│   │   │   └── Support.cmake
│   │   ├── CMakeFindDependencyMacro.cmake
│   │   ├── FindBZip2.cmake
│   │   ├── FindHDF5.cmake
│   │   ├── FindMPI.cmake
│   │   ├── FindPkgConfig.cmake
│   │   ├── FindPython.cmake
│   │   └── GoogleTest.cmake
│   ├── adios2-config-common.cmake.in
│   ├── adios2-config-install.cmake.in
│   ├── adios2-config.cmake.in
│   ├── ADIOSBisonFlexSub.cmake
│   ├── ADIOSFunctions.cmake
│   ├── check_libfabric_cxi.c
│   ├── CheckTypeRepresentation.cmake
│   ├── CheckTypeRepresentationCompile.c.in
│   ├── CheckTypeRepresentationCompile.f.in
│   ├── CheckTypeRepresentationRun.c.in
│   ├── CMakeFindDependencyMacro.cmake
│   ├── DetectOptions.cmake
│   ├── EmptyDir.cmake
│   ├── FindBZip2.cmake
│   ├── FindCaliper.cmake
│   ├── FindCrayDRC.cmake
│   ├── FindDAOS.cmake
│   ├── FindDataSpaces.cmake
│   ├── FindHDF5.cmake
│   ├── FindIME.cmake
│   ├── FindLIBFABRIC.cmake
│   ├── FindMPI.cmake
│   ├── FindPkgConfig.cmake
│   ├── Findpugixml.cmake
│   ├── FindPython.cmake
│   ├── FindPythonModule.cmake
│   ├── FindSodium.cmake
│   ├── FindSZ.cmake
│   ├── FindUCX.cmake
│   ├── FindZeroMQ.cmake
│   ├── GoogleTest.cmake
│   └── SSTFunctions.cmake
├── developer_docs/
│   ├── bp5format.md
│   └── bp5reader.md
├── docs/
│   ├── api_doxygen/
│   │   ├── C/
│   │   │   └── Doxyfile
│   │   └── CXX/
... (truncated)
```

## File Statistics

- **Files Processed:** 500
- **Files Skipped:** 1


## README

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Documentation](https://readthedocs.org/projects/adios2/badge/?version=latest)](https://adios2.readthedocs.io/en/latest/?badge=latest)
[![Circle CI](https://circleci.com/gh/ornladios/ADIOS2.svg?style=shield)](https://circleci.com/gh/ornladios/ADIOS2)
[![GitHub release](https://img.shields.io/github/release/ornladios/adios2/all.svg)]()
[![latest packaged version(s)](https://repology.org/badge/latest-versions/adios2.svg)](https://repology.org/project/adios2/versions)
[![OpenSSF Scorecard](https://api.scorecard.dev/projects/github.com/ornladios/ADIOS2/badge)](https://scorecard.dev/viewer/?uri=github.com/ornladios/ADIOS2)
[![OpenSSF Best Practices](https://www.bestpractices.dev/projects/11410/badge)](https://www.bestpractices.dev/projects/11410)

# ADIOS2 : The Adaptable Input Output System version 2

This is ADIOS2: The Adaptable Input/Output (I/O) System.

ADIOS2 is developed as part of the United States Department of Energy's Exascale Computing Project.
It is a framework for scientific data I/O to publish and subscribe to data when and where required.

ADIOS2 transports data as groups of self-describing variables and attributes across different media types (such as files, wide-area-networks, and remote direct memory access) using a common application programming interface for all transport modes.
ADIOS2 can be used on supercomputers, cloud systems, and personal computers.

ADIOS2 focuses on:

1. **Performance** I/O scalability in high performance computing (HPC) applications.
2. **Adaptability** unified interfaces to allow for several modes of transport (files, memory-to-memory)
3. **Ease of Use** two-level application programming interface (APIs)
* Full APIs for HPC applications: C++11, Fortran 90, C 99, Python 2 and 3
* Simplified High-Level APIs for data analysis: Python 2 and 3, C++11, Matlab

In addition, ADIOS2 APIs are based on:

* **MPI** Although ADIOS2 is MPI-based, it can also be used in non-MPI serial code.

* **Data Groups** ADIOS2 favors a deferred/prefetch/grouped variables transport mode by default to maximize data-per-request ratios.
Sync mode, one variable at a time, is treated as the special case.

* **Data Steps** ADIOS2 follows the actual production/consumption of data using an I/O “steps” abstraction removing the need to manage extra indexing information.

* **Data Engines** ADIOS2 Engine abstraction allows for reusing the APIs for different transport modes removing the need for drastic code changes.

## Documentation

Documentation is hosted at [readthedocs](https://adios2.readthedocs.io).

## Citing

If you find ADIOS2 useful, please cite our [SoftwareX paper](https://doi.org/10.1016/j.softx.2020.100561), which also gives a high-level overview to the motivation and goals of ADIOS; complementing the documentation.

## Getting ADIOS2

* From packages, please find packages information below at the packages section.
* From source: [Install ADIOS2 documentation](https://adios2.readthedocs.io/en/latest/setting_up/setting_up.html#).
  - For a `cmake` configuration example see [scripts/runconf/runconf.sh](https://github.com/ornladios/ADIOS2/blob/master/scripts/runconf/runconf.sh)
  - Once ADIOS2 is installed refer to: [Linking ADIOS2](https://adios2.readthedocs.io/en/latest/setting_up/setting_up.html#linking-adios-2)

## Releases

* Latest release: [v2.11.0](https://github.com/ornladios/ADIOS2/releases/tag/v2.11.0)
* Previous releases: [https://github.com/ornladios/ADIOS2/releases](https://github.com/ornladios/ADIOS2/releases)

## Packages

| Platform            | Package                                                                                                                                                    |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Summary             | [![latest packaged version(s)](https://repology.org/badge/latest-versions/adios2.svg)](https://repology.org/project/adios2/versions)                       |
| Conda               | [![Conda Version](https://img.shields.io/conda/v/conda-forge/libadios2)](https://anaconda.org/conda-forge/adios2)                                            |
| Spack               | [![Spack package](https://repology.org/badge/version-for-repo/spack/adios2.svg)](https://repology.org/project/adios2/versions)                             |
| Homebrew            | [![Homebrew package](https://repology.org/badge/version-for-repo/homebrew/adios2.svg)](https://repology.org/project/adios2/versions)                       |
| Ubuntu 24.04        | [![Ubuntu 24.04 package](https://repology.org/badge/version-for-repo/ubuntu_24_04/adios2.svg)](https://repology.org/project/adios2/versions)               |
| Debian 13           | [![Debian 13 package](https://repology.org/badge/version-for-repo/debian_13/adios2.svg)](https://repology.org/project/adios2/versions)                     |
| Debian Unstable     | [![Debian Unstable package](https://repology.org/badge/version-for-repo/debian_unstable/adios2.svg)](https://repology.org/project/adios2/versions)         |
| OpenSUSE TumbleWeed | [![openSUSE Tumbleweed package](https://repology.org/badge/version-for-repo/opensuse_tumbleweed/adios2.svg)](https://repology.org/project/adios2/versions) |
| OpenSUSE Leap 15.6  | [![openSUSE Leap 15.6 package](https://repology.org/badge/version-for-repo/opensuse_leap_15_6/adios2.svg)](https://repology.org/project/adios2/versions)   |
| vcpkg               | [![Vcpkg package](https://repology.org/badge/version-for-repo/vcpkg/adios2.svg)](https://repology.org/project/adios2/versions)                             |
| Dockerhub           | ![Docker Image Version](https://img.shields.io/docker/v/ornladios/adios2)                                                                                  |

## Community

ADIOS2 is an open source project: Questions, discussion, and contributions are welcome. Join us at:

- Mailing list: adios-ecp@kitware.com
- Github Discussions: https://github.com/ornladios/ADIOS2/discussions

## Reporting Bugs

If you find a bug, please open an [issue on ADIOS2 github repository](https://github.com/ornladios/ADIOS2/issues)

## Contributing

See the [Contributor's Guide to ADIOS 2](Contributing.md) for instructions on how to contribute.

## License
ADIOS2 is licensed under the Apache License v2.0.
See the accompanying [Copyright.txt](Copyright.txt) for more details.

## Directory layout

* bindings - public application programming interface, API, language bindings (C++11, C, Fortran, Python and Matlab)

* cmake - Project specific CMake modules

* examples - Simple set of examples in different languages

* scripts - Project maintenance and development scripts

* source - Internal source code for private components
* adios2 - source directory for the ADIOS2 library to be installed under install-dir/lib/libadios2.
* utils  - source directory for the binary utilities, to be installed under install-dir/bin

* testing - Tests using [gtest](https://github.com/google/googletest)


## Source Files

Source code files are processed separately by the processor.
File list:

- `bindings/Matlab/README.txt` (1,976 bytes)
- `docs/README.md` (1,165 bytes)
- `examples/ReadMe.md` (1,093 bytes)
- `examples/basics/ReadMe.md` (1,916 bytes)
- `examples/basics/queryWorker/ReadMe.md` (389 bytes)
- `examples/hello/ReadMe.md` (4,558 bytes)
- `examples/plugins/ReadMe.md` (662 bytes)
- `examples/simulations/GrayScott.jl/ReadMe.md` (6,086 bytes)
- `examples/simulations/ReadMe.md` (1,973 bytes)
- `examples/simulations/gray-scott-kokkos/ReadMe.md` (383 bytes)
- `examples/simulations/gray-scott-struct/ReadMe.md` (7,310 bytes)
- `examples/simulations/gray-scott/ReadMe.md` (8,082 bytes)
- `examples/simulations/heatTransfer/ReadMe.md` (2,987 bytes)
- `examples/simulations/korteweg-de-vries/ReadMe.md` (677 bytes)
- `examples/simulations/lorenz_ode/ReadMe.md` (1,388 bytes)
- `examples/useCases/ReadMe.md` (754 bytes)
- `examples/useCases/fidesOneCell/ReadMe.md` (1,949 bytes)
- `source/utils/profiler/ReadMe.md` (454 bytes)
- `source/utils/profiler_simplified/ReadMe.md` (1,697 bytes)
- `testing/adios2/engine/staging-common/README.md` (6,276 bytes)
- `testing/adios2/performance/metadata/README` (1,375 bytes)
- `thirdparty/EVPath/EVPath/mtests/README` (29 bytes)
- `thirdparty/EVPath/EVPath/rtests/README` (55 bytes)
- `thirdparty/EVPath/EVPath/tests/README` (33 bytes)
- `thirdparty/EVPath/EVPath/zpl-enet/README.md` (6,305 bytes)
- `thirdparty/EVPath/Readme.txt` (239 bytes)
- `thirdparty/GTest/Readme.txt` (248 bytes)
- `thirdparty/GTest/googletest/README.md` (5,814 bytes)
- `thirdparty/GTest/googletest/googlemock/README.md` (1,538 bytes)
- `thirdparty/GTest/googletest/googlemock/docs/README.md` (139 bytes)
- `thirdparty/GTest/googletest/googlemock/include/gmock/internal/custom/README.md` (510 bytes)
- `thirdparty/GTest/googletest/googletest/README.md` (8,961 bytes)
- `thirdparty/GTest/googletest/googletest/docs/README.md` (139 bytes)
- `thirdparty/GTest/googletest/googletest/include/gtest/internal/custom/README.md` (1,269 bytes)
- `thirdparty/KWSys/Readme.txt` (240 bytes)
- `thirdparty/KWSys/adios2sys/README.rst` (1,052 bytes)
- `thirdparty/atl/Readme.txt` (234 bytes)
- `thirdparty/dill/Readme.txt` (233 bytes)
- `thirdparty/enet/Readme.txt` (233 bytes)
- `thirdparty/enet/enet/README` (311 bytes)
- `thirdparty/ffs/Readme.txt` (230 bytes)
- `thirdparty/mingw-w64/Readme.txt` (238 bytes)
- `thirdparty/nlohmann_json/Readme.txt` (249 bytes)
- `thirdparty/perfstubs/Readme.txt` (244 bytes)
- `thirdparty/perfstubs/perfstubs/README.md` (685 bytes)
- `thirdparty/perfstubs/perfstubs/perfstubs_api/README.md` (5,369 bytes)
- `thirdparty/pugixml/Readme.txt` (235 bytes)
- `thirdparty/pybind11/Readme.txt` (273 bytes)
- `thirdparty/yaml-cpp/Readme.txt` (275 bytes)
- `.gitignore` (571 bytes)
- ... and 449 more files

## Skipped Files

The following files were skipped due to size limits:

- `examples/simulations/gray-scott-kokkos/json.hpp` (File too large (705,920 bytes))
