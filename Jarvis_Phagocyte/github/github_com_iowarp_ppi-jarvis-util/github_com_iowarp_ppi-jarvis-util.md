# ppi-jarvis-util

> Utilities to aid with creating shell scripts within Python

## Repository Info

- **Stars:** 1
- **Forks:** 1
- **Language:** Python
- **License:** Other
- **Source:** `https://github.com/iowarp/ppi-jarvis-util`
- **Branch:** `main`
- **Commit:** `596655f835f0`
- **Last Commit:** 2025-09-30 09:41:50 -0500
- **Commits:** 1
- **Extracted:** 2026-01-22T18:43:23.257104


## Directory Structure

```
ppi-jarvis-util/
├── .github/
│   └── workflows/
│       └── main.yml
├── .vscode/
│   └── launch.json
├── bin/
│   ├── jarvis-imports
│   ├── pylsblk
│   ├── pymonitor
│   └── qr-code-generator.py
├── ci/
│   ├── cluster/
│   │   ├── docker-compose.yml
│   │   └── Dockerfile
│   ├── install_deps.sh
│   ├── install_jarvis.sh
│   ├── install_spack.sh
│   ├── lint.sh
│   └── run_tests.sh
├── example/
│   ├── basic_argparse.py
│   ├── boolean_spaghetti.py
│   ├── choices.py
│   ├── hostfile_test.py
│   ├── hostfile_threads_test.py
│   ├── menu_argparse.py
│   ├── remainder.py
│   └── remainder_kv.py
├── jarvis_util/
│   ├── introspect/
│   │   ├── __init__.py
│   │   ├── monitor.py
│   │   └── system_info.py
│   ├── serialize/
│   │   ├── __init__.py
│   │   ├── ini_file.py
│   │   ├── json_file.py
│   │   ├── pickle.py
│   │   ├── serializer.py
│   │   ├── text_file.py
│   │   └── yaml_file.py
│   ├── shell/
│   │   ├── __init__.py
│   │   ├── compile.py
│   │   ├── exec.py
│   │   ├── exec_info.py
│   │   ├── filesystem.py
│   │   ├── local_exec.py
│   │   ├── mpi_exec.py
│   │   ├── pbs_exec.py
│   │   ├── process.py
│   │   ├── pscp.py
│   │   ├── pssh_exec.py
│   │   ├── scp.py
│   │   ├── slurm_exec.py
│   │   ├── spark_exec.py
│   │   └── ssh_exec.py
│   ├── util/
│   │   ├── __init__.py
│   │   ├── argparse.py
│   │   ├── expand_env.py
│   │   ├── hostfile.py
│   │   ├── import_all.py
│   │   ├── import_mod.py
│   │   ├── logging.py
│   │   ├── naming.py
│   │   ├── size_conv.py
│   │   └── small_df.py
│   ├── __init__.py
│   └── jutil_manager.py
├── test/
│   └── unit/
│       ├── ares.yaml
│       ├── print5s.py
│       ├── printNone.py
│       ├── test_argparse.py
│       ├── test_hostfile.py
│       ├── test_hostfile.txt
│       ├── test_local_exec.py
│       ├── test_monitor.py
│       ├── test_mpi.py
│       ├── test_small_df.py
│       └── test_system_info.py
├── .coveragerc
├── .gitignore
├── LICENSE
├── None
├── pr.sh
├── pylintrc
├── README.md
├── requirements.txt
└── setup.py
```

## File Statistics

- **Files Processed:** 72
- **Files Skipped:** 0


## README

# PPI Jarvis Util

[![License: BSD-3-Clause](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![IoWarp](https://img.shields.io/badge/IoWarp-GitHub-blue.svg)](http://github.com/iowarp)
[![GRC](https://img.shields.io/badge/GRC-Website-blue.svg)](https://grc.iit.edu/)
[![Python](https://img.shields.io/badge/Python-3.7+-yellow.svg)](https://www.python.org/)

A Python library containing various utilities to aid with creating shell scripts within Python. This library provides wrappers for executing shell commands locally, SSH, SCP, MPI, argument parsing, and various other utilities.

## Purpose
PPI Jarvis Util simplifies the creation of shell scripts within Python by providing comprehensive wrappers for command execution, remote operations, and system management tasks. It enables seamless integration between Python applications and system-level operations.

## Dependencies

### Python Dependencies
- `pyyaml` - YAML parsing and generation
- `tabulate` - Pretty-print tabular data

## Installation

For now, we only consider manual installation
```bash
cd jarvis-util
python3 -m pip install -r requirements.txt
python3 -m pip install -e .
```

## Executing a program

The following code will execute a command on the local machine.
The output will NOT be collected into an in-memory buffer.
The output will be printed to the terminal as it occurs.

```python
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.local_exec import LocalExecInfo 

node = Exec('echo hello', LocalExecInfo(collect_output=False))
```

Programs can also be executed asynchronously:
```python
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.local_exec import LocalExecInfo 

node = Exec('echo hello', LocalExecInfo(collect_output=False,
                                        exec_async=True))
node.wait()
```

Various examples of outputs:
```python
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.local_exec import LocalExecInfo 

# Will ONLY print to the terminal
node = Exec('echo hello', LocalExecInfo(collect_output=False))
# Will collect AND print to the terminal
node = Exec('echo hello', LocalExecInfo(collect_output=True))
# Will collect BUT NOT print to the terminal
node = Exec('echo hello', LocalExecInfo(collect_output=True,
                                        hide_output=True))
# Will collect, pipe to file, and print to terminal
node = Exec('echo hello', LocalExecInfo(collect_output=True,
                                        pipe_stdout='/tmp/stdout.txt',
                                        pipe_stderr='/tmp/stderr.txt'))
```

This is useful if you have a program which runs using a daemon mode.

## Executing an MPI program

The following code will execute the "hostname" command on the local
machine 24 times using MPI.

```python
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.mpi_exec import MpiExecInfo 

node = Exec('hostname', MpiExecInfo(hostfile=None,
                                    nprocs=24,
                                    ppn=None,
                                    collect_output=False))
```

## Executing an SSH program

The following code will execute the "hostname" command on all machines
in the hostfile

```python
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.pssh_exec import PsshExecInfo 

node = Exec('hostname', PsshExecInfo(hostfile="/tmp/hostfile.txt",
                                     collect_output=False))
```

## The contents of a hostfile

A hostfile can have the following syntax:
```
ares-comp-01
ares-comp-[02-04]
ares-comp-[05-09,11,12-14]-40g
```

These will be expanded internally by PSSH and MPI.

## Project Structure

- `bin/` - Command-line utilities (pylsblk, pymonitor)
- `jarvis_util/` - Core Python library
  - `shell/` - Command execution wrappers (local, SSH, MPI, etc.)
  - `util/` - Utility modules (argparse, hostfile, logging, etc.)
  - `serialize/` - File serialization modules (YAML, JSON, INI, etc.)
  - `introspect/` - System monitoring and information modules
- `example/` - Usage examples and demonstrations
- `test/unit/` - Unit tests
- `ci/` - CI/CD configuration and Docker setup

# Contributing

We use the Google Python Style guide (pylintrc).

## License

BSD 3-Clause License

Copyright (c) 2024, Gnosis Research Center, Illinois Institute of Technology. See the [LICENSE](LICENSE) file for details.

## Support

For issues, questions, or contributions, please:
- Open an issue on the [GitHub repository](https://github.com/iowarp/ppi-jarvis-util)
- Contact the Gnosis Research Center at Illinois Institute of Technology


## Source Files

Source code files are processed separately by the processor.
File list:

- `.gitignore` (2,015 bytes)
- `LICENSE` (1,685 bytes)
- `ci/cluster/Dockerfile` (1,345 bytes)
- `ci/cluster/docker-compose.yml` (292 bytes)
- `requirements.txt` (83 bytes)
- `setup.py` (1,085 bytes)
- `.github/workflows/main.yml` (1,266 bytes)
- `.vscode/launch.json` (506 bytes)
- `bin/qr-code-generator.py` (1,830 bytes)
- `ci/install_deps.sh` (139 bytes)
- `ci/install_jarvis.sh` (83 bytes)
- `ci/install_spack.sh` (125 bytes)
- `ci/lint.sh` (39 bytes)
- `ci/run_tests.sh` (84 bytes)
- `example/basic_argparse.py` (1,435 bytes)
- `example/boolean_spaghetti.py` (627 bytes)
- `example/choices.py` (462 bytes)
- `example/hostfile_test.py` (699 bytes)
- `example/hostfile_threads_test.py` (879 bytes)
- `example/menu_argparse.py` (1,535 bytes)
- `example/remainder.py` (467 bytes)
- `example/remainder_kv.py` (514 bytes)
- `jarvis_util/__init__.py` (1,365 bytes)
- `jarvis_util/introspect/__init__.py` (0 bytes)
- `jarvis_util/introspect/monitor.py` (2,603 bytes)
- `jarvis_util/introspect/system_info.py` (36,456 bytes)
- `jarvis_util/jutil_manager.py` (825 bytes)
- `jarvis_util/serialize/__init__.py` (0 bytes)
- `jarvis_util/serialize/ini_file.py` (613 bytes)
- `jarvis_util/serialize/json_file.py` (627 bytes)
- `jarvis_util/serialize/pickle.py` (535 bytes)
- `jarvis_util/serialize/serializer.py` (397 bytes)
- `jarvis_util/serialize/text_file.py` (603 bytes)
- `jarvis_util/serialize/yaml_file.py` (770 bytes)
- `jarvis_util/shell/__init__.py` (0 bytes)
- `jarvis_util/shell/compile.py` (1,515 bytes)
- `jarvis_util/shell/exec.py` (2,275 bytes)
- `jarvis_util/shell/exec_info.py` (9,290 bytes)
- `jarvis_util/shell/filesystem.py` (19,990 bytes)
- `jarvis_util/shell/local_exec.py` (6,136 bytes)
- `jarvis_util/shell/mpi_exec.py` (5,397 bytes)
- `jarvis_util/shell/pbs_exec.py` (7,178 bytes)
- `jarvis_util/shell/process.py` (1,136 bytes)
- `jarvis_util/shell/pscp.py` (1,799 bytes)
- `jarvis_util/shell/pssh_exec.py` (2,139 bytes)
- `jarvis_util/shell/scp.py` (4,113 bytes)
- `jarvis_util/shell/slurm_exec.py` (10,173 bytes)
- `jarvis_util/shell/spark_exec.py` (1,122 bytes)
- `jarvis_util/shell/ssh_exec.py` (2,285 bytes)
- `jarvis_util/util/__init__.py` (0 bytes)
- ... and 21 more files
