# hdf5

> Official HDF5® Library Repository

## Repository Info

- **Stars:** 878
- **Forks:** 327
- **Language:** C
- **License:** Other
- **Topics:** c, cpp, database, fortran, hdf, hdf5, java, library, nosql
- **Source:** `https://github.com/HDFGroup/hdf5`
- **Branch:** `develop`
- **Commit:** `9af6db11b688`
- **Last Commit:** 2026-01-22 16:14:20 -0600
- **Commits:** 1
- **Extracted:** 2026-01-22T17:54:02.715823


## Directory Structure

```
hdf5/
├── .devcontainer/
│   ├── devcontainer.json
│   ├── Dockerfile
│   └── noop.txt
├── .github/
│   ├── .well-known/
│   │   ├── funding-manifest-urls
│   │   └── funding.json
│   ├── actions/
│   │   └── setup-jextract/
│   │       └── action.yml
│   ├── ISSUE_TEMPLATE/
│   │   ├── blank-issue.md
│   │   ├── bug_report.md
│   │   ├── config.yml
│   │   └── feature-request.md
│   ├── PULL_REQUEST_TEMPLATE/
│   │   └── pull_request_template.md
│   ├── scripts/
│   │   ├── generate-index-html.sh
│   │   ├── test-java-implementations.sh
│   │   ├── test-maven-consumer.sh
│   │   └── validate-maven-artifacts.sh
│   ├── workflows/
│   │   ├── abi-report.yml
│   │   ├── analysis.yml
│   │   ├── aocc.yml
│   │   ├── arm-main.yml
│   │   ├── bintest.yml
│   │   ├── build-aws-c-s3.yml
│   │   ├── build_mpich_source.yml
│   │   ├── build_openmpi_source.yml
│   │   ├── call-workflows.yml
│   │   ├── clang-format-check.yml
│   │   ├── clang-format-fix.yml
│   │   ├── codeql.yml
│   │   ├── codespell.yml
│   │   ├── cross-compile.yml
│   │   ├── ctest.yml
│   │   ├── cve.yml
│   │   ├── cygwin.yml
│   │   ├── daily-build.yml
│   │   ├── daily-schedule.yml
│   │   ├── dev.yml
│   │   ├── freebsd.yml
│   │   ├── h5py.yml
│   │   ├── hdfeos5.yml
│   │   ├── i386.yml
│   │   ├── intel.yml
│   │   ├── java-examples-maven-test.yml
│   │   ├── java-implementation-test.yml
│   │   ├── julia.yml
│   │   ├── linkchecker.yml
│   │   ├── macos-26-matrix.yml
│   │   ├── main-par-spc.yml
│   │   ├── main-par.yml
│   │   ├── main-spc.yml
│   │   ├── main-static.yml
│   │   ├── main.yml
│   │   ├── markdown-link-check.yml
│   │   ├── markdown_config.json
│   │   ├── maven-build-test.yml
│   │   ├── maven-deploy.yml
│   │   ├── maven-staging.yml
│   │   ├── msys2.yml
│   │   ├── netcdf.yml
│   │   ├── nvhpc.yml
│   │   ├── openbsd.yml
│   │   ├── par-script.yml
│   │   ├── par-source.yml
│   │   ├── publish-branch.yml
│   │   ├── publish-release.yml
│   │   ├── README.md
│   │   ├── release-files.yml
│   │   ├── release.yml
│   │   ├── remove-files.yml
│   │   ├── scorecard.yml
│   │   ├── script.yml
│   │   ├── tarball.yml
│   │   ├── test-binary-installation.yml
│   │   ├── test-maven-deployment.yml
│   │   ├── test-maven-packages.yml
│   │   ├── testxpr.yml
│   │   ├── update-badge.sh
│   │   ├── update-progress.py
│   │   ├── update-progress.yml
│   │   ├── vfd-main.yml
│   │   ├── vfd-ros3.yml
│   │   ├── vfd-subfiling.yml
│   │   ├── vfd.yml
│   │   ├── vol.yml
│   │   ├── vol_adios2.yml
│   │   ├── vol_async.yml
│   │   ├── vol_cache.yml
│   │   ├── vol_ext_passthru.yml
│   │   ├── vol_log.yml
│   │   └── vol_rest.yml
│   ├── CODEOWNERS
│   ├── dependabot.yml
│   └── FUNDING.yml
├── bin/
│   ├── batch/
│   │   ├── ctest.qsub.in.cmake
│   │   ├── ctest_parallel.cmake.in
│   │   ├── ctest_serial.cmake.in
│   │   ├── ctestP.lsf.in.cmake
│   │   ├── ctestP.sl.in.cmake
│   │   ├── ctestS.lsf.in.cmake
│   │   ├── ctestS.sl.in.cmake
│   │   ├── ray_ctestP.lsf.in.cmake
│   │   ├── ray_ctestS.lsf.in.cmake
│   │   └── raybsub
│   ├── pkgscrpts/
│   │   └── h5rmflags
│   ├── checkapi
│   ├── chkcopyright
│   ├── debug-ohdr
│   ├── format_source
│   ├── genparser
│   ├── iostats
│   ├── make_err
│   ├── make_overflow
│   ├── make_vers
│   ├── output_filter.sh
│   ├── process_source.sh
│   ├── README.md
│   ├── release
│   ├── runbkgprog
│   ├── trace
│   └── warnhist
├── c++/
│   ├── src/
│   │   ├── header_files/
│   │   │   ├── filelist.xml
│   │   │   ├── hdf_logo.jpg
│   │   │   ├── help.jpg
│   │   │   ├── image001.jpg
│   │   │   └── image002.jpg
│   │   ├── C2Cppfunction_map.htm
│   │   ├── CMakeLists.txt
│   │   ├── H5AbstractDs.cpp
│   │   ├── H5AbstractDs.h
│   │   ├── H5Alltypes.h
│   │   ├── H5ArrayType.cpp
│   │   ├── H5ArrayType.h
│   │   ├── H5AtomType.cpp
│   │   ├── H5AtomType.h
│   │   ├── H5Attribute.cpp
│   │   ├── H5Attribute.h
│   │   ├── H5Classes.h
│   │   ├── H5CommonFG.cpp
│   │   ├── H5CommonFG.h
│   │   ├── H5CompType.cpp
│   │   ├── H5CompType.h
│   │   ├── H5Cpp.h
│   │   ├── H5DaccProp.cpp
│   │   ├── H5DaccProp.h
│   │   ├── H5DataSet.cpp
│   │   ├── H5DataSet.h
│   │   ├── H5DataSpace.cpp
│   │   ├── H5DataSpace.h
│   │   ├── H5DataType.cpp
│   │   ├── H5DataType.h
│   │   ├── H5DcreatProp.cpp
│   │   ├── H5DcreatProp.h
│   │   ├── H5DxferProp.cpp
│   │   ├── H5DxferProp.h
│   │   ├── H5EnumType.cpp
│   │   ├── H5EnumType.h
│   │   ├── H5Exception.cpp
│   │   ├── H5Exception.h
│   │   ├── H5FaccProp.cpp
│   │   ├── H5FaccProp.h
│   │   ├── H5FcreatProp.cpp
│   │   ├── H5FcreatProp.h
│   │   ├── H5File.cpp
│   │   ├── H5File.h
│   │   ├── H5FloatType.cpp
│   │   ├── H5FloatType.h
│   │   ├── H5Group.cpp
│   │   ├── H5Group.h
│   │   ├── H5IdComponent.cpp
│   │   ├── H5IdComponent.h
│   │   ├── H5Include.h
│   │   ├── H5IntType.cpp
│   │   ├── H5IntType.h
│   │   ├── H5LaccProp.cpp
│   │   ├── H5LaccProp.h
│   │   ├── H5LcreatProp.cpp
│   │   ├── H5LcreatProp.h
│   │   ├── H5Library.cpp
│   │   ├── H5Library.h
│   │   ├── H5Location.cpp
│   │   ├── H5Location.h
│   │   ├── H5Object.cpp
│   │   ├── H5Object.h
│   │   ├── H5OcreatProp.cpp
│   │   ├── H5OcreatProp.h
│   │   ├── H5PredType.cpp
... (truncated)
```

## File Statistics

- **Files Processed:** 2808
- **Files Skipped:** 13


## README

<div align="center">

![HDF5 Logo][u3]

[![BSD](https://img.shields.io/badge/License-BSD-blue.svg)](https://github.com/HDFGroup/hdf5/blob/develop/LICENSE)
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.17808614-blue)](https://doi.org/10.5281/zenodo.17808614)
[![develop cmake build status](https://img.shields.io/github/actions/workflow/status/HDFGroup/hdf5/call-workflows.yml?branch=develop&label=CMake%20CI)](https://github.com/HDFGroup/hdf5/actions/workflows/call-workflows.yml?query=branch%3Adevelop)

</div>

---

## What is HDF5?

This repository contains a high-performance library's source code and a file format
specification that implements the HDF5® data model. The model has been adopted across
many industries, and this implementation has become a de facto data management standard
in science, engineering, and research communities worldwide.

The HDF Group is the developer, maintainer, and steward of HDF5 software. Find more
information about The HDF Group, the HDF5 Community, and other HDF5 software projects,
tools, and services at [The HDF Group's website](https://www.hdfgroup.org/).

## Quick Start

- **New to HDF5?** Start with the [INSTALL](release_docs/INSTALL) guide for compilation and installation instructions.

- **Ready to build?** See [INSTALL_CMake.txt](release_docs/INSTALL_CMake.txt) for CMake-based builds.

- **Running on HPC?** Check out [README_HPC.md](release_docs/README_HPC.md) for parallel HDF5 configuration.

## Table of Contents

- [What is HDF5?](#what-is-hdf5)
- [Quick Start](#quick-start)
- [Documentation](#documentation)
- [Help and Support](#help-and-support)
- [Forum and News](#forum-and-news)
- [Release Schedule](#release-schedule)
- [Downloads and Source Code](#downloads-and-source-code)
- [Java Maven Artifacts](#java-maven-artifacts)
- [Contributing](#contributing)
- [How to Cite HDF5](#how-to-cite-hdf5)
- [Build Status](#build-status)

## Documentation

Documentation for all HDF software is available at:
- **All HDF Documentation**: https://support.hdfgroup.org/documentation/index.html
- **Latest HDF5 Library**: https://support.hdfgroup.org/documentation/hdf5/latest

See the [CHANGELOG.md][u1] file in the [release_docs/][u4] directory for information specific
to the features and updates included in this release of the library.

### Platform-Specific Guides

Several files in the [release_docs/][u4] directory provide platform-specific details:

| File | Description |
|------|-------------|
| [INSTALL](release_docs/INSTALL) | General compilation and installation instructions (start here) |
| [INSTALL_CMake.txt](release_docs/INSTALL_CMake.txt) | Building with CMake |
| [README_HPC.md](release_docs/README_HPC.md) | Building and configuring Parallel HDF5 on HPC systems |
| [INSTALL_Windows.txt](release_docs/INSTALL_Windows.txt) | Windows installation |
| [INSTALL_Cygwin.txt](release_docs/INSTALL_Cygwin.txt) | Cygwin installation |
| [USING_HDF5_CMake.txt](release_docs/USING_HDF5_CMake.txt) | Building HDF5 applications with CMake |
| [USING_CMake_Examples.txt](release_docs/USING_CMake_Examples.txt) | Building and testing HDF5 examples with CMake |

## Help and Support

The HDF Group staffs a free Help Desk accessible at https://help.hdfgroup.org and also monitors the [Forum](https://forum.hdfgroup.org). Our free support service is community-based and handled as time allows. We'll do our best to respond to your question as soon as possible, but please note that response times may vary depending on the complexity of the issue and staff availability.

If you're interested in guaranteed response and resolution times, a dedicated technical account manager, and more benefits (all while supporting the open-source work of The HDF Group), please check out [Priority Support](https://www.hdfgroup.org/solutions/priority-support/).

## Forum and News

The [HDF Forum](https://forum.hdfgroup.org) is provided for public announcements, technical questions, and discussions
of interest to the general HDF5 Community.

- [News and Announcements](https://forum.hdfgroup.org/c/news-and-announcements-from-the-hdf-group)
- [HDF5 Topics](https://forum.hdfgroup.org/c/hdf5)

These forums are provided as an open and public service for searching and reading.
Posting requires completing a simple registration and allows one to join in the
conversation. Please read the [quickstart guide](https://forum.hdfgroup.org/t/quickstart-guide-welcome-to-the-new-hdf-forum) for more information on how to get started.

## Release Schedule

![HDF5 release schedule][u2]

HDF5 does not follow a regular release schedule. Instead, updates are based on the
introduction of new features and the resolution of bugs. However, we aim to have at
least one annual release for each maintenance branch.

### Release Progress

[![Release Blockers](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/HDFGroup-Bot/0ad2eabb63b28eb90d69f5e5b2c1496f/raw/release-blocker-hdf5.json)](https://github.com/orgs/HDFGroup/projects/39/views/24)

[![Release Must Do](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/HDFGroup-Bot/0ad2eabb63b28eb90d69f5e5b2c1496f/raw/release-mustdo-hdf5.json)](https://github.com/orgs/HDFGroup/projects/39/views/24)

[![Release Nice to Have](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/HDFGroup-Bot/0ad2eabb63b28eb90d69f5e5b2c1496f/raw/release-nicetohave-hdf5.json)](https://github.com/orgs/HDFGroup/projects/39/views/24)

The badges above show the current progress of **release-blocking**, **must-do**, and **nice-to-have** issues with colors that reflect completion status:

- 🟢 **Green (90%+)**: Readying for Deployment - most issues completed
- 🟡 **Yellow (60-89%)**: Nearing Completion - on track for release
- 🟠 **Orange (40-59%)**: In Development - attention needed
- 🔴 **Red (<40%)**: Initial Phase - significant issues remain

Click the badges to view the detailed project board with current release items.

## Downloads and Source Code

### Snapshots and Releases

- **Development Snapshots**: https://github.com/HDFGroup/hdf5/releases/tag/snapshot
- **Latest Release**: https://github.com/HDFGroup/hdf5/releases
- **Previous Releases**: https://support.hdfgroup.org/archive/support/ftp/HDF5/releases/index.html
- **Development Code**: https://github.com/HDFGroup/hdf5.git

### HPC Testing Results

[View HPC configure/build/test results on CDash](https://my.cdash.org/index.php?project=HDF5)

## Java Maven Artifacts

HDF5 Java bindings and examples are available as Maven artifacts. For detailed usage instructions including dependency configuration, repository setup, and platform-specific builds, see [HDF5Examples/JAVA/README-MAVEN.md](HDF5Examples/JAVA/README-MAVEN.md).

## Contributing

We welcome contributions to HDF5! Whether you're fixing bugs, adding features, or improving documentation, your help is appreciated.

### How to Contribute

1. **Report Issues**: Use our [GitHub Issues](https://github.com/HDFGroup/hdf5/issues) to report bugs or request features
2. **Submit Pull Requests**: Fork the repository, make your changes, and submit a PR
3. **Join Discussions**: Participate in the [HDF Forum](https://forum.hdfgroup.org)

For detailed contribution guidelines, please contact us through the [Help Desk](https://help.hdfgroup.org).

## How to Cite HDF5

If you use HDF5 in your research, please cite it. This repository includes a [`CITATION.cff`](CITATION.cff) file containing standard citation metadata.

**Quick DOI:** [10.5281/zenodo.17808614](https://doi.org/10.5281/zenodo.17808614)

## Build Status

<details>
<summary>Click to expand detailed build status</summary>

### Continuous Integration

[![HDF5 develop daily build status](https://img.shields.io/github/actions/workflow/status/HDFGroup/hdf5/daily-schedule.yml?branch=develop&label=Daily%20Build)](https://github.com/HDFGroup/hdf5/actions/workflows/daily-schedule.yml?query=branch%3Adevelop)
[![CVE regression](https://img.shields.io/github/actions/workflow/status/HDFGroup/hdf5/cve.yml?branch=develop&label=CVE%20Tests)](https://github.com/HDFGroup/hdf5/actions/workflows/cve.yml?query=branch%3Adevelop)
[![OSS-Fuzz Status](https://oss-fuzz-build-logs.storage.googleapis.com/badges/hdf5.svg)](https://oss-fuzz-build-logs.storage.googleapis.com/index.html#hdf5)
[![Link Checker Status](https://github.com/HDFGroup/hdf5/actions/workflows/linkchecker.yml/badge.svg)](https://github.com/HDFGroup/hdf5/actions/workflows/linkchecker.yml)

### Integration Testing

[![HDF-EOS5 build status](https://img.shields.io/github/actions/workflow/status/HDFGroup/hdf5/hdfeos5.yml?branch=develop&label=HDF-EOS5)](https://github.com/HDFGroup/hdf5/actions/workflows/hdfeos5.yml?query=branch%3Adevelop)
[![netCDF build status](https://img.shields.io/github/actions/workflow/status/HDFGroup/hdf5/netcdf.yml?branch=develop&label=netCDF)](https://github.com/HDFGroup/hdf5/actions/workflows/netcdf.yml?query=branch%3Adevelop)
[![h5py build status](https://img.shields.io/github/actions/workflow/status/HDFGroup/hdf5/h5py.yml?branch=develop&label=h5py)](https://github.com/HDFGroup/hdf5/actions/workflows/h5py.yml?query=branch%3Adevelop)

### VOL and VFD Testing

[![HDF5 VOL connectors build status](https://img.shields.io/github/actions/workflow/status/HDFGroup/hdf5/vol.yml?branch=develop&label=VOL%20Connectors)](https://github.com/HDFGroup/hdf5/actions/workflows/vol.yml?query=branch%3Adevelop)
[![HDF5 VFD build status](https://img.shields.io/github/actions/workflow/status/HDFGroup/hdf5/vfd.yml?branch=develop&label=VFD%20Tests)](https://github.com/HDFGroup/hdf5/actions/workflows/vfd.yml?query=branch%3Adevelop)

</details>

---

[u1]: https://github.com/HDFGroup/hdf5/blob/develop/release_docs/CHANGELOG.md
[u2]: https://github.com/HDFGroup/hdf5/blob/develop/release_docs/img/release-schedule.png
[u3]: https://github.com/HDFGroup/hdf5/blob/develop/doxygen/img/HDF5.png
[u4]: https://github.com/HDFGroup/hdf5/blob/develop/release_docs


## Source Files

Source code files are processed separately by the processor.
File list:

- `.github/workflows/README.md` (4,048 bytes)
- `HDF5Examples/C/TUTR/README` (1,091 bytes)
- `HDF5Examples/README.md` (3,391 bytes)
- `bin/README.md` (1,319 bytes)
- `config/README.md` (944 bytes)
- `config/sanitizer/README.md` (17,617 bytes)
- `fortran/src/README.md` (7,861 bytes)
- `release_docs/README.md` (6,209 bytes)
- `test/API/README.md` (4,767 bytes)
- `tools/test/h5repack/testfiles/README` (295 bytes)
- `HDF5Examples/JAVA/README-MAVEN.md` (6,213 bytes)
- `release_docs/README_HPC.md` (17,468 bytes)
- `.devcontainer/Dockerfile` (292 bytes)
- `.gitignore` (498 bytes)
- `CODE_OF_CONDUCT.md` (5,218 bytes)
- `CONTRIBUTING.md` (15,791 bytes)
- `HDF5Examples/JAVA/.gitignore` (301 bytes)
- `LICENSE` (5,848 bytes)
- `SECURITY.md` (670 bytes)
- `config/sanitizer/LICENSE` (10,140 bytes)
- `release_docs/CHANGELOG.md` (10,974 bytes)
- `.devcontainer/devcontainer.json` (674 bytes)
- `.devcontainer/noop.txt` (186 bytes)
- `.github/.well-known/funding.json` (12,586 bytes)
- `.github/FUNDING.yml` (64 bytes)
- `.github/ISSUE_TEMPLATE/blank-issue.md` (323 bytes)
- `.github/ISSUE_TEMPLATE/bug_report.md` (889 bytes)
- `.github/ISSUE_TEMPLATE/config.yml` (29 bytes)
- `.github/ISSUE_TEMPLATE/feature-request.md` (593 bytes)
- `.github/PULL_REQUEST_TEMPLATE/pull_request_template.md` (291 bytes)
- `.github/actions/setup-jextract/action.yml` (7,196 bytes)
- `.github/dependabot.yml` (186 bytes)
- `.github/scripts/generate-index-html.sh` (9,976 bytes)
- `.github/scripts/test-java-implementations.sh` (10,492 bytes)
- `.github/scripts/test-maven-consumer.sh` (3,655 bytes)
- `.github/scripts/validate-maven-artifacts.sh` (17,779 bytes)
- `.github/workflows/abi-report.yml` (9,019 bytes)
- `.github/workflows/analysis.yml` (20,913 bytes)
- `.github/workflows/aocc.yml` (4,598 bytes)
- `.github/workflows/arm-main.yml` (15,897 bytes)
- `.github/workflows/bintest.yml` (10,498 bytes)
- `.github/workflows/build-aws-c-s3.yml` (11,530 bytes)
- `.github/workflows/build_mpich_source.yml` (3,321 bytes)
- `.github/workflows/build_openmpi_source.yml` (3,023 bytes)
- `.github/workflows/call-workflows.yml` (8,864 bytes)
- `.github/workflows/clang-format-check.yml` (786 bytes)
- `.github/workflows/clang-format-fix.yml` (1,497 bytes)
- `.github/workflows/codeql.yml` (2,697 bytes)
- `.github/workflows/codespell.yml` (535 bytes)
- `.github/workflows/cross-compile.yml` (3,735 bytes)
- ... and 2757 more files

## Skipped Files

The following files were skipped due to size limits:

- `java/hdf/hdf5lib/H5.java` (File too large (910,676 bytes))
- `java/src-jni/hdf/hdf5lib/H5.java` (File too large (588,519 bytes))
- `src/H5Shyper.c` (File too large (551,092 bytes))
- `test/API/H5_api_dataset_test.c` (File too large (508,673 bytes))
- `test/API/H5_api_link_test.c` (File too large (1,145,249 bytes))
- `test/cache.c` (File too large (1,229,870 bytes))
- `test/dsets.c` (File too large (632,082 bytes))
- `test/fheap.c` (File too large (599,737 bytes))
- `test/links.c` (File too large (851,501 bytes))
- `test/objcopy.c` (File too large (576,605 bytes))
- `test/testfiles/t8.shakespeare.txt` (File too large (5,458,199 bytes))
- `test/tselect.c` (File too large (613,178 bytes))
- `tools/test/h5dump/h5dumpgentest.c` (File too large (523,175 bytes))
