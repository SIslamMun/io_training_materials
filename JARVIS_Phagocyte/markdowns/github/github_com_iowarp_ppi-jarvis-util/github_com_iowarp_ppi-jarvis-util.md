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
- **Extracted:** 2026-01-08T12:00:35.132717


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

### `.gitignore`

```
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class
.idea
hostfile.txt
lcov.info

# C extensions
*.so

# Distribution / packaging
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
pip-wheel-metadata/
share/python-wheels/
*.egg-info/
.installed.cfg
*.egg
MANIFEST

# PyInstaller
#  Usually these files are written by a python script from a template
#  before PyInstaller builds the exe, so as to inject date/other infos into it.
*.manifest
*.spec

# Installer logs
pip-log.txt
pip-delete-this-directory.txt

# Unit test / coverage reports
htmlcov/
.tox/
.nox/
.coverage
.coverage.*
.cache
nosetests.xml
coverage.xml
*.cover
*.py,cover
.hypothesis/
.pytest_cache/

# Translations
*.mo
*.pot

# Django stuff:
*.log
local_settings.py
db.sqlite3
db.sqlite3-journal

# Flask stuff:
instance/
.webassets-cache

# Scrapy stuff:
.scrapy

# Sphinx documentation
docs/_build/

# PyBuilder
target/

# Jupyter Notebook
.ipynb_checkpoints

# IPython
profile_default/
ipython_config.py

# pyenv
.python-version

# pipenv
#   According to pypa/pipenv#598, it is recommended to include Pipfile.lock in version control.
#   However, in case of collaboration, if having platform-specific dependencies or dependencies
#   having no cross-platform support, pipenv may install dependencies that don't work, or not
#   install all needed dependencies.
#Pipfile.lock

# PEP 582; used by e.g. github.com/David-OConnor/pyflow
__pypackages__/

# Celery stuff
celerybeat-schedule
celerybeat.pid

# SageMath parsed files
*.sage.py

# Environments
.env
.venv
env/
venv/
ENV/
env.bak/
venv.bak/

# Spyder project settings
.spyderproject
.spyproject

# Rope project settings
.ropeproject

# mkdocs documentation
/site

# mypy
.mypy_cache/
.dmypy.json
dmypy.json

# Pyre type checker
.pyre/
/.idea/jarvis-cd.iml
/.idea/misc.xml
/.idea/modules.xml
/.idea/inspectionProfiles/profiles_settings.xml
/.idea/inspectionProfiles/Project_Default.xml
/.idea/vcs.xml
/.idea/deployment.xml
```

### `LICENSE`

```
# BSD 3-Clause License

Copyright (c) 2024, Gnosis Research Center, Illinois Institute of Technology
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

---

**Contact Information:**
Gnosis Research Center  
Illinois Institute of Technology  
Email: grc@illinoistech.edu
```

### `ci/cluster/Dockerfile`

```dockerfile
# Install ubuntu 20.04
FROM ubuntu:20.04
LABEL maintainer="llogan@hawk.iit.edu"
LABEL version="0.0"
LABEL description="An example docker image"

# Disable Prompt During Packages Installation
ARG DEBIAN_FRONTEND=noninteractive

# Update ubuntu
RUN apt update && apt install

# Install some basic packages
RUN apt install -y \
    openssh-server \
    sudo git nano vim \
    docker \
    mpich \
    gcc \
    g++ \
    gfortran \
    libtool \
    libtool-bin \
    automake \
    autoconf

# Create a new user
RUN useradd -m sshuser
RUN usermod -aG sudo sshuser
RUN passwd -d sshuser

# Copy the host's SSH keys
# Docker requires COPY be relative to the current working
# directory. We cannot pass ~/.ssh/id_rsa unfortunately...
ENV SSHDIR=/home/sshuser/.ssh
RUN sudo -u sshuser mkdir ${SSHDIR}
COPY id_rsa ${SSHDIR}/id_rsa
COPY id_rsa.pub ${SSHDIR}/id_rsa.pub

# Authorize host SSH keys
RUN sudo -u sshuser touch ${SSHDIR}/authorized_keys
RUN cat ${SSHDIR}/id_rsa.pub >> ${SSHDIR}/authorized_keys

# Set SSH permissions
RUN chmod 700 ${SSHDIR}
RUN chmod 644 ${SSHDIR}/id_rsa.pub
RUN chmod 600 ${SSHDIR}/id_rsa
RUN chmod 600 ${SSHDIR}/authorized_keys

# Enable passwordless SSH
RUN sed -i 's/#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config

# Start SSHD and wait forever
RUN mkdir /run/sshd
CMD ["/usr/sbin/sshd", "-D"]
```

### `ci/cluster/docker-compose.yml`

```yaml
version: "3"

services:
  node1:
    build: .
    links:
      - node2
    networks:
      - net
    hostname: node1
    stdin_open: true
    tty: true

  node2:
    build: .
    networks:
      - net
    hostname: node2
    stdin_open: true
    tty: true

networks:
  net:
    driver: bridge
```

### `requirements.txt`

```
pyyaml
#pylint==2.15.0
#coverage==5.5
#coverage-lcov==0.2.4
#pytest==6.2.5
tabulate
```

### `setup.py`

```python
import setuptools

setuptools.setup(
    name="jarvis_util",
    version="0.0.1",
    scripts=['bin/pylsblk', 'bin/pymonitor'],
    description='Utilities to aid with creating shell scripts within Python.',
    long_description=open('README.md').read(),
    long_description_content_type='text/markdown',
    author="Luke Logan",
    author_email="llogan@hawk.iit.edu",
    url="https://github.com/scs-lab/jarvis-util",
    packages=setuptools.find_packages(),
    install_requires=[
        'pyyaml',
        # 'pylint==2.15.0',
        # 'coverage==5.5',
        # 'coverage-lcov==0.2.4',
        # 'pytest==6.2.5',
        'tabulate'
    ],
    classifiers=[
        "Programming Language :: Python",
        "Programming Language :: Python :: 3",
        "Development Status :: 0 - Pre-Alpha",
        "Environment :: Other Environment",
        "Intended Audience :: Developers",
        "License :: None",
        "Operating System :: OS Independent",
        "Topic :: Software Development :: Libraries :: Python Modules",
        "Topic :: Application Configuration",
    ],
)
```

### `.github/workflows/main.yml`

```yaml
name: GitHub Actions

on:
  # push:
  # pull_request:
  #   branches: [ main ]
  workflow_dispatch:
    inputs:
      debug_enabled:
        description: 'Run the build with tmate debugging enabled'
        required: false
        default: false
env:
  BUILD_TYPE: Debug
  LOCAL: local

jobs:
  build:
    runs-on: ubuntu-24.04
    steps:
      - name: Get Sources
        uses: actions/checkout@v4

      - name: Cache Spack packages
        uses: actions/cache@v3
        id: spack-cache
        with:
          path: |
            ~/spack
            ~/.spack
          key: ${{ runner.os }}-${{ hashFiles('ci/install_deps.sh') }}

      - name: Install APT Dependencies
        run: bash ci/install_deps.sh

      - name: Install Spack Dependencies
        if: steps.spack-cache.outputs.cache-hit != 'true'
        run: bash ci/install_spack.sh

      - name: Setup python
        uses: actions/setup-python@v4

      - name: Install Jarvis
        run: bash ci/install_jarvis.sh

      - name: Run pylint
        run: bash ci/lint.sh

      - name: Test
        run: bash ci/run_tests.sh

      - name: Coveralls
        uses: coverallsapp/github-action@master
        with:
          path-to-lcov: lcov.info
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

### `.vscode/launch.json`

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Debug jarvis rg build",
            "type": "python",
            "python": "/home/llogan/.venv/bin/python",
            "request": "launch",
            "program": "/home/llogan/.venv/bin/jarvis",
            "args": [
                "rg",
                "build"
            ],
            "console": "integratedTerminal",
            "justMyCode": false,
            "envFile": "${workspaceFolder}/.env"
        }
    ]
}
```

### `bin/qr-code-generator.py`

```python
import qrcode
from qrcode.image.styledpil import StyledPilImage
from qrcode.image.styles.moduledrawers.pil import RoundedModuleDrawer
from qrcode.image.svg import SvgPathImage 
from qrcode.image.styledpil import StyledPilImage
from qrcode.image.styles.colormasks import RadialGradiantColorMask
from PIL import Image
from PIL import ImageFilter

# from qrcode.image.styles.moduledrawers.pil import RoundedModuleDrawer
# from qrcode.image.styles.colormasks import RadialGradiantColorMask

qr = qrcode.QRCode(
    version=None,
    error_correction=qrcode.constants.ERROR_CORRECT_H,
    box_size=15,
    border=1,
)
# factory = SvgCircleDrawer
factory = StyledPilImage
# drawer=RoundedModuleDrawer
drawer=RadialGradiantColorMask
# factory = StyledPilImage
qr.add_data('https://grc.iit.edu/research/projects/hermes')
qr.make(fit=True)

# img = qr.make_image(image_factory=StyledPilImage, embeded_image_path="/home/neeraj/Downloads/GRC-Logo-Square-Black.png")
# img = qr.make_image(embeded_image_path="/home/neeraj/Downloads/GRC-Logo-Square-Black.png", back_color=(20,157,204), fill_color=(255, 255, 255), image_factory=factory)
# img_1 = qr.make_image(image_factory=StyledPilImage, module_drawer=RoundedModuleDrawer())
img = qr.make_image(embeded_image_path="/home/lukemartinlogan/Downloads/github-icon.png",
                    image_factory=factory,
                    embeded_image_resample=Image.LANCZOS,
                    color_mask=RadialGradiantColorMask(back_color=(255, 255, 255), edge_color=(20, 157, 204), center_color= (0,0,0) ),
                    # module_drawer=drawer(),
                    fill_color="#149dcc",
                    back_color="#ffffff",
                    )
# img = qr.make_image(embeded_image_path="/home/neeraj/Downloads/GRC-Logo-Square-Black.png", fill_color=(), )
img.save("hermes-git.png")
```

### `ci/install_deps.sh`

```bash
#!/bin/bash
sudo apt update
sudo apt install -y \
mpich \
gcc \
g++ \
gfortran \
libtool \
libtool-bin \
automake \
autoconf \
pylint
```

### `ci/install_jarvis.sh`

```bash
#!/bin/bash
python3 -m pip install -r requirements.txt
python3 -m pip install -e .
```

### `ci/install_spack.sh`

```bash
#!/bin/bash
sudo apt update
sudo apt install -y \
mpich \
gcc \
g++ \
gfortran \
libtool \
libtool-bin \
automake \
autoconf
```

### `ci/lint.sh`

```bash
#!/bin/bash
pylint "${PWD}"/jarvis_util
```

### `ci/run_tests.sh`

```bash
#!/bin/bash
coverage run -m pytest test
rm -rf "*.pyc"
coverage report
coverage-lcov
```

### `example/basic_argparse.py`

```python
from jarvis_util.util.argparse import ArgParse


class MyArgParse(ArgParse):
    def define_options(self):
        self.add_menu()
        self.add_args([
            {
                'name': 'hello',
                'msg': 'A message to print',
                'type': str,  # The type of this variable
                'required': True,  # This argument is required
                'pos': True,  # This is a positional argument
            },
            {
                'name': 'hello_optional',
                'msg': 'An optional message to print',
                'type': str,  # The type of the variable to produce
                'default': 'no optional message given',
                'required': False,  # This argument is not required
                'pos': True,  # This is a positional argument
            },
            {
                'name': 'hello_kwarg',
                'msg': 'An integer key-word argument to print',
                'type': int,  # The type of the variable
                'default': 0,
            },
        ])

    # When add_menu has no parameters, process_args will call this function
    def main_menu(self):
        # Parsed parameters are placed in self.kwargs
        print(self.kwargs['hello'])
        print(self.kwargs['hello_optional'])
        print(self.kwargs['hello_kwarg'])
        print(self.kwargs)
        print(self.real_kwargs)


args = MyArgParse()
args.process_args()
```

### `example/boolean_spaghetti.py`

```python
from jarvis_util.util.argparse import ArgParse


class MyArgParse(ArgParse):
    def define_options(self):
        self.add_menu('spaghetti')
        self.add_args([
            {
                'name': 'cheese',
                'msg': 'Whether to use cheese',
                'type': bool,  # The type of this variable
                'default': True
            }
        ])

    def spaghetti(self):
        if self.kwargs['cheese']:
            print('I will take the spaghetti with cheese')
        else:
            print('I want actual Italian, and will not take your cheese')


args = MyArgParse()
args.process_args()
```

### `example/choices.py`

```python
from jarvis_util.util.argparse import ArgParse


class MyArgParse(ArgParse):
    def define_options(self):
        self.add_menu()
        self.add_args([
            {
                'name': 'hi',
                'msg': 'hello',
                'type': str,
                'choices': ['a', 'b', 'c'],
                'default': None
            }
        ])

    def main_menu(self):
        print(self.kwargs['hi'])


args = MyArgParse()
args.process_args()
```

### `example/hostfile_test.py`

```python
from jarvis_util.util.argparse import ArgParse


class MyArgParse(ArgParse):
    def define_options(self):
        self.add_menu('vpic run',
                      keep_remainder=False)
        self.add_args([
            {
                'name': 'hosts',
                'msg': 'A list of hosts and threads pr',
                'type': list,
                'args': [
                    {
                        'name': 'host',
                        'msg': 'A string representing a host',
                        'type': str,
                    }
                ]
            }
        ])

    def vpic_run(self):
        print(self.kwargs['hosts'])


args = MyArgParse()
args.process_args()
```

### `example/hostfile_threads_test.py`

```python
from jarvis_util.util.argparse import ArgParse


class MyArgParse(ArgParse):
    def define_options(self):
        self.add_menu('vpic run',
                      keep_remainder=False)
        self.add_args([
            {
                'name': 'hosts',
                'msg': 'A list of hosts and threads per-host',
                'type': list,
                'args': [
                    {
                        'name': 'host',
                        'msg': 'Host name',
                        'type': str,
                    },
                    {
                        'name': 'count',
                        'msg': 'The number of devices to search for',
                        'type': int,
                    }
                ]
            }
        ])

    def vpic_run(self):
        print(self.kwargs['hosts'])


args = MyArgParse()
args.process_args()
```

### `example/menu_argparse.py`

```python
from jarvis_util.util.argparse import ArgParse


class MyArgParse(ArgParse):
    def define_options(self):
        self.add_menu('vpic')
        self.add_args([
            {
                'name': 'steps',
                'msg': 'Number of execution steps',
                'type': int,  # The type of this variable
                'required': True,  # This argument is required
                'pos': True,  # This is a positional argument
            }
        ])

        self.add_menu('bd-cats run')
        self.add_args([
            {
                'name': 'path',
                'msg': 'Path to particle data',
                'type': str,  # The type of this variable
                'required': True,  # This argument is required
                'pos': True,  # This is a positional argument
            }
        ])

        self.add_menu('bd-cats draw')
        self.add_args([
            {
                'name': 'resolution',
                'msg': 'Dimensions of the image to create',
                'type': str,  # The type of this variable
                'required': True,  # This argument is required
                'pos': True,  # This is a positional argument
            }
        ])

    def vpic(self):
        print(f'Starting VPIC with {self.kwargs["steps"]} steps')

    def bd_cats_run(self):
        print(f'Starting BD-CATS with {self.kwargs["path"]}')

    def bd_cats_draw(self):
        print(f'Drawing BD-CATS output at {self.kwargs["resolution"]}')


args = MyArgParse()
args.process_args()
```

### `example/remainder.py`

```python
from jarvis_util.util.argparse import ArgParse


class MyArgParse(ArgParse):
    def define_options(self):
        self.add_menu(keep_remainder=True)
        self.add_args([
            {
                'name': 'hi',
                'msg': 'hello',
                'type': str,
                'default': None
            }
        ])

    def main_menu(self):
        print(self.kwargs['hi'])
        print(self.remainder)


args = MyArgParse()
args.process_args()
```

### `example/remainder_kv.py`

```python
from jarvis_util.util.argparse import ArgParse


class MyArgParse(ArgParse):
    def define_options(self):
        self.add_menu(keep_remainder=True,
                      remainder_as_kv=True)
        self.add_args([
            {
                'name': 'hi',
                'msg': 'hello',
                'type': str,
                'default': None
            }
        ])

    def main_menu(self):
        print(self.kwargs['hi'])
        print(self.remainder_kv)


args = MyArgParse()
args.process_args()
```

### `jarvis_util/__init__.py`

```python
"""Import all modules"""
from jarvis_util.jutil_manager import *
from jarvis_util.util.expand_env import *
from jarvis_util.util.size_conv import *
from jarvis_util.util.logging import *
from jarvis_util.util.hostfile import *
from jarvis_util.util.small_df import *
from jarvis_util.util.argparse import *
from jarvis_util.util.import_all import *
from jarvis_util.util.import_mod import *
from jarvis_util.util.naming import *
from jarvis_util.serialize.pickle import *
from jarvis_util.serialize.ini_file import *
from jarvis_util.serialize.yaml_file import *
from jarvis_util.serialize.json_file import *
from jarvis_util.serialize.serializer import *
from jarvis_util.serialize.text_file import *
from jarvis_util.shell.spark_exec import *
from jarvis_util.shell.pbs_exec import *
from jarvis_util.shell.exec_info import *
from jarvis_util.shell.slurm_exec import *
from jarvis_util.shell.scp import *
from jarvis_util.shell.compile import *
from jarvis_util.shell.pssh_exec import *
from jarvis_util.shell.filesystem import *
from jarvis_util.shell.mpi_exec import *
from jarvis_util.shell.local_exec import *
from jarvis_util.shell.process import *
from jarvis_util.shell.exec import *
from jarvis_util.shell.ssh_exec import *
from jarvis_util.shell.pscp import *
from jarvis_util.introspect.monitor import *
from jarvis_util.introspect.system_info import *
```

### `jarvis_util/introspect/__init__.py`

```python

```

### `jarvis_util/introspect/monitor.py`

```python
from jarvis_util.shell.exec import Exec
from jarvis_util.serialize.yaml_file import YamlFile
import os
import yaml

class Callgrind(Exec):
    def __init__(self, cmd, exec_info=None):
        super().__init__(f'valgrind --tool=callgrind {cmd}')


class Monitor(Exec):
    def __init__(self, frequency_sec, monitor_dir, exec_info=None):
        super().__init__(
            f'pymonitor {frequency_sec} {monitor_dir}', exec_info)


class MonitorParser:
    def __init__(self, monitor_dir):
        self.monitor_dir = monitor_dir
        self.disk = {}
        self.net = {}
        self.mem = {}
        self.cpu = {}

    def parse(self):
        paths = os.listdir(self.monitor_dir)
        for hostname in paths:
            path = os.path.join(self.monitor_dir, hostname)
            with open(path, 'r') as fp:
                lines = fp.readlines()
                for line in lines:
                    try:
                        yaml_dict = yaml.load(line, Loader=yaml.FullLoader)
                    except yaml.YAMLError:
                        continue
                    if yaml_dict['type'] == 'DSK':
                        if hostname not in self.disk:
                            self.disk[hostname] = []
                        self.disk[hostname].append(yaml_dict)
                    elif yaml_dict['type'] == 'NET':
                        if hostname not in self.net:
                            self.net[hostname] = []
                        self.net[hostname].append(yaml_dict)
                    elif yaml_dict['type'] == 'MEM':
                        if hostname not in self.mem:
                            self.mem[hostname] = []
                        self.mem[hostname].append(yaml_dict)
                    elif yaml_dict['type'] == 'CPU':
                        if hostname not in self.cpu:
                            self.cpu[hostname] = []
                        self.cpu[hostname].append(yaml_dict)

    def avg_memory(self):
        total = 0
        count = 0
        for hostname in self.mem:
            for mem in self.mem[hostname]:
                total += mem['percent']
                count += 1
        return total / count

    def peak_memory(self):
        peak = 0
        for hostname in self.mem:
            for mem in self.mem[hostname]:
                peak = max(peak, mem['percent'])
        return peak

    def avg_cpu(self):
        total = 0
        count = 0
        for hostname in self.cpu:
            for cpu in self.cpu[hostname]:
                total += cpu['percent']
                count += 1
        return total / count
```

### `jarvis_util/introspect/system_info.py`

```python
"""
This module provides methods for querying the information of the host
system. This can be used to make scripts more portable.
"""

import sys
import socket
import re
import platform
from jarvis_util.util.logging import ColorPrinter, Color
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.local_exec import LocalExec, LocalExecInfo
from jarvis_util.shell.mpi_exec import MpiExecInfo
from jarvis_util.util.size_conv import SizeConv
from jarvis_util.serialize.yaml_file import YamlFile
from jarvis_util.shell.process import Kill
from jarvis_util.util.hostfile import Hostfile
import jarvis_util.util.small_df as sdf
import threading
import json
import yaml
import shlex
import ipaddress
import copy
import time
import os
from pathlib import Path
# pylint: disable=C0121


# Note, not using enum to avoid YAML serialization errors
# YAML expects simple types
class StorageDeviceType:
    PMEM = 'pmem'
    NVME = 'nvme'
    SSD = 'ssd'
    HDD = 'hdd'


class SystemInfo:
    """
    This class queries information about the host machine, such as OS,
    CPU, and kernel
    """

    instance_ = None

    @staticmethod
    def get_instance():
        if SystemInfo.instance_ is None:
            SystemInfo.instance_ = SystemInfo()
        return SystemInfo.instance_

    def __init__(self):
        with open('/etc/os-release', 'r', encoding='utf-8') as fp:
            lines = fp.read().splitlines()
            self.os = self._detect_os_type(lines)
            self.os_like = self._detect_os_like_type(lines)
            self.os_version = self._detect_os_version(lines)
        self.ksemantic = platform.platform()
        self.krelease = platform.release()
        self.ktype = platform.system()
        self.cpu = platform.processor()
        self.cpu_family = platform.machine()

    def _detect_os_type(self, lines):
        for line in lines:
            if 'ID=' in line:
                if 'ubuntu' in line:
                    return 'ubuntu'
                elif 'centos' in line:
                    return 'centos'
                elif 'debian' in line:
                    return 'debian'

    def _detect_os_like_type(self, lines):
        for line in lines:
            if 'ID_LIKE=' in line:
                if 'ubuntu' in line:
                    return 'ubuntu'
                elif 'centos' in line:
                    return 'centos'
                elif 'debian' in line:
                    return 'debian'

    def _detect_os_version(self, lines):
        for line in lines:
            grp = re.match('VERSION_ID=\"(.*)\"', line)
            if grp:
                return grp.group(1)

    def __hash__(self):
        return hash(str([self.os, self.os_like,
                         self.os_version, self.ksemantic,
                         self.krelease, self.ktype,
                         self.cpu, self.cpu_family]))

    def __eq__(self, other):
        return (
            (self.os == other.os) and
            (self.os_like == other.os_like) and
            (self.os_version == other.os_version) and
            (self.ksemantic == other.ksemantic) and
            (self.krelease == other.krelease) and
            (self.cpu == other.cpu) and
            (self.cpu_family == other.cpu_family)
        )


class Lsblk(Exec):
    """
    List all block devices in the system per-node. Lsblk will return
    a JSON output

    A table is stored per-host:
        parent: the parent device of the partition (e.g., /dev/sda or NaN)
        device: the name of the partition (e.g., /dev/sda1)
        size: total size of the partition (bytes)
        mount: where the partition is mounted (if anywhere)
        model: the exact model of the device
        tran: the transport of the device (e.g., /dev/nvme)
        rota: whether or not the device is rotational
        dev_type: the category of the device
        host: the host this record corresponds to
    """
    columns = [
        'parent', 'device', 'size', 'mount', 'model', 'tran',
        'rota', 'dev_type', 'host'
    ]

    def __init__(self, exec_info):
        cmd = 'lsblk -o NAME,SIZE,MODEL,TRAN,MOUNTPOINT,ROTA -J'
        super().__init__(cmd, exec_info.mod(collect_output=True))
        self.exec_async = exec_info.exec_async
        self.df = None
        if not self.exec_async:
            self.wait()

    def wait(self):
        super().wait()
        total = []
        for host, stdout in self.stdout.items():
            try:
                lsblk_data = json.loads(stdout)['blockdevices']
                if len(lsblk_data) == 0:
                    continue
                for dev in lsblk_data:
                    parent = f'/dev/{dev["name"]}'
                    if dev['size'] is None:
                        dev['size'] = '0'
                    if dev['tran'] is None:
                        dev['tran'] = 'sata'
                    if dev['rota'] is None:
                        dev['rota'] = False
                    total.append({
                        'parent': None,
                        'device': parent,
                        'size': SizeConv.to_int(dev['size']),
                        'model': dev['model'],
                        'tran': dev['tran'].lower(),
                        'mount': dev['mountpoint'],
                        'rota': dev['rota'],
                        'dev_type': self.GetDevType(dev),
                        'host': host
                    })
                    if 'children' not in dev:
                        continue
                    for partition in dev['children']:
                        if partition['size'] is None:
                            partition['size'] = '0'
                        total.append({
                            'parent': parent,
                            'device': f'/dev/{partition["name"]}',
                            'size': SizeConv.to_int(partition['size']),
                            'model': dev['model'],
                            'tran': dev['tran'].lower(),
                            'mount': partition['mountpoint'],
                            'rota': dev['rota'],
                            'dev_type': self.GetDevType(dev),
                            'host': host
                        })
            except json.JSONDecodeError:
                pass
        self.df = sdf.SmallDf(rows=total, columns=self.columns)

    def GetDevType(self, dev):
        if dev['tran'] == 'sata':
            if dev['rota']:
                return str(StorageDeviceType.HDD)
            else:
                return str(StorageDeviceType.SSD)
        elif dev['tran'] == 'nvme':
            return str(StorageDeviceType.NVME)
        elif dev['tran'] == 'dimm':
            return str(StorageDeviceType.PMEM)


class PyLsblk(Exec):
    """
       List all block devices in the system per-node. PyLsblk will return
       a YAML output

       A table is stored per-host:
           parent: the parent device of the partition (e.g., /dev/sda or NaN)
           device: the name of the partition (e.g., /dev/sda1)
           size: total size of the partition (bytes)
           mount: where the partition is mounted (if anywhere)
           model: the exact model of the device
           tran: the transport of the device (e.g., /dev/nvme)
           rota: whether or not the device is rotational
           host: the host this record corresponds to
       """
    columns = [
        'parent', 'device', 'size', 'mount', 'model', 'tran',
        'rota', 'dev_type', 'host'
    ]
    def __init__(self, exec_info):
        cmd = 'pylsblk'
        super().__init__(cmd, exec_info.mod(collect_output=True, hide_output=False))
        self.exec_async = exec_info.exec_async
        self.df = None
        if not self.exec_async:
            self.wait()

    def wait(self):
        super().wait()
        total = []
        for host, stdout in self.stdout.items():
            lsblk_data = yaml.load(stdout, Loader=yaml.FullLoader)
            if not lsblk_data:
                print(f'Warning: no storage devices found on host {host}')
                print(f'STDOUT: \n{stdout}')
                continue
            for dev in lsblk_data:
                if dev['tran'] == 'pcie':
                    dev['tran'] = 'nvme'
                dev['dev_type'] = self.GetDevType(dev)
                dev['host'] = host
                total.append(dev)
        self.df = sdf.SmallDf(rows=total, columns=self.columns)

    def GetDevType(self, dev):
        if dev['tran'] == 'sata':
            if dev['rota']:
                return str(StorageDeviceType.HDD)
            else:
                return str(StorageDeviceType.SSD)
        elif dev['tran'] == 'nvme':
            return str(StorageDeviceType.NVME)
        elif dev['tran'] == 'dimm':
            return str(StorageDeviceType.PMEM)


class Blkid(Exec):
    """
    List all filesystems (even those unmounted) and their properties

    Stores a per-host table with the following:
        device: the device (or partition) which stores the data (e.g., /dev/sda)
        fs_type: the type of filesystem (e.g., ext4)
        uuid: filesystem-level uuid from the FS metadata
        partuuid: the partition-lable UUID for the partition
        partlabel: semantic partition type information
        label: semantic label given by users
        host: the host this entry corresponds to
    """
    def __init__(self, exec_info):
        cmd = 'blkid'
        super().__init__(cmd, exec_info.mod(collect_output=True))
        self.exec_async = exec_info.exec_async
        self.df = None
        if not self.exec_async:
            self.wait()

    def wait(self):
        super().wait()
        dev_list = []
        for host, stdout in self.stdout.items():
            devices = stdout.splitlines()
            for dev in devices:
                dev_dict = {}
                toks = shlex.split(dev)
                dev_name = toks[0].split(':')[0]
                dev_dict['device'] = dev_name
                dev_dict['host'] = host
                for tok in toks[1:]:
                    keyval = tok.split('=')
                    key = keyval[0].lower()
                    val = ' '.join(keyval[1:])
                    dev_dict[key] = val
                dev_list.append(dev_dict)
        df = sdf.SmallDf(dev_list)
        df = df.rename({'type': 'fs_type'})
        self.df = df


class ListFses(Exec):
    """
    List all mounted filesystems

    Will store a per-host dictionary containing:
        device: the device which contains the filesystem
        fs_size: total size of the filesystem
        used: total nubmer of bytes used
        avail: total number of bytes remaining
        use%: the percent of capacity used
        fs_mount: where the filesystem is mounted
        host: the host this entry corresponds to
    """

    def __init__(self, exec_info):
        cmd = 'df -h'
        super().__init__(cmd, exec_info.mod(collect_output=True))
        self.exec_async = exec_info.exec_async
        self.df = None
        if not self.exec_async:
            self.wait()

    def wait(self):
        super().wait()
        columns = ['device', 'fs_size', 'used',
                   'avail', 'use%', 'fs_mount', 'host']
        rows = []
        for host, stdout in self.stdout.items():
            lines = stdout.strip().splitlines()
            rows += [line.split() + [host] for line in lines[1:]]
        df = sdf.SmallDf(rows, columns=columns)
        self.df = df


class FiInfo(Exec):
    """
    List all networks and their information
        provider: network protocol (e.g., sockets, tcp, ib)
        fabric: IP address
        domain: network domain
        version: network version
        type: packet type (e.g., DGRAM)
        protocol: protocol constant
        host: the host this network corresponds to
    """
    def __init__(self, exec_info):
        super().__init__('fi_info', exec_info.mod(collect_output=True))
        self.exec_async = exec_info.exec_async
        self.graph = {}
        if not self.exec_async:
            self.wait()

    def wait(self):
        super().wait()
        providers = []
        for host, stdout in self.stdout.items():
            lines = stdout.strip().splitlines()
            for line in lines:
                if 'provider' in line:
                    providers.append({
                        'provider': line.split(':')[1].strip(),
                        'host': host
                    })
                else:
                    splits = line.split(':')
                    key = splits[0].strip()
                    val = splits[1].strip()
                    providers[-1][key] = val
        self.df = sdf.SmallDf(providers)
        self.df.drop_duplicates()


class ChiNetPing(Exec):
    """
    Determine whether a network functions across a set of hosts
    """
    def __init__(self, provider, domain, port, mode, 
                 local_only, exec_info, hostfile=None, 
                 timeout=None):
        if hostfile is None:
            hostfile = exec_info.hostfile
        hostfile = hostfile.path if hostfile.path else '\"\"'
        self.cmd = [
            'chi_net_ping',
            hostfile,
            f'\'{provider}\'',
            f'\'{domain}\'',
            str(port),
            mode,
            local_only
        ]
        self.cmd = ' '.join(self.cmd)
        if mode == 'server':
            super().__init__(self.cmd, exec_info.mod(
                exec_async=True, hide_output=False,
                timeout=timeout))
        else:
            super().__init__(self.cmd, LocalExecInfo(env=exec_info.env, 
            hide_output=False, timeout=timeout))


class ChiNetPingTest:
    """
    Determine whether a network functions across a set of hosts
    """
    def __init__(self, provider, domain, port, local_only,
                  exec_info, net_sleep=10, hostfile=None, timeout=5): 
        netping_timeout = net_sleep + timeout + 1
        self.server = ChiNetPing(provider, domain, port, "server", local_only,
                                 exec_info.mod(exec_async=True),
                                   hostfile=hostfile, timeout=netping_timeout)
        print(f'Server timeout: {net_sleep}')
        time.sleep(net_sleep)
        print(f'Client timeout: {timeout}') 
        self.client = ChiNetPing(provider, domain, port, "client", local_only, 
                                 exec_info.mod(exec_async=True),
                                 hostfile=hostfile,
                                 timeout=timeout)  
        time.sleep(timeout)
        print(f'Timeout finished')
        self.client.wait()
        self.exit_code = self.client.exit_code
        print(f'Client finished: {self.client.exit_code}')


class NetTest:
    """
    Determine whether a set of networks function across a set of hosts.
    """
    def __init__(self, fi_info_df, port, exec_info, 
                 exclusions=None, base_port=6040, net_sleep=10, local_only=False, 
                 server_start_only=False, timeout=5):
        self.local_only = local_only
        self.server_start_only = server_start_only
        self.working = [] 
        df = fi_info_df[['provider', 'domain', 'fabric']].drop_duplicates()
        if exclusions:
            exclusions = exclusions[['provider', 'domain', 'fabric']].drop_duplicates()
            df = df[lambda r: r not in exclusions]
        self.net_count = len(df)
        ColorPrinter.print(f'About to test {self.net_count} networks', Color.YELLOW)
        port = base_port
        threads = []
        self.results = [None] * len(df)
        self.timeout = timeout
        for idx, net in enumerate(df.rows): 
            self._async_test(idx, net, port, exec_info, net_sleep)
            port += 2

        # Wait for all threads to complete    
        for idx in range(len(df)):  
            result = self.results[idx]
            if result is not None:
                self.working.append(result)
            
        self.df = sdf.SmallDf(self.working)
        Kill('chi_net_ping', exec_info)

    def _async_test(self, idx, net, port, exec_info, net_sleep):
        if self.server_start_only:
            self.touch_test(idx, net, port, exec_info)
        else:
            self.roundtrip_test(idx, net, port, exec_info, net_sleep)

    def touch_test(self, idx, net, port, exec_info):
        provider = net['provider']
        domain = net['domain']
        fabric = net['fabric']
        # Create the output hostfile
        ColorPrinter.print(f'Testing {idx + 1}/{self.net_count} {provider}://{domain}/[{fabric}]:{port}', Color.CYAN)
        out_hostfile = os.path.join(Path.home(), '.jarvis', 'hostfiles', f'hosts.{idx}')
        os.makedirs(os.path.dirname(out_hostfile), exist_ok=True)
        compile = CompileHostfile(LocalExecInfo().hostfile, provider, domain, 
                                  fabric, out_hostfile, env=exec_info.env)
        # Run the ping test
        ping = ChiNetPing(provider, domain, port, "touchserver", "local",
                           exec_info, hostfile=compile.hostfile)
        if ping.exit_code != 0:
            ColorPrinter.print(f'EXCLUDING the network {provider}://{domain}/[{fabric}]:{port}: {ping.exit_code}', Color.YELLOW)
            ColorPrinter.print(f'EXCLUDING the network {provider}://{domain}/[{fabric}]:{port}: {ping.exit_code}', Color.YELLOW, file=sys.stderr)
        else:
            ColorPrinter.print(f'INCLUDING the network {provider}://{domain}/[{fabric}]:{port}', Color.GREEN)
            self.results[idx] = net

    def roundtrip_test(self, idx, net, port, exec_info, net_sleep):
        provider = net['provider']
        domain = net['domain']
        fabric = net['fabric']
        ColorPrinter.print(f'Testing {idx + 1}/{self.net_count} {provider}://{domain}/[{fabric}]:{port}', Color.CYAN)
        # Create the output hostfile
        out_hostfile = os.path.join(Path.home(), '.jarvis', 'hostfiles', f'hosts.{idx}')
        os.makedirs(os.path.dirname(out_hostfile), exist_ok=True)
        compile = CompileHostfile(exec_info.hostfile, provider, domain, 
                                  fabric, out_hostfile, env=exec_info.env)
        # Test if the network works locally
        ping = ChiNetPingTest(provider, domain, port, "local", 
                              exec_info, hostfile=compile.hostfile, timeout=5, net_sleep=5)
        net['shared'] = False
        shared = 'local'
        if ping.exit_code != 0:
            ColorPrinter.print(f'EXCLUDING the network {provider}://{domain}/[{fabric}]:{port} (hostfile={out_hostfile}): {ping.exit_code}', Color.YELLOW)
            ColorPrinter.print(f'EXCLUDING the network {provider}://{domain}/[{fabric}]:{port} (hostfile={out_hostfile}): {ping.exit_code}', Color.YELLOW, file=sys.stderr)
            return
        self.results[idx] = net
        port += 1
        if not self.local_only and domain != 'lo':
            # Test if the network works across hosts
            ping = ChiNetPingTest(provider, domain, port, "all", 
                                  exec_info, net_sleep, hostfile=compile.hostfile, timeout=self.timeout)
            if ping.exit_code == 0:
                net['shared'] = True
                shared = 'shared'
        ColorPrinter.print(f'INCLUDING the {shared} network {provider}://{domain}/[{fabric}]:{port}', Color.GREEN)
        ColorPrinter.print(f'INCLUDING the {shared} network {provider}://{domain}/[{fabric}]:{port}', Color.GREEN, file=sys.stderr)


class CompileHostfile(Exec):
    def __init__(self, cur_hosts, provider, domain, fabric, out_hostfile, env=None):
        cmd = [
            'chi_net_find',
            f'"{provider}"',
            f'"{domain}"',
            f'"{fabric}"',
            out_hostfile
        ]
        cmd = ' '.join(cmd)
        super().__init__(cmd, MpiExecInfo(env=env, hosts=cur_hosts, ppn=1, 
                                          nprocs=len(cur_hosts), hide_output=True))
        self.hostfile = Hostfile(path=out_hostfile)


class ResourceGraph:
    """
    Stores helpful information about storage and networking info for machines.

    Two tables are stored to make decisions on application deployment.
    fs:
        parent: the parent device of the partition (e.g., /dev/sda or NaN)
        device: the name of the device (e.g., /dev/sda1 or /dev/sda)
        mount: where the device is mounted (if anywhere)
        model: the exact model of the device
        dev_type: type of device
        fs_type: the type of filesystem (e.g., ext4)
        needs_root: whether the user needs sudo to access the device
        uuid: filesystem-levle uuid from the FS metadata
        avail: total number of bytes remaining
        shared: whether the this is a shared service or not
        host: the host this record corresponds to
    net:
        provider: network protocol (e.g., sockets, tcp, ib)
        fabric: IP address
        domain: network domain
        host: the host this network corresponds to
        speed: the network speed of the interconnect
        shared: whether the network is used across hosts

    TODO: Need to verify on more than ubuntu20.04
    TODO: Can we make this work for windows?
    TODO: Can we make this work even when hosts have different OSes?
    """

    def __init__(self):
        self.fs_columns = [
            'parent', 'device', 'mount', 'model', 'dev_type',
            'fs_type', 'uuid',
            'avail', 'shared', 'needs_root'
        ]
        self.net_columns = [
            'provider', 'fabric', 'domain',
            'speed', 'shared'
        ]
        self.create()
        self.path = None

    """
    Build the resource graph
    """

    def create(self):
        self.fs = sdf.SmallDf(columns=self.fs_columns)
        self.net = sdf.SmallDf(columns=self.net_columns)

    def build(self, exec_info, introspect=True, net_sleep=10):
        """
        Build a resource graph.

        :param exec_info: Where to collect resource information
        :param introspect: Whether to pylsblk system info, or rely solely
        on admin-defined settings
        :return: self
        """
        self.create()
        if introspect:
            self.introspect_fs(exec_info)
            self.introspect_net(exec_info, prune_nets=True, net_sleep=net_sleep)
        self.apply()
        return self
    
    def modify(self, exec_info, net_sleep):
        """
        Edit a resource graph with new information
        
        """
        self.introspect_fs(exec_info)
        self.introspect_net(exec_info, prune_nets=True, net_sleep=net_sleep)
        self.apply()

    """
    Introspect filesystems
    """

    def introspect_fs(self, exec_info, sudo=False):
        lsblk = PyLsblk(exec_info.mod(hide_output=True))  
        blkid = Blkid(exec_info.mod(hide_output=True))
        list_fs = ListFses(exec_info.mod(hide_output=True))
        fs = sdf.merge([lsblk.df, blkid.df],
                          on=['device', 'host'],
                          how='outer') 
        fs[:, 'shared'] = False
        fs = sdf.merge([fs, list_fs.df],
                            on=['device', 'host'],
                            how='outer')
        fs['mount'] = fs['fs_mount'] 
        fs = self._find_common_mounts(fs, exec_info)
        fs = self._label_user_mounts(fs)
        fs = fs.drop_columns([
            'used', 'use%', 'fs_mount', 'partuuid', 'fs_size',
            'partlabel', 'label', 'host'])
        # Filter out all devices that begin with /run
        exclusions = ['/run', '/sys', '/proc', '/dev/shm', '/boot']
        fs = fs.loc(lambda r: r['mount'] and not r['needs_root']
                     and not any(r['mount'].startswith(ex) for ex in exclusions)
                     and not r['device'] == 'tmpfs')
        self.fs = fs
        return self.fs
    
    def _find_common_mounts(self, fs, exec_info):
        """
        Finds mount point points common across all hosts
        """ 
        io_groups = fs.groupby(['mount', 'device'])
        common = []
        for name, group in io_groups.groups.items():
            if len(group) != len(exec_info.hostfile.hosts):
                continue
            common.append(group.rows[0])
        return sdf.SmallDf(common)

    def _label_user_mounts(self, fs):
        """
        Try to find folders/directories the current user
        can access without root priveleges in each mount
        """
        for dev in fs.rows:
            dev['needs_root'] = True
            if dev['mount'] is None:
                continue
            if not dev['mount'].startswith('/'):
                continue
            dev['mount'] = self._try_user_access_paths(dev, fs)
        return sdf.SmallDf(fs.rows)

    def _try_user_access_paths(self, dev, fs):
        username = os.getenv('USER') or os.getenv('USERNAME')
        paths = [
            dev['mount'], 
            os.path.join(dev["mount"], username),
            os.path.join(dev["mount"], 'users', username),
            os.path.join(dev["mount"], 'home', username),
        ]
        for path in paths:
            if self._try_user_access(fs, path, path == dev['mount']):
                dev['needs_root'] = False
                return path
        dev['needs_root'] = True
        return dev['mount']

    def _try_user_access(self, fs, mount, known_mount=False):
        try:
            if mount.startswith('/boot'):
                print(mount)
            if not known_mount and self._check_if_mounted(fs, mount):
                return False
            test_file = os.path.join(mount, '.jarvis_access')
            with open(test_file, 'w') as f:
                pass
            with open(test_file, 'r') as f:
                pass
            os.remove(test_file)
            return True
        except (PermissionError, OSError):
            return False

    def _check_if_mounted(self, fs, mount):
        return len(fs[lambda r: r['mount'] == mount]) > 0

    """
    Introspect networks
    """

    def introspect_net(self, exec_info, prune_nets=False, prune_port=4192, net_sleep=10):
        fi_info = FiInfo(exec_info.mod(hide_output=True))
        if prune_nets:
            fi_info = NetTest(fi_info.df, prune_port, exec_info.mod(hide_output=True), 
            exclusions=self.net, net_sleep=net_sleep, server_start_only=True)
        net_df = fi_info.df
        net_df[:, 'speed'] = 0
        net_df.drop_columns(['version', 'type', 'protocol'])
        net_df.drop_duplicates()
        if self.net:
            self.net = sdf.concat([self.net, net_df])
        else:
            self.net = net_df

    """
    Update the resource graph
    """

    def add_storage(self, hosts, records):
        """
        Register a set of storage devices on a set of hosts

        :param hosts: Hostfile() indicating set of hosts to make record for
        :param records: A list or single dict of device info
        :return: None
        """
        if not isinstance(records, list):
            records = [records]
        new_rows = []
        for host in hosts.hosts:
            for record in records:
                record = copy.deepcopy(record)
                record['host'] = host
                new_rows.append(record)
        new_df = sdf.SmallDf(rows=new_rows, columns=self.fs.columns)
        self.fs = sdf.concat([self.fs, new_df])
        self.apply()

    def add_net(self, hosts, records):
        """
        Register a network record

        :param hosts: Hostfile() indicating set of hosts to make record for
        :param records: A list or single dict of network info
        :return: None
        """
        new_rows = []
        new_rows = []
        for host, ip in zip(hosts.hosts, hosts.hosts_ip):
            for record in records:
                record = copy.deepcopy(record)
                record['fabric'] = ip
                record['host'] = host
                new_rows.append(record)
        new_df = sdf.SmallDf(rows=new_rows, columns=self.net.columns)
        self.net = sdf.concat([self.net, new_df])
        self.apply()

    def filter_fs(self, mount_res):
        """
        Track all filesystems + devices matching the mount regex.

        :param mount_res: A list or single regex to match mountpoints
        :return: self
        """
        self.fs = self.find_storage(mount_res=mount_res)
        self.apply()
        return self

    def add_suffix(self, mount_re, mount_suffix):
        """
        Track all filesystems + devices matching the mount regex.

        :param mount_re: The regex to match a set of mountpoints
        :param mount_suffix: After the mount_re is matched, append this path
        to the mountpoint to indicate where users can access data. A typical
        value for this is /${USER}, indicating the mountpoint has a subdirectory
        per-user where they can access data.
        :return: self
        """
        df = self.fs[lambda r: re.match(mount_re, str(r['mount'])), 'mount']
        df += f'/{mount_suffix}'
        return self

    def make_common(self, hosts):
        """
        This resource graph should contain only entries common across all hosts.

        :return: self
        """
        self.fs = self.find_storage(common=True,
                                    condense=True)
        self.net = self.find_net_info(hosts, condense=True)
        return self

    def apply(self):
        """
        Remove duplicates from the host
        :return:
        """
        self.fs.drop_duplicates()
        self.net.drop_duplicates()
        self._derive_net_cols()
        self._derive_storage_cols()

    def save(self, path):
        """
        Save the resource graph YAML file

        :param path: the path to save the file
        :return: None
        """
        graph = {
            'fs': self.fs.rows,
            'net': self.net.rows,
        }
        YamlFile(path).save(graph)
        self.path = path

    def load(self, path):
        """
        Load resource graph from storage.

        :param path: The path to the resource graph YAML file
        :return: self
        """
        graph = YamlFile(path).load()
        self.path = path
        self.fs = sdf.SmallDf(graph['fs'], columns=self.fs_columns)
        self.net = sdf.SmallDf(graph['net'], columns=self.net_columns)
        self.apply()
        return self

    def _derive_storage_cols(self):
        df = self.fs
        if df is None or len(df) == 0:
            return
        df['mount'].fillna('')
        df['shared'].fillna(True)
        df['tran'].fillna('')
        df['size'].fillna(0)
        noavail = df[lambda r: r['avail'] == 0 or r['avail'] is None, :]
        noavail['avail'] = noavail['size']
        df['avail'].apply(lambda r, c: SizeConv.to_int(r[c]))
        df['size'] = df['avail']

    def _derive_net_cols(self):
        self.net['domain'].fillna('')

    """
    Query the resource graph
    """

    def find_shared_storage(self):
        """
        Find the set of shared storage services

        :return: Dataframe
        """
        df = self.fs
        return df[lambda r: r['shared'] == True]

    def find_user_storage(self):
        """
        Find the set of user-accessible storage services

        :return: Dataframe
        """
        df = self.fs
        return df[lambda r: r['needs_root'] == False]

    def find_storage(self,
                     dev_types=None,
                     is_mounted=True,
                     needs_root = None,
                     count_per_node=None,
                     count_per_dev=None,
                     min_cap=None,
                     min_avail=None,
                     mount_res=None,
                     shared=None,
                     df=None):
        """
        Find a set of storage devices.

        :param dev_types: Search for devices of type in order. Either a list
        or a string.
        :param is_mounted: Search only for mounted devices
        column and will only contain one entry per mount point.
        :param needs_root: Search for devices that do or don't need root access.
        :param count_per_node: Choose only a subset of devices matching query
        :param count_per_dev: Choose only a subset of devices matching query
        :param min_cap: Remove devices with too little overall capacity
        :param min_avail: Remove devices with too little available space
        :param mount_res: A regex or list of regexes to match mount points
        :param shared: Whether to search for devices which are shared
        :param df: The data frame to run this query
        :return: Dataframe
        """
        if df is None:
            df = self.fs
        # Filter devices by whether or not a mount is needed
        if is_mounted:
            df = df[lambda r: r['mount'] != '']
        # Filter devices matching the mount regex
        if mount_res is not None:
            if not isinstance(mount_res, (list, tuple, set)):
                mount_res = [mount_res]
            df = df[lambda r:
                    any(re.match(reg, str(r['mount'])) for reg in mount_res)]
        # Filter devices by whether or not root is needed
        if needs_root is not None:
            df = df[lambda r: r['needs_root'] == needs_root]
        # Find devices of a particular type
        if dev_types is not None:
            if not isinstance(dev_types, (list, tuple, set)):
                dev_types = [dev_types]
            df = df[lambda r: str(r['dev_type']) in dev_types]
        # Remove storage with too little capacity
        if min_cap is not None:
            df = df[lambda r: r['size'] >= min_cap]
        # Remove storage with too little available space
        if min_avail is not None:
            df = df[lambda r: r['avail'] >= min_avail]
        # Take a certain number of each device per-host
        if count_per_dev is not None:
            df = df.groupby(['dev_type', 'host']).\
                head(count_per_dev).reset_index()
        # Take a certain number of matched devices per-host
        if count_per_node is not None:
            df = df.groupby('host').head(count_per_node).reset_index()
        #     df = df.drop_columns('host')
        if shared is not None:
            df = df[lambda r: r['shared'] == shared]
        return df

    def find_net_info(self,
                      hosts=None,
                      strip_ips=False,
                      providers=None,
                      local=True,
                      shared=True,
                      df=None,
                      prune_port=6040,
                      env=None):
        """
        Find the set of networks common between each host.

        :param hosts: A Hostfile() data structure containing the set of
        all hosts to find network information for
        :param strip_ips: remove IPs that are not compatible with the hostfile
        :param providers: The network protocols to search for.
        :param df: The df to use for this query
        :param local: Filter local networks
        :param shared: Filter shared networks
        :param prune_port: The port to use for network testing
        :param net_sleep: The time to sleep between network tests
        :param env: Environment for the net ping tests
        :return: Dataframe
        """
        if df is None:
            df = self.net
        # Choose only a subset of providers
        if providers is not None:
            if not isinstance(providers, (list, set)):
                providers = [providers]
            providers = set(providers)
            df = df[lambda r: r['provider'] in providers]
        # Remove shared networks
        if not shared:
            df = df[lambda r: r['shared'] != True]
        # Remove local networks
        if not local:
            df = df[lambda r: r['shared'] != False]
        # Test validitiy of networks for current hostfile
        if hosts is not None and strip_ips:
            # Perform a local net-test to see if we can start a server 
            fi_info = NetTest(df, prune_port, 
                    LocalExecInfo(hostfile=hosts, env=env, hide_output=True),
                    net_sleep=1, local_only=True, server_start_only=True)
            df = fi_info.df
        return df

    def print_df(self, df):
        if 'device' in df.columns:
            print(df.sort_values('mount').to_string())
        else:
            print(df.sort_values('provider').to_string())


# pylint: enable=C0121
```

### `jarvis_util/jutil_manager.py`

```python
"""
This file contains properties which are globally accessible to all
jarvis-util modules. This can be used to configure various aspects
of jarvis, such as output.
"""


class JutilManager:
    """
    A singleton which stores various properties that can be queried by
    internally by jutil modules. This includes properties such output
    management.
    """

    instance_ = None

    @staticmethod
    def get_instance():
        if JutilManager.instance_ is None:
            JutilManager.instance_ = JutilManager()
        return JutilManager.instance_

    def __init__(self):
        self.collect_output = False
        self.hide_output = False
        self.debug_mpi_exec = False
        self.debug_local_exec = False
        self.debug_scp = False
        self.debug_slurm = False
        self.debug_pbs = True
```

### `jarvis_util/serialize/__init__.py`

```python

```

### `jarvis_util/serialize/ini_file.py`

```python
"""
This module contains methods to serialize and deserialize data from
a human-readable ini file.
"""
import configparser
from jarvis_util.serialize.serializer import Serializer


class IniFile(Serializer):
    """
    This class contains methods to serialize and deserialize data from
    a human-readable ini file.
    """
    def __init__(self, path):
        self.path = path

    def load(self):
        config = configparser.ConfigParser()
        config.read(self.path)
        return config

    def save(self, data):
        with open(self.path, 'w', encoding='utf-8') as fp:
            data.write(fp)
```

### `jarvis_util/serialize/json_file.py`

```python
"""
This module contains methods to serialize and deserialize data from
a human-readable YAML file.
"""
from jarvis_util.serialize.serializer import Serializer
import json


class JsonFile(Serializer):
    """
    This class contains methods to serialize and deserialize data from
    a human-readable YAML file.
    """
    def __init__(self, path):
        self.path = path

    def load(self):
        with open(self.path, 'r', encoding='utf-8') as fp:
            return json.load(fp)
        return None

    def save(self, data):
        with open(self.path, 'w', encoding='utf-8') as fp:
            json.dump(data, fp)
```

### `jarvis_util/serialize/pickle.py`

```python
"""
This module contains methods to serialize and deserialize data from
a pickle file.
"""

import pickle as pkl
from jarvis_util.serialize.serializer import Serializer


class PickleFile(Serializer):
    """
    This class serializes and deserializes data from a pickle file
    """

    def __init__(self, path):
        self.path = path

    def load(self):
        with open(self.path, 'rb') as fp:
            return pkl.load(fp)

    def save(self, data):
        with open(self.path, 'wb') as fp:
            pkl.dump(data, fp)
```

### `jarvis_util/serialize/serializer.py`

```python
"""
This module contains an abstract class used to define classes which
serialize data to a file.
"""

from abc import ABC, abstractmethod


class Serializer(ABC):
    """
    An abstract class which loads serialized data from a file and
    saves serialized data to a file.
    """

    @abstractmethod
    def load(self):
        pass

    @abstractmethod
    def save(self, data):
        pass
```

### `jarvis_util/serialize/text_file.py`

```python
"""
This module stores data into a file in a human-readable way
"""
from jarvis_util.serialize.serializer import Serializer


class TextFile(Serializer):
    """
    This class stores data directly into a file using str() as the
    serialization method. The data is intended to be human-readable.
    """
    def __init__(self, path):
        self.path = path

    def load(self):
        with open(self.path, 'r', encoding='utf-8') as fp:
            data = fp.read()
        return data

    def save(self, data):
        with open(self.path, 'w', encoding='utf-8') as fp:
            fp.write(data)
```

### `jarvis_util/serialize/yaml_file.py`

```python
"""
This module contains methods to serialize and deserialize data from
a human-readable YAML file.
"""
from jarvis_util.serialize.serializer import Serializer
import yaml


class YamlFile(Serializer):
    """
    This class contains methods to serialize and deserialize data from
    a human-readable YAML file.
    """
    def __init__(self, path):
        self.path = path

    def load(self):
        with open(self.path, 'r', encoding='utf-8') as fp:
            return yaml.load(fp, Loader=yaml.FullLoader)
        return None

    def save(self, data):
        with open(self.path, 'w', encoding='utf-8') as fp:
            yaml.dump(data, fp)

    def append(self, data):
        with open(self.path, 'a', encoding='utf-8') as fp:
            yaml.dump(data, fp)
```

### `jarvis_util/shell/__init__.py`

```python

```

### `jarvis_util/shell/compile.py`

```python

from .exec import Exec
from .local_exec import LocalExecInfo
from .filesystem import Mkdir

class Cmake(Exec):
    def __init__(self, root_dir, out_dir, opts=None, exec_info=None):
        """
        Run cmake

        :param root_dir: Where the root of the cmake project is
        :param out_dir: Where to output build data
        :param opts: A dict mapping cmake keys to values
        :param exec_info: The execution info
        """
        if exec_info is None:
            exec_info = LocalExecInfo()
        self.opts = opts
        self.root_dir = root_dir
        self.out_dir = out_dir
        Mkdir(out_dir)
        self.cmd = [f'cmake {root_dir}']
        if opts is not None:
            for key, val in opts.items():
                if isinstance(val, bool):
                    if val:
                        self.cmd.append(f'-D{key}=ON')
                    else:
                        self.cmd.append(f'-D{key}=OFF')
                else:
                    self.cmd.append(f'-D{key}={val}')
        self.cmd = ' '.join(self.cmd)
        super().__init__(self.cmd, exec_info.mod(cwd=self.out_dir))

class Make(Exec):
    def __init__(selfs, build_dir, nthreads=8, install=False,
                 exec_info=None):
        if exec_info is None:
            exec_info = LocalExecInfo()
        if install:
            cmd = f'make -j{nthreads} install'
        else:
            cmd = f'make -j{nthreads}'
        super().__init__(cmd,
                         exec_info.mod(cwd=build_dir))
```

### `jarvis_util/shell/exec.py`

```python
"""
This module provides mechanisms to execute binaries either locally or
remotely.
"""
from .local_exec import LocalExec
from .pssh_exec import PsshExec
from .pssh_exec import SshExec
from .mpi_exec import MpiVersion, MpichExec, OpenMpiExec, CrayMpichExec
from .exec_info import ExecInfo, ExecType, Executable


class Exec(Executable):
    """
    This class is a factory which wraps around various shell command
    execution stragies, such as MPI and SSH.
    """

    def __init__(self, cmd, exec_info=None):
        """
        Execute a command or list of commands

        :param cmd: list of commands or a single command string
        :param exec_info: Info needed to execute processes locally
        """
        super().__init__()
        if exec_info is None:
            exec_info = ExecInfo()
        exec_type = exec_info.exec_type
        if exec_type == ExecType.LOCAL:
            self.exec_ = LocalExec(cmd, exec_info)
        elif exec_type == ExecType.SSH:
            self.exec_ = SshExec(cmd, exec_info)
        elif exec_type == ExecType.PSSH:
            self.exec_ = PsshExec(cmd, exec_info)
        elif exec_type == ExecType.MPI:
            exec_type = MpiVersion(exec_info).version

        if exec_type == ExecType.MPICH:
            self.exec_ = MpichExec(cmd, exec_info)
        elif exec_type == ExecType.INTEL_MPI:
            self.exec_ = MpichExec(cmd, exec_info)
        elif exec_type == ExecType.OPENMPI:
            self.exec_ = OpenMpiExec(cmd, exec_info)
        elif exec_type == ExecType.CRAY_MPICH:
            self.exec_ = CrayMpichExec(cmd, exec_info)

        self.set_exit_code()
        self.set_output()

    def wait(self):
        self.exec_.wait()
        self.set_output()
        self.set_exit_code()
        return self.exit_code

    def set_output(self):
        self.stdout = self.exec_.stdout
        self.stderr = self.exec_.stderr
        if isinstance(self.stdout, str):
            if hasattr(self.exec_, 'addr'):
                host = self.exec_.addr
            else:
                host = 'localhost'
            self.stdout = {host: self.stdout}
            self.stderr = {host: self.stderr}

    def set_exit_code(self):
        self.exec_.set_exit_code()
        self.exit_code = self.exec_.exit_code
```

### `jarvis_util/shell/exec_info.py`

```python
"""
This module contains data structures for determining how to execute
a subcommand. This includes information such as storing SSH keys,
passwords, working directory, etc.
"""

from enum import Enum
from jarvis_util.util.hostfile import Hostfile
from jarvis_util.jutil_manager import JutilManager
import os
from abc import ABC, abstractmethod


class ExecType(Enum):
    """
    Different program execution methods.
    """

    LOCAL = 'LOCAL'
    SSH = 'SSH'
    PSSH = 'PSSH'
    MPI = 'MPI'
    MPICH = 'MPICH'
    OPENMPI = 'OPENMPI'
    INTEL_MPI = 'INTEL_MPI'
    SLURM = 'SLURM'
    PBS = 'PBS'
    CRAY_MPICH = 'CRAY_MPICH'


class ExecInfo:
    """
    Contains all information needed to execute a program. This includes
    parameters such as the path to key-pairs, the hosts to run the program
    on, number of processes, etc.
    """
    def __init__(self,  exec_type=ExecType.LOCAL, nprocs=None, ppn=None,
                 user=None, pkey=None, port=None,
                 hostfile=None, hosts=None, env=None,
                 sleep_ms=0, sudo=False, sudoenv=True, cwd=None,
                 collect_output=None, pipe_stdout=None, pipe_stderr=None,
                 hide_output=None, exec_async=False, stdin=None,
                 do_dbg=False, dbg_port=None, strict_ssh=False, timeout=None, **kwargs):
        """

        :param exec_type: How to execute a program. SSH, MPI, Local, etc.
        :param nprocs: Number of processes to spawn. E.g., MPI uses this
        :param ppn: Number of processes per node. E.g., MPI uses this
        :param user: The user to execute command under. E.g., SSH, PSSH
        :param pkey: The path to the private key. E.g., SSH, PSSH
        :param port: The port to use for connection. E.g., SSH, PSSH
        :param hostfile: The hosts to launch command on. E.g., PSSH, MPI
        :param hosts: A list (or single string) of host names to run command on.
        :param env: The environment variables to use for command.
        :param sleep_ms: Sleep for a period of time AFTER executing
        :param sudo: Execute command with root privilege. E.g., SSH, PSSH
        :param sudoenv: Support environment preservation in sudo
        :param cwd: Set current working directory. E.g., SSH, PSSH
        :param collect_output: Collect program output in python buffer
        :param pipe_stdout: Pipe STDOUT into a file. (path string)
        :param pipe_stderr: Pipe STDERR into a file. (path string)
        :param hide_output: Whether to print output to console
        :param exec_async: Whether to execute program asynchronously
        :param stdin: Any input needed by the program. Only local
        :param do_dbg: Enable debugging
        :param dbg_port: The port number
        :param strict_ssh: Strict ssh host key verification
        :param timeout: Timeout subprocess within timeframe
        """

        self.exec_type = exec_type
        self.nprocs = nprocs
        self.user = user
        self.pkey = pkey
        self.port = port
        self.ppn = ppn
        self.hostfile = hostfile
        self._set_hostfile(hostfile=hostfile, hosts=hosts)
        self.env = env
        self.basic_env = {}
        self._set_env(env)
        self.cwd = cwd
        self.sudo = sudo
        self.sudoenv = sudoenv
        self.sleep_ms = sleep_ms
        self.collect_output = collect_output
        self.pipe_stdout = pipe_stdout
        self.pipe_stderr = pipe_stderr
        self.hide_output = hide_output
        self.exec_async = exec_async
        self.stdin = stdin
        self.do_dbg = do_dbg
        self.dbg_port = dbg_port
        self.strict_ssh = strict_ssh
        self.timeout = timeout
        self.keys = ['exec_type', 'nprocs', 'ppn', 'user', 'pkey', 'port',
                     'hostfile', 'env', 'sleep_ms', 'sudo', 'sudoenv',
                     'cwd', 'hosts', 'collect_output',
                     'pipe_stdout', 'pipe_stderr', 'hide_output',
                     'exec_async', 'stdin', 'do_dbg', 'dbg_port', 'strict_ssh', 'timeout']

    def _set_env(self, env):
        if env is None:
            self.env = {}
        else:
            self.env = env
        basic_env = [
            'PATH', 'LD_LIBRARY_PATH', 'LIBRARY_PATH', 'CMAKE_PREFIX_PATH',
            'PYTHONPATH', 'CPATH', 'INCLUDE', 'JAVA_HOME'
        ]
        self.basic_env = {}
        for key in basic_env:
            if key not in os.environ:
                continue
            self.basic_env[key] = os.getenv(key)
        for key, val in self.basic_env.items():
            if key not in self.env:
                self.env[key] = val
        self.basic_env.update(self.env)
        if 'LD_PRELOAD' in self.basic_env:
            del self.basic_env['LD_PRELOAD']

    def _set_hostfile(self, hostfile=None, hosts=None):
        if hostfile is not None:
            if isinstance(hostfile, str):
                self.hostfile = Hostfile(hostfile=hostfile)
            elif isinstance(hostfile, Hostfile):
                self.hostfile = hostfile
            else:
                raise Exception('Hostfile is neither string nor Hostfile')
        if hosts is not None:
            if isinstance(hosts, list):
                self.hostfile = Hostfile(all_hosts=hosts)
            elif isinstance(hosts, str):
                self.hostfile = Hostfile(all_hosts=[hosts])
            elif isinstance(hosts, Hostfile):
                self.hostfile = hosts
            else:
                raise Exception('Host set is neither str, list or Hostfile')

        if hosts is not None and hostfile is not None:
            raise Exception('Must choose either hosts or hostfile, not both')

        if self.hostfile is None:
            self.hostfile = Hostfile()

    def mod(self, **kwargs):
        self._mod_kwargs(kwargs)
        return ExecInfo(**kwargs)

    def _mod_kwargs(self, kwargs):
        for key in self.keys:
            if key not in kwargs and hasattr(self, key):
                kwargs[key] = getattr(self, key)

    def copy(self):
        return self.mod()


class Executable(ABC):
    """
    An abstract class representing a class which is intended to run
    shell commands. This includes SSH, MPI, etc.
    """

    def __init__(self):
        self.exit_code = None
        self.stdout = ''
        self.stderr = ''
        self.jutil = JutilManager.get_instance()

    def failed(self):
        return self.exit_code != 0

    @abstractmethod
    def set_exit_code(self):
        pass

    @abstractmethod
    def wait(self):
        pass

    def smash_cmd(self, cmds, sudo, basic_env, sudoenv):
        """
        Convert a list of commands into a single command for the shell
        to execute.

        :param cmds: A list of commands or a single command string
        :param prefix: A prefix for each command
        :param sudo: Whether or not root is required
        :param basic_env: The environment to forward to the command
        :param sudoenv: Whether sudo supports environment forwarding
        :return:
        """
        env = None
        if sudo:
            env = ''
            if sudoenv:
                env = [f'-E {key}=\"{val}\"' for key, val in
                       basic_env.items()]
                env = ' '.join(env)
            env = f'sudo {env}'
        if not isinstance(cmds, (list, tuple)):
            cmds = [cmds]
        if env is not None:
            cmds = [f'{env} {cmd}' for cmd in cmds]
        return ';'.join(cmds)

    def wait_list(self, nodes):
        for node in nodes:
            node.wait()

    def smash_list_outputs(self, nodes):
        """
        Combine the outputs of a set of nodes into a single output.
        For example, used if executing multiple commands in sequence.

        :param nodes:
        :return:
        """
        self.stdout = '\n'.join([node.stdout for node in nodes])
        self.stderr = '\n'.join([node.stderr for node in nodes])

    def per_host_outputs(self, nodes):
        """
        Convert the outputs of a set of nodes to a per-host dictionary.
        Used if sending commands to multiple hosts

        :param nodes:
        :return:
        """
        self.stdout = {}
        self.stderr = {}
        self.stdout = {node.addr: node.stdout for node in nodes}
        self.stderr = {node.addr: node.stderr for node in nodes}

    def set_exit_code_list(self, nodes):
        """
        Set the exit code from a set of nodes.

        :param nodes: The set of execution nodes that have been executed
        :return:
        """
        for node in nodes:
            if node.exit_code:
                self.exit_code = node.exit_code

    def get_dbg_cmd(self, cmd, exec_info):
        """
        Get the command to debug a program

        :param cmd: the command to debug
        :param exec_info: exec information
        :return: the debug command
        """
        dbg_port = exec_info.dbg_port
        preload = ""
        if 'LD_PRELOAD' in exec_info.env:
            exec_info.env = exec_info.env.copy()
            preload = exec_info.env['LD_PRELOAD']
            del exec_info.env['LD_PRELOAD']
        if len(preload):
            return f'gdbserver localhost:{dbg_port} env LD_PRELOAD={preload} {cmd}'
        else:
            return f'gdbserver localhost:{dbg_port} {cmd}'
```

### `jarvis_util/shell/filesystem.py`

```python
"""
This module contains various wrappers over typical filesystem commands seen
in shell scripts. This includes operations such as creating directories,
changing file permissions, etc.
"""
from .exec import Exec


class Mkdir(Exec):
    """
    Create directories + subdirectories.
    """

    def __init__(self, paths, exec_info=None):
        """
        Create directories + subdirectories. Does not fail if the dirs
        already exist.

        :param paths: A list of paths or a single path string.
        :param exec_info: Info needed to execute the mkdir command
        """

        if isinstance(paths, str):
            paths = [paths]
        path = ' '.join(paths)
        super().__init__(f'mkdir -p {path}', exec_info)


class Rm(Exec):
    """
    Remove a file and its subdirectories
    """

    def __init__(self, paths, exec_info=None):
        """
        Execute file or directory remove.

        :param paths: Either a list of paths or a single path string
        :param exec_info: Information needed to execute rm
        """

        if isinstance(paths, str):
            paths = [paths]
        path = ' '.join(paths)
        super().__init__(f'rm -rf {path}', exec_info)


class Chmod(Exec):
    """
    Change the mode of a file
    """

    def __init__(self, path=None, mode=None, modes=None, exec_info=None):
        """
        Change the mode of a file

        :param path: path to file to mode change
        :param mode: the mode to change to
        :param modes: A list of tuples [(Path, Mode)]
        :param exec_info: How to execute commands
        """
        cmds = []
        if path is not None and mode is not None:
            cmds.append(f'chmod {mode} {path}')
        if modes is not None:
            cmds += [f'chmod {mode[1]} {mode[0]}' for mode in modes]
        if len(cmds) == 0:
            raise Exception('Must set either path+mode or modes')
        super().__init__(cmds, exec_info)


class Chown(Exec):
    """
    Change the owner of a file
    """

    def __init__(self, path, user, group, exec_info=None):
        """
        Change the owner of a file

        :param path: path to file to chown
        :param user: user to chown to
        :param group: group to chown to
        :param exec_info: How to execute commands
        """
        super().__init__(f'chown {user}:{group} {path}', exec_info)
        

class Copy(Exec):
    """
    Change the mode of a file
    """

    def __init__(self, target=None, destination=None, exec_info=None):
        """
        Change the mode of a file

        :param target: path to file to copy
        :param destination: destination of the new file
        """
        if isinstance(target, str) and isinstance(destination, str):
            super().__init__(f'cp -r {target} {destination}', exec_info)
        else:
            raise Exception('target and destination must be strings')


class MkfsExt4(Exec):
    """
    Create an EXT4 filesystem on a device or partition
    """

    def __init__(self, device, force=False, exec_info=None, **kwargs):
        """
        Create an EXT4 filesystem on a device or partition.

        :param device: Path to the device or partition (e.g. /dev/sda1)
        :param force: Whether to force creation without prompting (defaults to False)
        :param exec_info: Information needed to execute mkfs
        :param kwargs: Additional EXT4 filesystem options:
            - block_size: Block size in bytes (must be power of 2)
            - label: Label for the filesystem (max 16 bytes)
            - bytes_per_inode: Number of bytes per inode (ratio for inode creation)
            - journal: Enable/disable journaling (True/False)
            - journal_device: External journal device path
            - num_inodes: Number of inodes to create
            - flex_bg_size: Size of a flex block group
            - reserved_blocks_percentage: Percentage of blocks reserved for super-user
            - stripe_width: RAID stripe width in blocks
            - extent: Enable/disable extents feature (True/False)
            - extra_isize: Additional inode space in bytes
            - quota: Enable quota support (user, group, project)
            - cluster_size: Cluster size in bytes
            - metadata_checksum: Enable metadata checksums (True/False)
        """
        cmd = 'mkfs.ext4'
        
        if force:
            cmd += ' -F'

        # Basic options
        if 'block_size' in kwargs:
            cmd += f' -b {kwargs["block_size"]}'
        
        if 'label' in kwargs:
            cmd += f' -L {kwargs["label"]}'

        if 'bytes_per_inode' in kwargs:
            cmd += f' -i {kwargs["bytes_per_inode"]}'

        # Journal options
        if 'journal' in kwargs and not kwargs['journal']:
            cmd += ' -O ^has_journal'
        if 'journal_device' in kwargs:
            cmd += f' -J device={kwargs["journal_device"]}'

        # Inode and block group options
        if 'num_inodes' in kwargs:
            cmd += f' -N {kwargs["num_inodes"]}'
        if 'flex_bg_size' in kwargs:
            cmd += f' -G {kwargs["flex_bg_size"]}'
        if 'reserved_blocks_percentage' in kwargs:
            cmd += f' -m {kwargs["reserved_blocks_percentage"]}'

        # Performance options
        if 'stripe_width' in kwargs:
            cmd += f' -E stride={kwargs["stripe_width"]}'
        if 'cluster_size' in kwargs:
            cmd += f' -C {kwargs["cluster_size"]}'

        # Feature flags
        if 'extent' in kwargs:
            cmd += ' -O extent' if kwargs['extent'] else ' -O ^extent'
        if 'extra_isize' in kwargs:
            cmd += f' -I {kwargs["extra_isize"]}'
        if 'quota' in kwargs:
            cmd += ' -O quota'
        if 'metadata_checksum' in kwargs:
            cmd += ' -O metadata_csum' if kwargs['metadata_checksum'] else ' -O ^metadata_csum'

        cmd += f' {device}'
        super().__init__(cmd, exec_info)


class MkfsXfs(Exec):
    """
    Create an XFS filesystem on a device or partition
    """

    def __init__(self, device, force=False, exec_info=None, **kwargs):
        """
        Create an XFS filesystem on a device or partition.

        :param device: Path to the device or partition (e.g. /dev/sda1)
        :param force: Whether to force creation without prompting (defaults to False)
        :param exec_info: Information needed to execute mkfs
        :param kwargs: Additional XFS filesystem options:
            - block_size: Block size in bytes (must be power of 2)
            - label: Label for the filesystem
            
            Data section options:
            - agcount: Number of allocation groups
            - data_sunit: Stripe unit for data section (in 512B blocks)
            - data_swidth: Stripe width for data section (in 512B blocks)
            
            Inode options:
            - isize: Inode size in bytes
            - sparse: Enable sparse inode allocation (0 or 1)
            
            Log section options:
            - logsize: Size of the log section in bytes
            - log_sunit: Stripe unit for log section (in 512B blocks)
            - log_internal: Whether log is internal (True) or external (False)
            - log_device: Device path for external log
            
            Real-time section options:
            - rt_device: Device path for real-time section
            - rt_extsize: Real-time extent size in bytes
            
            Metadata options:
            - lazy_count: Enable/disable lazy-count feature (0 or 1)
            - bigtime: Enable timestamps beyond 2038 (0 or 1)
            - finobt: Enable free inode btree (0 or 1)
            - sparse: Enable sparse inode allocation (0 or 1)
            - rmapbt: Enable reverse mapping btree (0 or 1)
            - reflink: Enable reflink feature (0 or 1)
            - metadata_crc: Enable metadata CRC feature (0 or 1)
        """
        cmd = 'mkfs.xfs'
        
        if force:
            cmd += ' -f'

        # Basic options
        if 'block_size' in kwargs:
            cmd += f' -b size={kwargs["block_size"]}'
        
        if 'label' in kwargs:
            cmd += f' -L {kwargs["label"]}'

        # Data section options
        data_opts = []
        if 'agcount' in kwargs:
            data_opts.append(f'agcount={kwargs["agcount"]}')
        if 'data_sunit' in kwargs:
            data_opts.append(f'sunit={kwargs["data_sunit"]}')
        if 'data_swidth' in kwargs:
            data_opts.append(f'swidth={kwargs["data_swidth"]}')
        if data_opts:
            cmd += f' -d {",".join(data_opts)}'

        # Inode options
        inode_opts = []
        if 'isize' in kwargs:
            inode_opts.append(f'size={kwargs["isize"]}')
        if 'sparse' in kwargs:
            inode_opts.append(f'sparse={1 if kwargs["sparse"] else 0}')
        if inode_opts:
            cmd += f' -i {",".join(inode_opts)}'

        # Log section options
        log_opts = []
        if 'logsize' in kwargs:
            log_opts.append(f'size={kwargs["logsize"]}')
        if 'log_sunit' in kwargs:
            log_opts.append(f'sunit={kwargs["log_sunit"]}')
        if 'log_internal' in kwargs and not kwargs['log_internal']:
            log_opts.append('internal=0')
        if 'log_device' in kwargs:
            log_opts.append(f'logdev={kwargs["log_device"]}')
        if log_opts:
            cmd += f' -l {",".join(log_opts)}'

        # Real-time section options
        rt_opts = []
        if 'rt_device' in kwargs:
            rt_opts.append(f'rtdev={kwargs["rt_device"]}')
        if 'rt_extsize' in kwargs:
            rt_opts.append(f'extsize={kwargs["rt_extsize"]}')
        if rt_opts:
            cmd += f' -r {",".join(rt_opts)}'

        # Metadata options
        meta_opts = []
        if 'lazy_count' in kwargs:
            meta_opts.append(f'lazy-count={kwargs["lazy_count"]}')
        if 'bigtime' in kwargs:
            meta_opts.append(f'bigtime={kwargs["bigtime"]}')
        if 'finobt' in kwargs:
            meta_opts.append(f'finobt={kwargs["finobt"]}')
        if 'rmapbt' in kwargs:
            meta_opts.append(f'rmapbt={kwargs["rmapbt"]}')
        if 'reflink' in kwargs:
            meta_opts.append(f'reflink={kwargs["reflink"]}')
        if 'metadata_crc' in kwargs:
            meta_opts.append(f'crc={1 if kwargs["metadata_crc"] else 0}')
        if meta_opts:
            cmd += f' -m {",".join(meta_opts)}'

        cmd += f' {device}'
        super().__init__(cmd, exec_info)


class MkfsF2fs(Exec):
    """
    Create a Flash-Friendly File System (F2FS) on a device or partition
    """

    def __init__(self, device, force=False, exec_info=None, **kwargs):
        """
        Create an F2FS filesystem on a device or partition.

        :param device: Path to the device or partition (e.g. /dev/sda1)
        :param force: Whether to force creation without prompting (defaults to False)
        :param exec_info: Information needed to execute mkfs
        :param kwargs: Additional F2FS filesystem options:
            - label: Volume label (up to 512 bytes)
            - segment_count: Number of segments per section
            - sectors_per_blk: Size of block in sectors (default: 4)
            - sections_per_zone: Number of sections per zone (default: 1)
            - trim: Enable/disable TRIM (default: True)
            - coverage: Space utilization in percentage (default: 100)
            - overprovision: Percentage of overprovision area (default: 5)
            - zoned: Configure zoned block device support
        """
        cmd = ['mkfs.f2fs']
        if force:
            cmd.append('-f')
        
        if 'label' in kwargs:
            cmd.extend(['-l', str(kwargs['label'])])
        if 'segment_count' in kwargs:
            cmd.extend(['-c', str(kwargs['segment_count'])])
        if 'sectors_per_blk' in kwargs:
            cmd.extend(['-s', str(kwargs['sectors_per_blk'])])
        if 'sections_per_zone' in kwargs:
            cmd.extend(['-z', str(kwargs['sections_per_zone'])])
        if 'trim' in kwargs and not kwargs['trim']:
            cmd.append('-t')
        if 'coverage' in kwargs:
            cmd.extend(['-u', str(kwargs['coverage'])])
        if 'overprovision' in kwargs:
            cmd.extend(['-r', str(kwargs['overprovision'])])
        if 'zoned' in kwargs and kwargs['zoned']:
            cmd.append('-m')

        cmd.append(device)
        super().__init__(' '.join(cmd), exec_info)


class MkfsBtrfs(Exec):
    """
    Create a BTRFS filesystem on a device or partition
    """

    def __init__(self, devices, force=False, exec_info=None, **kwargs):
        """
        Create a BTRFS filesystem on one or more devices.

        :param devices: Single device path or list of device paths
        :param force: Whether to force creation without prompting (defaults to False)
        :param exec_info: Information needed to execute mkfs
        :param kwargs: Additional BTRFS filesystem options:
            - label: Volume label
            - metadata_profile: Metadata profile (raid0, raid1, raid1c3, raid1c4, raid5, raid6, dup, single)
            - data_profile: Data profile (same options as metadata_profile)
            - mixed: Enable mixed block groups for metadata and data
            - nodesize: Node size in bytes (default: 16384)
            - sectorsize: Sector size in bytes (default: 4096)
            - features: List of features to enable
            - checksum: Checksum algorithm (crc32c, xxhash, sha256, blake2)
        """
        cmd = ['mkfs.btrfs']
        if force:
            cmd.append('-f')
        
        if 'label' in kwargs:
            cmd.extend(['-L', str(kwargs['label'])])
        if 'metadata_profile' in kwargs:
            cmd.extend(['-m', kwargs['metadata_profile']])
        if 'data_profile' in kwargs:
            cmd.extend(['-d', kwargs['data_profile']])
        if kwargs.get('mixed', False):
            cmd.append('--mixed')
        if 'nodesize' in kwargs:
            cmd.extend(['--nodesize', str(kwargs['nodesize'])])
        if 'sectorsize' in kwargs:
            cmd.extend(['--sectorsize', str(kwargs['sectorsize'])])
        if 'features' in kwargs:
            cmd.extend(['--features', ','.join(kwargs['features'])])
        if 'checksum' in kwargs:
            cmd.extend(['--checksum', kwargs['checksum']])

        if isinstance(devices, str):
            devices = [devices]
        cmd.extend(devices)
        super().__init__(' '.join(cmd), exec_info)


class MkfsZfs(Exec):
    """
    Create a ZFS filesystem on a device or pool
    """

    def __init__(self, name, exec_info=None, **kwargs):
        """
        Create a ZFS filesystem in a pool.

        :param name: Name of the filesystem to create (pool/dataset)
        :param exec_info: Information needed to execute zfs
        :param kwargs: Additional ZFS filesystem options:
            - mountpoint: Custom mount point
            - compression: Compression algorithm (on, off, lzjb, gzip, zle, lz4)
            - atime: Update access time on read (on/off)
            - quota: Limit on how much space can be used
            - reservation: Guaranteed space for dataset
            - recordsize: Record size (power of 2 between 512B and 1M)
            - dedup: Enable deduplication (on/off)
            - encryption: Encryption algorithm (aes-128-ccm, aes-192-ccm, aes-256-ccm)
            - keylocation: Location of the encryption key
            - keyformat: Format of the encryption key (raw, hex, passphrase)
        """
        cmd = ['zfs', 'create']
        
        if 'mountpoint' in kwargs:
            cmd.extend(['-o', f'mountpoint={kwargs["mountpoint"]}'])
        if 'compression' in kwargs:
            cmd.extend(['-o', f'compression={kwargs["compression"]}'])
        if 'atime' in kwargs:
            cmd.extend(['-o', f'atime={kwargs["atime"]}'])
        if 'quota' in kwargs:
            cmd.extend(['-o', f'quota={kwargs["quota"]}'])
        if 'reservation' in kwargs:
            cmd.extend(['-o', f'reservation={kwargs["reservation"]}'])
        if 'recordsize' in kwargs:
            cmd.extend(['-o', f'recordsize={kwargs["recordsize"]}'])
        if 'dedup' in kwargs:
            cmd.extend(['-o', f'dedup={kwargs["dedup"]}'])
        if 'encryption' in kwargs:
            cmd.extend(['-o', f'encryption={kwargs["encryption"]}'])
        if 'keylocation' in kwargs:
            cmd.extend(['-o', f'keylocation={kwargs["keylocation"]}'])
        if 'keyformat' in kwargs:
            cmd.extend(['-o', f'keyformat={kwargs["keyformat"]}'])

        cmd.append(name)
        super().__init__(' '.join(cmd), exec_info)


class Mount(Exec):
    """
    Mount a filesystem
    """

    def __init__(self, source, target, exec_info=None, **kwargs):
        """
        Mount a filesystem.

        :param source: Source device, partition, or network location to mount
        :param target: Target mount point directory
        :param exec_info: Information needed to execute mount
        :param kwargs: Additional mount options:
            - type: Filesystem type (e.g., ext4, xfs, btrfs, zfs, nfs, etc.)
            - options: List of mount options or string of comma-separated options
            - bind: Create a bind mount (True/False)
            - recursive: Recursively mount filesystems from fstab (True/False)
            - read_only: Mount as read-only (True/False)
            - remount: Remount an existing mount point (True/False)
            - make_dirs: Create target directory if it doesn't exist (True/False)
        """
        if kwargs.get('make_dirs', False):
            Mkdir(target, exec_info).run()

        cmd = ['mount']
        
        # Handle bind mounts
        if kwargs.get('bind', False):
            cmd.append('--bind')
        
        # Handle recursive mounting
        if kwargs.get('recursive', False):
            cmd.append('--all')
        
        # Handle filesystem type
        if 'type' in kwargs:
            cmd.extend(['-t', kwargs['type']])
        
        # Handle mount options
        options = []
        if kwargs.get('read_only', False):
            options.append('ro')
        if kwargs.get('remount', False):
            options.append('remount')
        
        # Add user-provided options
        if 'options' in kwargs:
            if isinstance(kwargs['options'], list):
                options.extend(kwargs['options'])
            else:
                options.append(kwargs['options'])
        
        if options:
            cmd.extend(['-o', ','.join(options)])
        
        cmd.extend([source, target])
        super().__init__(' '.join(cmd), exec_info)


class Umount(Exec):
    """
    Unmount a filesystem
    """

    def __init__(self, target, exec_info=None, **kwargs):
        """
        Unmount a filesystem.

        :param target: Mount point or device to unmount
        :param exec_info: Information needed to execute umount
        :param kwargs: Additional unmount options:
            - force: Force unmount (True/False)
            - lazy: Lazy unmount (True/False)
            - recursive: Recursively unmount all filesystems under target (True/False)
            - all_types: Unmount all filesystems of specified types
            - types: List of filesystem types to unmount (used with all_types)
        """
        cmd = ['umount']
        
        if kwargs.get('force', False):
            cmd.append('--force')
        
        if kwargs.get('lazy', False):
            cmd.append('--lazy')
        
        if kwargs.get('recursive', False):
            cmd.append('--recursive')
        
        if kwargs.get('all_types', False) and 'types' in kwargs:
            if isinstance(kwargs['types'], list):
                cmd.extend(['-t', ','.join(kwargs['types'])])
            else:
                cmd.extend(['-t', kwargs['types']])
        
        cmd.append(target)
        super().__init__(' '.join(cmd), exec_info)
```

### `jarvis_util/shell/local_exec.py`

```python
"""
Provides methods for executing a program or workflow locally. This class
is intended to be called from Exec, not by general users.
"""

import time
import subprocess
import os
import sys
import io
import threading
from jarvis_util.jutil_manager import JutilManager
from .exec_info import ExecInfo, ExecType, Executable


class LocalExec(Executable):
    """
    Provides methods for executing a program or workflow locally.
    """

    def __init__(self, cmd, exec_info):
        """
        Execute a program or workflow

        :param cmd: list of commands or a single command string
        :param exec_info: Info needed to execute processes locally
        """

        super().__init__()

        # Managing console output and collection
        self.collect_output = exec_info.collect_output
        self.pipe_stdout = exec_info.pipe_stdout
        self.pipe_stderr = exec_info.pipe_stderr
        self.pipe_stdout_fp = None
        self.pipe_stderr_fp = None
        self.hide_output = exec_info.hide_output
        # pylint: disable=R1732
        if self.collect_output is None:
            self.collect_output = self.jutil.collect_output
        if self.pipe_stdout is not None:
            self.pipe_stdout_fp = open(self.pipe_stdout, 'wb')
        if self.pipe_stderr is not None:
            self.pipe_stderr_fp = open(self.pipe_stderr, 'wb')
        if self.hide_output is None:
            self.hide_output = self.jutil.hide_output
        # pylint: enable=R1732
        self.stdout = io.StringIO()
        self.stderr = io.StringIO()
        self.last_stdout_size = 0
        self.last_stderr_size = 0
        self.print_stdout_thread = None
        self.print_stderr_thread = None
        self.stop_print_worker = False
        self.exit_code = 0

        # Managing command execution
        self.start_time = time.time()
        self.timeout = exec_info.timeout
        self.sudo = exec_info.sudo
        self.stdin = exec_info.stdin
        self.exec_async = exec_info.exec_async
        self.sleep_ms = exec_info.sleep_ms
        if exec_info.cwd is None:
            self.cwd = os.getcwd()
        else:
            self.cwd = exec_info.cwd
        self.basic_env = exec_info.basic_env.copy()

        # Create the command
        cmd = self.smash_cmd(cmd, self.sudo, self.basic_env, exec_info.sudoenv)
        if exec_info.do_dbg:
            cmd = self.get_dbg_cmd(cmd, exec_info)
        self.cmd = cmd

        # Copy ENV
        self.env = exec_info.env.copy()
        for key, val in os.environ.items():
            if key not in self.env:
                self.env[key] = val

        # Execute the command
        if self.jutil.debug_local_exec:
            print(cmd)
        self._start_bash_processes()

    def _start_bash_processes(self):
        time.sleep(self.sleep_ms)
        # pylint: disable=R1732
        self.proc = subprocess.Popen(self.cmd,
                                     stdin=self.stdin,
                                     stdout=subprocess.PIPE,
                                     stderr=subprocess.PIPE,
                                     cwd=self.cwd,
                                     env=self.env,
                                     shell=True)
        # pylint: enable=R1732
        self.print_stdout_thread = threading.Thread(
            target=self.print_stdout_worker)
        self.print_stderr_thread = threading.Thread(
            target=self.print_stderr_worker)
        self.print_stdout_thread.start()
        self.print_stderr_thread.start()
        if not self.exec_async:
            self.wait()

    def wait(self):
        # self.proc.wait()
        if self.timeout:
            try:
                time.sleep(self.timeout)
                self.proc.kill()
                self.stop_print_worker = True
            except:
                self.proc.kill()
                self.stop_print_worker = True
                pass
        self.join_print_worker()
        self.set_exit_code()
        return self.exit_code

    def set_exit_code(self):
        self.exit_code = self.proc.returncode

    def get_pid(self):
        if self.proc is not None:
            return self.proc.pid
        else:
            return None

    def print_stdout_worker(self):
        while self.proc.poll() is None and not self.stop_print_worker:
            self.print_to_outputs(self.proc.stdout, self.stdout,
                                  self.pipe_stdout_fp, sys.stdout)
            time.sleep(1 / 1000)
        self.print_to_outputs(self.proc.stdout, self.stdout,
                              self.pipe_stdout_fp, sys.stdout)

    def print_stderr_worker(self):
        while self.proc.poll() is None and not self.stop_print_worker:
            self.print_to_outputs(self.proc.stderr, self.stderr,
                                  self.pipe_stderr_fp, sys.stderr)

            time.sleep(1 / 1000)
        self.print_to_outputs(self.proc.stderr, self.stderr,
                              self.pipe_stderr_fp, sys.stderr)

    def print_to_outputs(self, proc_sysout, self_sysout, file_sysout, sysout):
        # pylint: disable=W0702
        for line in proc_sysout:
            try:
                text = line.decode('utf-8')
                if not self.hide_output:
                    sysout.write(text)
                if self.collect_output:
                    self_sysout.write(text)
                    self_sysout.flush()
                if file_sysout is not None:
                    file_sysout.write(line)
            except:
                return
        # pylint: enable=W0702

    def join_print_worker(self):
        if isinstance(self.stdout, str):
            return
        self.print_stdout_thread.join()
        self.print_stderr_thread.join()
        self.stdout = self.stdout.getvalue()
        self.stderr = self.stderr.getvalue()
        if self.pipe_stdout_fp is not None:
            self.pipe_stdout_fp.close()
        if self.pipe_stderr_fp is not None:
            self.pipe_stderr_fp.close()


class LocalExecInfo(ExecInfo):
    def __init__(self, **kwargs):
        super().__init__(exec_type=ExecType.LOCAL, **kwargs)
```

### `jarvis_util/shell/mpi_exec.py`

```python
"""
This module provides methods to execute a process in parallel using the
Message Passing Interface (MPI). This module assumes MPI is installed
on the system. This class is intended to be called from Exec,
not by general users.
"""

from jarvis_util.jutil_manager import JutilManager
from jarvis_util.shell.local_exec import LocalExec
from .exec_info import ExecInfo, ExecType
from abc import abstractmethod


class MpiVersion(LocalExec):
    """
    Introspect the current MPI implementation from the machine using
    mpirun --version
    """

    def __init__(self, exec_info):
        self.cmd = 'mpiexec --version'
        super().__init__(self.cmd,
                         exec_info.mod(env=exec_info.basic_env,
                                       collect_output=True,
                                       hide_output=True,
                                       do_dbg=False))
        vinfo = self.stdout
        # print(f'MPI INFO: stdout={vinfo} stderr={self.stderr}')
        if 'mpich' in vinfo.lower():
            self.version = ExecType.MPICH
        elif 'Open MPI' in vinfo or 'OpenRTE' in vinfo:
            self.version = ExecType.OPENMPI
        elif 'Intel(R) MPI Library' in vinfo:
            # NOTE(llogan): similar to MPICH
            self.version = ExecType.INTEL_MPI
        elif 'mpiexec version' in vinfo:
            self.version = ExecType.CRAY_MPICH
        else:
            raise Exception(f'Could not identify MPI implementation: {vinfo}')


class LocalMpiExec(LocalExec):
    def __init__(self, cmd, exec_info):
        self.cmd = cmd
        self.nprocs = exec_info.nprocs
        self.ppn = exec_info.ppn
        self.hostfile = exec_info.hostfile
        self.mpi_env = exec_info.env
        if exec_info.do_dbg:
            self.base_cmd = cmd # To append to the extra processes
            self.cmd = self.get_dbg_cmd(cmd, exec_info)
        super().__init__(self.mpicmd(),
                         exec_info.mod(env=exec_info.basic_env,
                                       do_dbg=False))

    @abstractmethod
    def mpicmd(self):
        pass

class OpenMpiExec(LocalMpiExec):
    """
    This class contains methods for executing a command in parallel
    using MPI.
    """
    def mpicmd(self):
        params = [f'mpiexec']
        params.append('--oversubscribe')
        params.append('--allow-run-as-root')  # For docker
        if self.ppn is not None:
            params.append(f'-npernode {self.ppn}')
        if len(self.hostfile):
            if self.hostfile.is_subset() or self.hostfile.path is None:
                params.append(f'--host {",".join(self.hostfile.hosts)}')
            else:
                params.append(f'--hostfile {self.hostfile.path}')
        params += [f'-x {key}=\"{val}\"'
                   for key, val in self.mpi_env.items()]
        if self.cmd.startswith('gdbserver'):
            params.append(f'-n 1 {self.cmd}')
            if self.nprocs > 1:
                params.append(f': -n {self.nprocs - 1} {self.base_cmd}')
        else:
            params.append(f'-n {self.nprocs}')
            params.append(self.cmd)
        cmd = ' '.join(params)
        jutil = JutilManager.get_instance()
        if jutil.debug_mpi_exec:
            print(cmd)
        return cmd


class MpichExec(LocalMpiExec):
    """
    This class contains methods for executing a command in parallel
    using MPI.
    """

    def mpicmd(self):
        params = ['mpiexec']

        if self.ppn is not None:
            params.append(f'-ppn {self.ppn}')

        if len(self.hostfile):
            if self.hostfile.is_subset() or self.hostfile.path is None:
                params.append(f'--host {",".join(self.hostfile.hosts)}')
            else:
                params.append(f'--hostfile {self.hostfile.path}')

        params += [f'-genv {key}=\"{val}\"'
                   for key, val in self.mpi_env.items()]

        if self.cmd.startswith('gdbserver'):
            params.append(f'-n 1 {self.cmd}')
            if self.nprocs > 1:
                params.append(f': -n {self.nprocs - 1} {self.base_cmd}')
        else:
            params.append(f'-n {self.nprocs}')
            params.append(self.cmd)

        cmd = ' '.join(params)

        jutil = JutilManager.get_instance()
        if jutil.debug_mpi_exec:
            print(cmd)

        return cmd

class CrayMpichExec(LocalMpiExec):
    """
    This class contains methods for executing a command in parallel
    using MPI.
    """
    def mpicmd(self):
        params = [f'mpiexec -n {self.nprocs}']
        if self.ppn is not None:
            params.append(f'--ppn {self.ppn}')
        if len(self.hostfile):
            if self.hostfile.hosts[0] == 'localhost' and len(self.hostfile) == 1:
                pass
            elif self.hostfile.is_subset() or self.hostfile.path is None:
                params.append(f'--hosts {",".join(self.hostfile.hosts)}')
            else:
                params.append(f'--hostfile {self.hostfile.path}')
        params += [f'--env {key}=\"{val}\"'
                   for key, val in self.mpi_env.items()]
        params.append(self.cmd)
        cmd = ' '.join(params)
        jutil = JutilManager.get_instance()
        if jutil.debug_mpi_exec:
            print(cmd)
        return cmd

class MpiExecInfo(ExecInfo):
    def __init__(self, **kwargs):
        super().__init__(exec_type=ExecType.MPI, **kwargs)
```

### `jarvis_util/shell/pbs_exec.py`

```python
"""
This module provides methods to execute a process in parallel using the
Message Passing Interface (MPI). This module assumes MPI is installed
on the system. This class is intended to be called from Exec,
not by general users.
"""
from jarvis_util.shell.filesystem import Chmod
from jarvis_util.jutil_manager import JutilManager
from jarvis_util.shell.local_exec import LocalExec, LocalExecInfo
from .exec_info import ExecInfo, ExecType

class PbsExec(LocalExec):
    """
    This class contains methods for executing a command
    through the PBS scheduler
    """

    def __init__(self, cmd, exec_info):
        """
        Execute a command through qsub
        :param cmd: A command (string) to execute
        :param exec_info: Information needed by qsub
        """
        self.cmd = cmd
        self.interactive = exec_info.interactive
        self.nnodes = exec_info.nnodes
        self.system = exec_info.system
        self.filesystems = exec_info.filesystems
        self.walltime = exec_info.walltime
        self.account = exec_info.account
        self.queue = exec_info.queue
        self.env_vars = exec_info.env_vars

        self.bash_script = exec_info.bash_script

        jarvis_comma_list = ','.join(exec_info.basic_env.keys())
        if self.env_vars:
            self.env_vars = f'{self.env_vars},{jarvis_comma_list}'
        else:
            self.env_vars = jarvis_comma_list

        super().__init__(self.pbscmd(),
                         exec_info.mod(env=exec_info.basic_env))

    def generate_qsub_command(self):
        cmd = 'qsub'

        if self.interactive:
            cmd += ' -I'

        equal_map = {
            'filesystems': 'l filesystems',
            'walltime': 'l walltime',
        }

        non_equal_map ={
            'account': 'A',
            'queue': 'q',
            'env_vars' : 'v'
        }

        if self.nnodes and self.system:
            cmd += f' -l select={self.nnodes}:system={self.system}'
        elif self.nnodes:
            cmd += f' -l select={self.nnodes}'
        else:
            raise ValueError("System defined without select value.")

        for attr, option in equal_map.items():
            value = getattr(self, attr)
            if value is not None:
                cmd += f' -{option}={value}'

        for attr, option in non_equal_map.items():
            value = getattr(self, attr)
            if value is not None:
                cmd += f' -{option} {value}'

        cmd += f' -- \"{self.bash_script}\"'
        return cmd

    def pbscmd(self):

        script = ['#!/bin/bash',
                 f'{self.cmd}']

        with open(self.bash_script, mode='w', encoding='utf-8') as f:
            f.write('\n'.join(script))

        Chmod(self.bash_script, "+x")

        cmd = self.generate_qsub_command()
        jutil = JutilManager.get_instance()
        if jutil.debug_pbs:
            print(cmd)
        return cmd


class PbsExecInfo(ExecInfo):
    def __init__(self, **kwargs):
        super().__init__(exec_type=ExecType.PBS, **kwargs)
        allowed_options = ['interactive', 'nnodes', 'system', 'filesystems',
                           'walltime', 'account', 'queue', 'env_vars', 'bash_script']
        self.keys += allowed_options
        # We use output and error file from the base Exec Info
        for key in allowed_options:
            if key in kwargs:
                setattr(self, key, kwargs[key])
            else:
                setattr(self, key, None)

    @staticmethod
    def get_args():
        return [
            {
                'name': 'nnodes',
                'msg': 'The number of nodes to execute the pipeline on',
                'required': True,
                'pos': False,
                'default': 1,
                'class': 'pbs',
                'rank': 1
            },
            {
                'name': 'pbs',
                'msg': 'This is the pbs job submitter',
                'type': bool,
                'required': False,
                'pos': False,
                'default': None,
                'class': 'pbs',
                'rank': 1
            },
            {
                'name': 'pbs_host',
                'msg': 'This is the pbs job receiver (internal, never set manually)',
                'type': bool,
                'required': False,
                'pos': False,
                'default': None,
                'class': 'pbs',
                'rank': 10
            },
            {
                'name': 'system',
                'msg': 'The type of system to allocate the nodes on',
                'required': False,
                'pos': False,
                'default': 'polaris',
                'class': 'pbs'
            },
            {
                'name': 'filesystems',
                'msg': 'The filesystem to be used (e.g. home:grand)',
                'required': False,
                'pos': False,
                'default': 'home:grand',
                'class': 'pbs'
            },
            {
                'name': 'time',
                'msg': 'Maximum time allotted to the job',
                'required': False,
                'pos': False,
                'default': '00:10:00',
                'aliases': ['walltime'],
                'class': 'pbs'
            },
            {
                'name': 'account',
                'msg': 'Account used for job submission',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'pbs'
            },
            {
                'name': 'queue',
                'msg': 'Queue in which to submit the job',
                'required': False,
                'pos': False,
                'default': 'debug-scaling',
                'class': 'pbs'
            },
            {
                'name': 'interactive',
                'msg': 'Submit the job in interactive mode',
                'required': False,
                'pos': False,
                'default': False,
                'type': bool,
                'class': 'pbs'
            },
            {
                'name': 'env_vars',
                'msg': 'Environmental variables to pass through PBS. '
                       'Comma separated list of strings of the form variable or variable=value',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'pbs'
            },
            {
                'name': 'polaris',
                'msg': 'Submit using polaris',
                'required': False,
                'pos': False,
                'default': False,
                'type': bool,
                'class': 'pbs'
            },
        ]

    @staticmethod
    def from_kwargs(kwargs, script_location):
        return PbsExecInfo(
            nnodes=kwargs['nnodes'],
            system=kwargs['system'],
            filesystems=kwargs['filesystems'],
            walltime=kwargs['walltime'],
            account=kwargs['account'],
            queue=kwargs['queue'],
            interactive=kwargs['interactive'],
            bash_script=script_location
        )
```

### `jarvis_util/shell/process.py`

```python
"""
This module provides various wrappers for methods which manage processes
in the cluster. Examples include killing processes, determining whether
or not a process exists, etc.
"""

from .exec import Exec


class Kill(Exec):
    """
    Kill all processes which match the name regex.
    """

    def __init__(self, cmd, exec_info, partial=True):
        """
        Kill all processes which match the name regex.

        :param cmd: A regex for the command to kill
        :param exec_info: Info needed to execute the command
        """
        partial_cmd = "-f" if partial else ""
        super().__init__(f"pkill -9 {partial_cmd} {cmd}", exec_info)


class SetAffinity(Exec):
    """
    Set CPU affinity for a process.
    """

    def __init__(self, pid, cpu_list, exec_info):
        """
        Set CPU affinity for a specific process.

        :param pid: Process ID
        :param cpu_list: List of CPU cores to set affinity to
        :param exec_info: Info needed to execute the command
        """
        cpu_string = ",".join(map(str, cpu_list))
        super().__init__(f"taskset -pc {cpu_string} {pid}", exec_info)
```

### `jarvis_util/shell/pscp.py`

```python
"""
This module provides methods to distribute a command among multiple
nodes using SSH. This class is intended to be called from Exec,
not by general users.
"""

from .scp import Scp
from .exec_info import Executable


class Pscp(Executable):
    """
    Execute commands on multiple hosts using SSH.
    """

    def __init__(self, paths, exec_info):
        """
        Copy files to a set of remote hosts via rsync.

        Case 1: Paths is a single file:
        paths = '/tmp/hi.txt'
        '/tmp/hi.txt' will be copied to user@host:/tmp/hi.txt

        Case 2: Paths is a list of files:
        paths = ['/tmp/hi1.txt', '/tmp/hi2.txt']
        Repeat Case 1 twice.

        Case 3: Paths is a list of tuples of files:
        paths = [('/tmp/hi.txt', '/tmp/remote_hi.txt')]
        '/tmp/hi.txt' will be copied to user@host:'/tmp/remote_hi.txt'

        :param paths: Either a path to a file, a list of files, or a list of
        tuples of files.
        :param exec_info: Connection information for SSH
        """
        super().__init__()
        self.exec_async = exec_info.exec_async
        self.hosts = exec_info.hostfile.hosts
        self.scp_nodes = []
        self.stdout = {}
        self.stderr = {}
        self.hosts = exec_info.hostfile.hosts
        for host in self.hosts:
            ssh_exec_info = exec_info.mod(hostfile=None,
                                          hosts=host,
                                          exec_async=True)
            self.scp_nodes.append(Scp(paths, ssh_exec_info))
        if self.exec_async:
            self.wait()

    def wait(self):
        self.wait_list(self.scp_nodes)
        self.per_host_outputs(self.scp_nodes)
        self.set_exit_code()

    def set_exit_code(self):
        self.set_exit_code_list(self.scp_nodes)
```

### `jarvis_util/shell/pssh_exec.py`

```python
"""
This module provides methods to distribute a command among multiple
nodes using SSH. This class is intended to be called from Exec,
not by general users.
"""

from .ssh_exec import SshExec
from .local_exec import LocalExec
from .exec_info import ExecInfo, ExecType, Executable


class PsshExec(Executable):
    """
    Execute commands on multiple hosts using SSH.
    """

    def __init__(self, cmd, exec_info):
        """
        Execute commands on multiple hosts.

        :param cmd: A list of commands or a single command string
        :param exec_info: Info needed to execute command with SSH
        """
        super().__init__()
        self.exec_async = exec_info.exec_async
        self.hosts = exec_info.hostfile.hosts
        self.execs_ = []
        self.stdout = {}
        self.stderr = {}
        self.is_local = exec_info.hostfile.is_local()
        if not self.is_local:
            dbg_cmd = cmd
            if exec_info.do_dbg:
                dbg_cmd = self.get_dbg_cmd(cmd, exec_info)
            for i, host in enumerate(self.hosts):
                sshcmd = cmd
                if i == 0:
                    sshcmd = dbg_cmd
                ssh_exec_info = exec_info.mod(hostfile=None,
                                              hosts=host,
                                              exec_async=True,
                                              do_dbg=False)
                self.execs_.append(SshExec(sshcmd, ssh_exec_info))
        else:
            self.execs_.append(
                LocalExec(cmd, exec_info.mod(exec_async=True)))
        if not self.exec_async:
            self.wait()

    def wait(self):
        self.wait_list(self.execs_)
        if not self.is_local:
            self.per_host_outputs(self.execs_)
        else:
            self.stdout = {'localhost': self.execs_[0].stdout}
            self.stderr = {'localhost': self.execs_[0].stderr}
        self.set_exit_code()

    def set_exit_code(self):
        self.set_exit_code_list(self.execs_)


class PsshExecInfo(ExecInfo):
    def __init__(self, **kwargs):
        super().__init__(exec_type=ExecType.PSSH, **kwargs)
```

### `jarvis_util/shell/scp.py`

```python
"""
This module provides methods to execute a single command remotely using SSH.
This class is intended to be called from Exec, not by general users.
"""
from .local_exec import LocalExec
from .exec_info import Executable
from jarvis_util.jutil_manager import JutilManager


class _Scp(LocalExec):
    """
    This class provides methods to copy data over SSH using the "rsync"
    command utility in Linux
    """

    def __init__(self, src_path, dst_path, exec_info):
        """
        Copy a file or directory from source to destination via rsync

        :param src_path: The path to the file on the host
        :param dst_path: The desired file path on the remote host
        :param exec_info: Info needed to execute command with SSH
        """

        self.addr = exec_info.hostfile.hosts[0]
        if self.addr == 'localhost' or self.addr == '127.0.0.1':
            return
        self.src_path = src_path
        self.dst_path = dst_path
        self.user = exec_info.user
        self.pkey = exec_info.pkey
        self.port = exec_info.port
        self.sudo = exec_info.sudo
        self.jutil = JutilManager.get_instance()
        super().__init__(self.rsync_cmd(src_path, dst_path),
                         exec_info.mod(env=exec_info.basic_env))

    def rsync_cmd(self, src_path, dst_path):
        lines = ['rsync -ha']
        if self.pkey is not None or self.port is not None:
            ssh_lines = ['ssh']
            if self.pkey is not None:
                ssh_lines.append(f'-i {self.pkey}')
            if self.port is not None:
                ssh_lines.append(f'-p {self.port}')
            ssh_cmd = ' '.join(ssh_lines)
            lines.append(f'-e \'{ssh_cmd}\'')
        lines.append(src_path)
        if self.user is not None:
            lines.append(f'{self.user}@{self.addr}:{dst_path}')
        else:
            lines.append(f'{self.addr}:{dst_path}')
        rsync_cmd = ' '.join(lines)
        if self.jutil.debug_scp:
            print(rsync_cmd)
        return rsync_cmd


class Scp(Executable):
    """
    Secure copy data between two hosts.
    """

    def __init__(self, paths, exec_info):
        """
        Copy files via rsync.

        Case 1: Paths is a single file:
        paths = '/tmp/hi.txt'
        '/tmp/hi.txt' will be copied to user@host:/tmp/hi.txt

        Case 2: Paths is a list of files:
        paths = ['/tmp/hi1.txt', '/tmp/hi2.txt']
        Repeat Case 1 twice.

        Case 3: Paths is a list of tuples of files:
        paths = [('/tmp/hi.txt', '/tmp/remote_hi.txt')]
        '/tmp/hi.txt' will be copied to user@host:'/tmp/remote_hi.txt'

        :param paths: Either a path to a file, a list of files, or a list of
        tuples of files.
        :param exec_info: Connection information for SSH
        """

        super().__init__()
        self.paths = paths
        self.exec_info = exec_info
        self.scp_nodes = []
        if isinstance(paths, str):
            self._exec_single_path(paths)
        if isinstance(paths, list):
            if len(paths) == 0:
                raise Exception('Must have at least one path to scp')
            elif isinstance(paths[0], str):
                self._exec_many_paths(paths)
            elif isinstance(paths[0], tuple):
                self._exec_many_paths_tuple(paths)
            elif isinstance(paths[0], list):
                self._exec_many_paths_tuple(paths)
        if not self.exec_info.exec_async:
            self.wait()

    def _exec_single_path(self, path):
        self.scp_nodes.append(_Scp(path, path, self.exec_info))

    def _exec_many_paths(self, paths):
        for path in paths:
            self.scp_nodes.append(_Scp(path, path, self.exec_info))

    def _exec_many_paths_tuple(self, path_tlist):
        for src, dst in path_tlist:
            self.scp_nodes.append(_Scp(src, dst, self.exec_info))

    def wait(self):
        self.wait_list(self.scp_nodes)
        self.smash_list_outputs(self.scp_nodes)
        self.set_exit_code()
        return self.exit_code

    def set_exit_code(self):
        self.set_exit_code_list(self.scp_nodes)
```

### `jarvis_util/shell/slurm_exec.py`

```python
"""
This module provides methods to execute a process in parallel using the
Message Passing Interface (MPI). This module assumes MPI is installed
on the system. This class is intended to be called from Exec,
not by general users.
"""

from jarvis_util.jutil_manager import JutilManager
from jarvis_util.shell.local_exec import LocalExec, LocalExecInfo
from .exec_info import ExecInfo, ExecType


class SlurmExec(LocalExec):
    """
    This class contains methods for executing a command
    through the Slurm scheduler
    """

    def __init__(self, cmd, exec_info):
        """
        Execute a command through sbatch
        :param cmd: A command (string) to execute
        :param exec_info: Information needed by sbatch
        """
        self.cmd = cmd
        self.job_name = exec_info.job_name
        self.num_nodes = exec_info.num_nodes
        self.ppn = exec_info.ppn
        self.cpus_per_task = exec_info.cpus_per_task
        self.time = exec_info.time
        self.partition = exec_info.partition
        self.mail_type = exec_info.mail_type
        self.output = exec_info.pipe_stdout
        self.error = exec_info.pipe_stderr
        self.mem = exec_info.mem
        self.gres = exec_info.gres
        self.exclusive = exec_info.exclusive
        self.host_suffix = exec_info.host_suffix
        self.nodelist = exec_info.nodelist

        super().__init__(self.slurmcmd(),
                         exec_info.mod(env=exec_info.basic_env))

    def generate_sbatch_command(self):
        cmd = "sbatch"

        # Mapping of attribute names to their corresponding sbatch option names
        options_map = {
            'job_name': 'job-name',
            'num_nodes': 'nodes',
            'ppn': 'ntasks-per-node',
            'cpus_per_task': 'cpus-per-task',
            'time': 'time',
            'partition': 'partition',
            'mail_type': 'mail-type',
            'output': 'output',
            'error': 'error',
            'mem': 'mem',
            'gres': 'gres',
            'exclusive': 'exclusive',
            'nodelist': 'nodelist',
        }

        for attr, option in options_map.items():
            value = getattr(self, attr)
            if value is not None:
                if value is True:  # For options like 'exclusive' that don't take a value
                    cmd += f" --{option}"
                else:
                    cmd += f" --{option}={value}"

        cmd += f" {self.cmd}"
        return cmd

    def slurmcmd(self):
        cmd = self.generate_sbatch_command()
        jutil = JutilManager.get_instance()
        if jutil.debug_slurm:
            print(cmd)
        return cmd
    

class SlurmExecInfo(ExecInfo):
    def __init__(self, job_name=None, num_nodes=1, **kwargs):
        super().__init__(exec_type=ExecType.SLURM, **kwargs)
        allowed_options = ['job_name', 'num_nodes', 'cpus_per_task', 'time', 'partition', 'mail_type',
                           'mail_user', 'mem', 'gres', 'exclusive', 'host_suffix', 'nodelist', 'account']
        self.keys += allowed_options
        # We use ppn, and the output and error file from the base Exec Info
        for key in allowed_options:
            if key in kwargs:
                setattr(self, key, kwargs[key])
            else:
                setattr(self, key, None)
        self.job_name = job_name
        self.num_nodes = num_nodes

    @staticmethod
    def get_args():
        return [ 
            {
                'name': 'job_name',
                'msg': 'The name given to this job',
                'required': True,
                'pos': False,
                'default': None,
                'class': 'slurm',
                'rank': 1
            },
            {
                'name': 'nnodes',
                'msg': 'The number of nodes to execute the pipeline on',
                'required': True,
                'pos': False,
                'default': None,
                'class': 'slurm',
                'rank': 1
            },
            {
                'name': 'slurm',
                'msg': 'This is the slurm job submitter',
                'type': bool,
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm',
                'rank': 1
            },
            {
                'name': 'slurm_host',
                'msg': 'This is the slurm job receiver (internal, never set manually)',
                'type': bool,
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm',
                'rank': 10
            },
            {
                'name': 'account',
                'msg': 'The account to use for the job',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'ppn',
                'msg': 'The number of processes per node',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'cpus_per_task',
                'msg': 'Advise the Slurm controller that ensuing job will require ncpus number of processors per task',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'time',
                'msg': 'Maximum time aloted to the job',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'partition',
                'msg': 'The partition in which to allocate the nodes',
                'required': False,
                'pos': False,
                'default': 'compute',
                'class': 'slurm'
            },
            {
                'name': 'mail_type',
                'msg': 'When to email users of the status of the job',
                'required': False,
                'pos': False,
                'default': None,
                'choices': ['NONE', 'BEGIN', 'END', 'FAIL', 'REQUEUE', 'ALL'],
                'class': 'slurm'
            },
            {
                'name': 'mail_user',
                'msg': 'What email to use',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'output_file',
                'msg': 'File to write all output messages',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'error_file',
                'msg': 'File to write all error messages',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'memory',
                'msg': 'Amount of memory to request for the job',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'gres',
                'msg': 'A comma-delimited list of generic consumable resources, like gpus',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'exclusive',
                'msg': 'Request the nodes exclusively',
                'required': False,
                'pos': False,
                'default': True,
                'class': 'slurm'
            },
            {
                'name': 'host_suffix',
                'msg': 'Append suffix to all hosts in hostfile',
                'required': False,
                'pos': False,
                'default': None,
                'class': 'slurm'
            },
            {
                'name': 'nodelist',
                'msg': 'A list of nodes to run the job on, exp: ares-comp-[10-14],ares-comp-15',
                'required': False,
                'pos': False,
                'type': str,
                'default': None,
                'class': 'slurm'
            }
        ]

    @staticmethod
    def from_kwargs(kwargs):
        SlurmExecInfo(
            account=kwargs['account'],
            job_name=kwargs['job_name'],
            num_nodes=kwargs['nnodes'],
            ppn=kwargs['ppn'],
            cpus_per_task=kwargs['cpus_per_task'],
            time=kwargs['time'],
            partition=kwargs['partition'],
            mail_type=kwargs['mail_type'],
            mail_user=kwargs['mail_user'],
            pipe_stdout=kwargs['output_file'],
            pipe_stderr=kwargs['error_file'],
            mem=kwargs['memory'],
            gres=kwargs['gres'],
            exclusive=kwargs['exclusive'],
            host_suffix=kwargs['host_suffix'],
            nodelist=kwargs['nodelist']
        )


class SlurmHostfile(LocalExec):
    def __init__(self, file_location, host_suffix=None):
        self.file_location = file_location
        self.host_suffix = host_suffix
        cmd = f'scontrol show hostnames $SLURM_JOB_NODELIST > {file_location}'
        super().__init__(cmd, LocalExecInfo())
        if host_suffix is not None:
            with open(file_location, 'r', encoding='utf-8') as fp:
                lines = fp.read().splitlines()
                lines = [f'{line}{host_suffix}' for line in lines]
            with open(file_location, 'w', encoding='utf-8') as fp:
                fp.write('\n'.join(lines))
                fp.write('\n')
```

### `jarvis_util/shell/spark_exec.py`

```python
"""
This module provides methods to execute a process in parallel using the
Message Passing Interface (MPI). This module assumes MPI is installed
on the system. This class is intended to be called from Exec,
not by general users.
"""

from jarvis_util.jutil_manager import JutilManager
from jarvis_util.shell.local_exec import LocalExec
from .exec_info import ExecInfo, ExecType
from abc import abstractmethod


class SparkExec(LocalExec):
    def __init__(self, cmd, master_host, master_port,
                 driver_mem='1g', executor_mem='1g', scratch='/tmp', replication=1,
                 exec_info=None):
        master_url = f'spark://{master_host}:{master_port}'
        sparkcmd = [
            'spark-submit',
            f'--master {master_url}',
            f'--driver-memory {driver_mem}',
            f'--executor-memory {executor_mem}',
            f'--conf spark.speculation=false',
            f'--conf spark.storage.replication={replication}',
            f'--conf spark.local.dir={scratch}',
            cmd
        ]
        sparkcmd = ' '.join(sparkcmd)
        super().__init__(sparkcmd, exec_info)
```

### `jarvis_util/shell/ssh_exec.py`

```python
"""
This module provides methods to execute a single command remotely using SSH.
This class is intended to be called from Exec, not by general users.
"""
from .local_exec import LocalExec
from .exec_info import ExecInfo, ExecType


class SshExec(LocalExec):
    """
    This class provides methods to execute a command via SSH.
    """

    def __init__(self, cmd, exec_info):
        """
        Execute a command remotely via SSH

        :param cmd: A list of commands or a single command string
        :param exec_info: Info needed to execute command with SSH
        """

        self.addr = exec_info.hostfile.hosts[0]
        self.user = exec_info.user
        self.pkey = exec_info.pkey
        self.port = exec_info.port
        self.sudo = exec_info.sudo
        self.ssh_env = exec_info.env
        self.basic_env = exec_info.env
        self.strict_ssh = exec_info.strict_ssh
        self.password = False
        cmd = self.smash_cmd(cmd, self.sudo, self.basic_env, exec_info.sudoenv)
        if not exec_info.hostfile.is_local():
            super().__init__(self.ssh_cmd(cmd),
                             exec_info.mod(env=exec_info.basic_env,
                                           sudo=False))
        else:
            super().__init__(cmd, exec_info.mod(sudo=False))

    def ssh_cmd(self, cmd):
        lines = ['ssh']
        if self.pkey is not None:
            lines.append(f'-i {self.pkey}')
        if self.port is not None:
            lines.append(f'-p {self.port}')
        if not self.password:
            lines.append(f'-o PasswordAuthentication=no')
        if not self.strict_ssh:
            lines.append(f'-o StrictHostKeyChecking=no')
        if self.user is not None:
            lines.append(f'{self.user}@{self.addr}')
        else:
            lines.append(f'{self.addr}')
        ssh_cmd = ' '.join(lines)

        cmd_lines = []
        if self.ssh_env is not None:
            for key, val in self.ssh_env.items():
                cmd_lines.append(f'{key}=\'{val}\'')
        cmd_lines.append(f'\"{cmd}\"')
        env_cmd = ' '.join(cmd_lines)
        real_cmd = f'{ssh_cmd} {env_cmd}'
        return real_cmd


class SshExecInfo(ExecInfo):
    def __init__(self, **kwargs):
        super().__init__(exec_type=ExecType.SSH, **kwargs)
```

### `jarvis_util/util/__init__.py`

```python

```

### `jarvis_util/util/argparse.py`

```python
"""
This module contains an argument parser which defines
"""

import sys
import os
from abc import ABC, abstractmethod
import shlex
import yaml
from tabulate import tabulate


class PatternTree:
    def __init__(self):
        self.pattern = {}

    def add_menu(self, menu):
        alias_to = None
        if len(menu['name_toks']) == 0:
            self.pattern['__menu'] = menu
            return
        for alias_str, alias_toks in menu['aliases']:
            alias_to = self._add_menu(menu, self.pattern, alias_toks, alias_to)

    def _add_menu(self, menu, pattern, toks, alias_to):
        tok = toks[0]
        if tok not in pattern:
            if len(toks) == 1 and alias_to is not None:
                pattern[tok] = alias_to
            else:
                pattern[tok] = {}
        if len(toks) == 1:
            pattern[tok]['__menu'] = menu
            return pattern[tok]
        self._add_menu(menu, pattern[tok], toks[1:], alias_to)

    def get_default_menu(self):
        if '__menu' in self.pattern:
            return self.pattern['__menu']
        return None

    def match_pattern(self, toks):
        if len(toks) == 0 and '__menu' in self.pattern:
            return (0, self.pattern)
        return self._match_pattern(toks, self.pattern, 0)

    def _match_pattern(self, toks, pattern, depth, last_match=(0, None)):
        if len(toks) == 0:
            return last_match
        tok = toks[0]
        if tok in pattern:
            if '__menu' in pattern[tok]:
                last_match = (depth + 1, pattern[tok])
            last_match = self._match_pattern(
                toks[1:], pattern[tok], depth + 1, last_match)
        return last_match

    @staticmethod
    def get_matches(menus):
        matches = {}
        for tok, pattern in menus.items():
            if tok != '__menu' and '__menu' in pattern:
                menu = pattern['__menu']
                matches[menu['name_str']] = menu
        matches = list(matches.values())
        return matches


class ArgParse(ABC):
    """
    A class for parsing command line arguments.
        Parsed menu name stored in self.menu_name
        Parsed menu arguments stored in self.kwargs
        Parsed remaining arguments stored in self.remainder
    """

    def __init__(self, args=None, exit_on_fail=True, **custom_info):
        """
        :param args: Unparsed CLI arguments. Either a string or a list.
        :param exit_on_fail: Whether to exit the program if parsing the
        menu fails.
        """
        if args is None:
            args = sys.argv[1:]
        elif isinstance(args, str):
            args = shlex.split(args)
        self.binary_name = os.path.basename(sys.argv[0])
        self.args = args
        self.error = None
        self.exit_on_fail = exit_on_fail
        self.custom_info = custom_info
        self.menus = PatternTree()
        self.vars = {}
        self.remainder = []
        self.remainder_kv = {}
        self.pos_required = False
        self.keep_remainder = False
        self.remainder_as_kv = False

        self.needed_help = False
        self.menu = None
        self.cmd = None
        self.kwargs = {}
        self.real_kwargs = {}
        self.define_options()
        self._parse()

    @staticmethod
    def merge(*arglists):
        final = {}
        for arglist in arglists:
            for arg in arglist:
                if arg['name'] in final:
                    continue
                final[arg['name']] = arg
        return list(final.values())

    @abstractmethod
    def define_options(self):
        """
        User-defined options menu

        :return:
        """
        pass

    def process_args(self):
        """
        After args have been parsed, can call this function to process
        the arguments. Assumes that derived ArgParse class has a function
        for each menu option.

        :return: None
        """
        if self.needed_help:
            return
        func_name = self.menu_name.replace(' ', '_')
        func_name = func_name.replace('-', '_')
        if func_name == '':
            func_name = 'main_menu'
        func = getattr(self, func_name)
        func()

    def _get_alias(self, name):
        if name is not None:
            name_toks = name.split()
            name_str = ' '.join(name_toks)
            return (name_str, name_toks)
        return ('', [])

    def add_cmd(self, name=None, msg=None,
                 keep_remainder=False,
                 remainder_as_kv=False,
                 aliases=None):
        self.add_menu(name, msg,
                      keep_remainder,
                      remainder_as_kv,
                      aliases,
                      is_cmd=True)

    def add_menu(self, name=None, msg=None,
                 keep_remainder=False,
                 remainder_as_kv=False,
                 aliases=None,
                 is_cmd=False):
        """
        A menu is a container of arguments.

        :param name: The name that appears in the CLI to trigger the menu.
        Spaces indicate menu nesting. E.g., 'repo add' will trigger the
        menu argparser only if 'repo' and 'add' appear next to each other
        in the argument list.
        :param msg: The message to print if the user selects an improper menu
        in the CLI.
        :param keep_remainder: Whether or not the menu should store all
        remaining arguments for further use later.
        :param remainder_as_kv: Automatically parse the remainder as string
        type entries.
        :param rank: rank the importance of this argument to print
        :param aliases: Alternative names for this menu
        :param is_cmd: This menu represents a single command
        :return:
        """
        toks = []
        name_str, name_toks = self._get_alias(name)
        full_aliases = [(name_str, name_toks)]
        if aliases is None:
            aliases = []
        for alias in aliases:
            full_aliases.append(self._get_alias(alias))
        menu = {
                'name_str': name_str,
                'name_toks': name_toks,
                'msg': msg,
                'num_required': 0,
                'pos_opts': [],
                'kw_opts': {},
                'keep_remainder': keep_remainder,
                'remainder_as_kv': remainder_as_kv,
                'is_cmd': is_cmd,
                'aliases': full_aliases
            }
        self.menus.add_menu(menu)
        self.menu = menu

    @staticmethod
    def _default_arg_list_params(args):
        """
        Make the menu argument list contain all needed parameters.

        :param args: The set of arguments being modified
        :return:
        """
        for arg in args:
            if 'name' not in arg:
                raise Exception('Name is a required argument')
            if 'type' not in arg:
                arg['type'] = str
            if 'choices' not in arg:
                arg['choices'] = []
            if 'default' not in arg:
                arg['default'] = None
            if 'args' not in arg:
                arg['args'] = None
            if 'required' not in arg:
                arg['required'] = False
            if 'pos' not in arg:
                arg['pos'] = False
            if arg['args'] is not None:
                for list_args in arg['args']:
                    ArgParse._default_arg_list_params([list_args])

    def add_args(self, args):
        """
        Add arguments to the current menu

        menu arguments have the following parameters:
            name: The name of the argument
            type: The arg type (e.g., str, int, bool, list). Default str.
            choices: Available choices for the menu option. Default None.
            pos: Whether the argument is positional. Default false.
            required: Whether a positional argument is required. Default false.
            default: The default value of the argument. Default None.
            args: For arguments of the 'list' types, represents the
            meaning of entries in the list
            rank: The importance of this argument to print
            class: The category of option
            aliases: Alternative names for keyword arguments

        :param args: A list of argument dicts
        :return:
        """
        self.menu['pos_opts'] += [arg for arg in args
                                  if 'pos' in arg and
                                  arg['pos'] is True]
        self.menu['kw_opts'].update({arg['name']: arg for arg in args
                                     if 'pos' not in arg or
                                     arg['pos'] is False})
        for opt in self.menu['pos_opts']:
            if 'required' in opt and opt['required']:
                self.menu['num_required'] += 1
            if 'rank' not in opt:
                opt['rank'] = len(args)
            if 'class' not in opt:
                opt['class'] = None
        self.menu['kw_opts'].update({'help': {
            'name': 'help',
            'type': bool,
            'msg': 'Print help menu',
            'default': False,
            'aliases': ['h']
        }})
        for opt_name, opt in list(self.menu['kw_opts'].items()):
            if 'rank' not in opt:
                opt['rank'] = len(args)
            if 'class' not in opt:
                opt['class'] = None
            if 'aliases' in opt:
                for alias in opt['aliases']:
                    self.menu['kw_opts'][alias] = opt
        self._default_arg_list_params(self.menu['pos_opts'])
        self._default_arg_list_params(list(self.menu['kw_opts'].values()))

    def _parse(self):
        """
        Parse the CLI arguments.
            Will modify self.menu to indicate which menu is used
            Will modify self.args to create a key-value store of arguments

        :return: None.
        """
        # Parse the menu options
        self._parse_menu()
        default_args = self.default_kwargs(
            list(self.menu['kw_opts'].values()) + self.menu['pos_opts'])
        default_args.update(self.kwargs)
        self.real_kwargs = self.kwargs
        self.kwargs = default_args

    @staticmethod
    def default_kwargs(menu_args):
        """
        Pack the kwargs dictionary with default values for missing entries.

        :param menu_args: The menu argument list containing all parameters
        and their defaults.
        :return: dict
        """
        kwargs = {}
        for arg in menu_args:
            if arg['name'] == 'help':
                continue
            if arg['name'] == 'h':
                continue
            if 'default' in arg:
                kwargs[arg['name']] = arg['default']
            else:
                kwargs[arg['name']] = None
        return kwargs

    def _parse_menu(self):
        """
        Determine which menu is used in the CLI.

        :return: Modify self.menu. No return value.

        # Find the commands matching the first letter
        """
        # Identify the menu we are currently under
        self.menu = None
        # Filter out matches
        depth, menus = self.menus.match_pattern(self.args)
        # If there was nothing remotely close, try default menu
        if menus is None:
            self.menu = self.menus.get_default_menu()
        else:
            self.menu = menus['__menu']
            self.args = self.args[depth:]
        # If there was nothing at all, error now
        if self.menu is None or not self.menu['is_cmd']:
            if menus is not None:
                matches = [self.menu]
                matches += PatternTree.get_matches(menus)
            else:
                matches = []
            self._invalid_menu(matches)
        self.menu_name = self.menu['name_str']
        self.keep_remainder = self.menu['keep_remainder']
        self.remainder_as_kv = self.menu['remainder_as_kv']
        self._parse_args()

    def _parse_args(self):
        i = self._parse_pos_args()
        self._parse_kw_args(i)
        if 'h' in self.kwargs or 'help' in self.kwargs:
            self._print_help()

    def _parse_pos_args(self):
        """
        Parse positional arguments
            Modify the self.kwargs dictionary

        :return:
        """

        i = 0
        args = self.args
        menu = self.menu
        while i < len(menu['pos_opts']):
            # Get the positional arg info
            opt_name = menu['pos_opts'][i]['name']
            if i >= len(args):
                if i >= menu['num_required']:
                    break
                else:
                    self._missing_positional(opt_name)

            # Get the arg value
            opt_val = args[i]
            if self._is_kw_value(i):
                break
            opt = menu['pos_opts'][i]
            opt_val = self._convert_opt(opt, opt_val)

            # Set the argument
            self._set_opt(opt, opt_val)
            i += 1
        return i

    def _parse_kw_args(self, i):
        """
        Parse key-word arguments.
            Modify the self.kwargs dictionary

        :param i: The starting index in the self.args list where kv pairs start
        :return:
        """

        menu = self.menu
        args = self.args
        while i < len(args):
            opt_name = args[i]
            opt_val = True
            if '=' in opt_name:
                opt_name, opt_val = opt_name.split('=')
            elif opt_name == '-h':
                opt_name = 'h'
                opt_val = True
            elif opt_name == '--help':
                opt_name = 'help'
                opt_val = True
            elif opt_name.startswith('+'):
                opt_val = True
            elif opt_name.startswith('-') and not opt_name.startswith('--'):
                opt_val = False

            # Normalize opt name
            opt_name = self._get_opt_name(opt_name)

            # Verify argument is apart of the menu
            if opt_name not in menu['kw_opts']:
                if self.remainder_as_kv:
                    self.remainder_kv[opt_name] = opt_val
                    i += 1
                    continue
                elif self.keep_remainder:
                    self.remainder = args[i:]
                    return
                else:
                    self._invalid_kwarg(opt_name)

            # Get argument type
            opt = menu['kw_opts'][opt_name]

            # Convert argument to type
            opt_val = self._convert_opt(opt, opt_val)

            # Set the argument
            self._set_opt(opt, opt_val)
            i += 1

    def _set_opt(self, opt, opt_val):
        opt_name = opt['name']
        if isinstance(opt_val, list):
            if opt_name not in self.kwargs or len(opt_val) == 0:
                self.kwargs[opt_name] = opt_val
            else:
                self.kwargs[opt_name] += opt_val
        else:
            self.kwargs[opt_name] = opt_val

    def _convert_opt(self, opt, arg):
        opt_name = opt['name']
        opt_type = opt['type']
        opt_choices = opt['choices']
        opt_args = opt['args'] 
        if opt_type is not None:
            # pylint: disable=W0702
            try:
                if opt_type is list:
                    if isinstance(arg, str):
                        try:
                            arg = yaml.safe_load(arg)
                        except:
                            pass
                    if not isinstance(arg, list):
                        if arg is None:
                            arg = ''
                        elif isinstance(arg, str) and len(arg) == 0:
                            arg = ''
                        else:
                            arg = [arg]
                if isinstance(arg, list):
                    # Parse a list
                    # Verify each entry in the list matches opt_args
                    for i, entry in enumerate(arg):
                        if isinstance(entry, list):
                            new_entry = {}
                            for j, sub_entry in enumerate(entry): 
                                entry_key = opt_args[j]['name']
                                new_entry[entry_key] = self._convert_opt(opt_args[j],
                                                             sub_entry)
                            arg[i] = new_entry
                        elif isinstance(entry, dict):
                            for j, opt_arg in enumerate(opt_args):
                                if opt_arg['name'] in entry:
                                    entry[opt_arg['name']] = self._convert_opt(
                                        opt_arg, entry[opt_arg['name']])
                        else:
                            arg[i] = self._convert_opt(
                                opt_args[0], entry)
                elif opt_type is bool and isinstance(arg, str):
                    arg = yaml.safe_load(arg)
                else:
                    # Parse a simple type
                    if arg == '' and opt['default'] is None and not opt['required']:
                        arg = None
                    else:
                        arg = opt_type(arg)
                # Verify the opt matches the available choices
                if opt_choices is not None and len(opt_choices):
                    if arg not in opt_choices:
                        self._invalid_choice(opt_name, arg)
            except:
                self._invalid_type(opt_name, opt_type)
            # pylint: enable=W0702
        return arg

    def _is_kw_value(self, i):
        """
        Check if the argument at position i is a kwopt

        :param i:
        :return:
        """
        if i >= len(self.args):
            return False
        opt_name = self.args[i]
        if '=' in opt_name:
            return True
        if opt_name.startswith('+'):
            return True
        if opt_name.startswith('-'):
            return True
        return self._get_opt_name(opt_name) in self.menu['kw_opts']

    def _get_opt_name(self, opt_name):
        """
        Normalize option names
            '--with-' and '--no-' are removed
            '+' and '-' are removed

        :param opt_name: The menu option name
        :param is_bool_arg: Whether the arg is a boolean arg
        :return:
        """
        opt_name = opt_name.replace('--with-', '')
        opt_name = opt_name.replace('--no-', '')
        opt_name = opt_name.replace('+', '')
        opt_name = opt_name.replace('-', '')
        return opt_name

    def _invalid_menu(self, matches):
        self._print_error('', matches=matches)

    def _invalid_choice(self, opt_name, arg):
        self._print_menu_error(f'{opt_name}={arg} is not a valid choice')

    def _missing_positional(self, opt_name):
        self._print_menu_error(f'{opt_name} was required, but not defined')

    def _invalid_kwarg(self, opt_name):
        self._print_menu_error(f'{opt_name} is not a valid key-word argument')

    def _invalid_kwarg_default(self, opt_name):
        self._print_menu_error(
            f'{opt_name} was not given a value, but requires one')

    def _invalid_type(self, opt_name, opt_type):
        self._print_menu_error(f'{opt_name} was not of type {opt_type}')

    def _print_menu_error(self, msg):
        self._print_error(f'In the menu {self.menu["name_str"]}, {msg}')

    def _print_error(self, msg,
                     matches=None):
        if len(msg):
            print(f'{msg}')
        self._print_help(matches)
        if self.exit_on_fail:
            sys.exit(1)
        else:
            raise Exception(msg)

    def _print_help(self,
                    matches=None):
        self.needed_help = True
        if matches is None:
            self._print_menu_help()
        else:
            self._print_menus(matches)

    def _print_menus(self, matches):
        """
        Print a set of menus that were closest to the user's input

        :param matches: The set of menu matches
        :return:
        """
        if len(matches) == 0:
            menus = []
            if len(self.menus.pattern):
                menus = PatternTree.get_matches(self.menus.pattern)
            for menu in menus:
                self.menu = menu
                self._print_menu_help(True, max_len=1)
        else:
            for menu in matches:
                self.menu = menu
                self._print_menu_help(True)

    def _print_menu_help(self, only_usage=False, alias=None, max_len=100):
        if self.menu is None:
            return
        if not self.menu['is_cmd']:
            title = 'MENU'
            for alias_str, alias_toks in self.menu['aliases']:
                print(f'{title}: {self.binary_name} {alias_str}')
                title = 'ALIAS'
            if self.menu['msg'] is not None:
                print(f'BRIEF: {self.menu["msg"]}')
            print()
            return
        else:
            # Print usage menu
            pos_args = []
            for arg in self.menu['pos_opts']:
                if arg['required']:
                    pos_args.append(f'[{arg["name"]}]')
                else:
                    pos_args.append(f'[{arg["name"]} (opt)]')
            pos_args = ' '.join(pos_args)
            title = 'COMMAND'
            for alias_str, alias_toks in self.menu['aliases']:
                menu_str = alias_str
                if len(self.menu['kw_opts']):
                    print(f'{title}: {self.binary_name} {menu_str} {pos_args} ...')
                else:
                    print(f'{title}: {self.binary_name} {menu_str} {pos_args}')
                title = 'ALIAS'
            if self.menu['msg'] is not None:
                print(f'BRIEF: {self.menu["msg"]}')
            print()
        if only_usage:
            return

        # Get pos + kw opts and filter out aliases
        all_opts = (self.menu['pos_opts'] +
                    [opt
                     for name, opt in self.menu['kw_opts'].items()
                     if name == opt['name']])

        # Group options into classes
        all_class_opts = {}
        for opt in all_opts:
            if opt['class'] is None:
                opt['class'] = ''
            if opt['class'] not in all_class_opts:
                all_class_opts[opt['class']] = [opt]
            else:
                all_class_opts[opt['class']] += [opt]
        all_class_opts = list(all_class_opts.items())
        all_class_opts.sort()

        # Print each option class
        headers = ['Name', 'Default', 'Type', 'Description']
        for class_name, class_opts in all_class_opts:
            table = []
            print(f'Option Class: {class_name}')
            class_opts.sort(key=lambda opt: opt['rank'])
            for arg in class_opts:
                default = arg['default'] if 'default' in arg else None
                names = [arg['name']]
                if 'aliases' in arg:
                    names += list(arg['aliases'])
                names.sort()
                name_set = ','.join(names)
                table.append(
                    [name_set, default, self._get_type(arg), arg['msg']])
            print(tabulate(table, headers=headers, tablefmt="simple"))
            print()

    def _get_type(self, arg):
        if arg['type'] == list:
            return str([self._get_type(subarg) for subarg in arg['args']])
        else:
            return str(arg['type']).split("'")[1]

    @staticmethod
    def _calculate_column_widths(fractions):
        terminal_width = os.get_terminal_size().columns
        total_fractions = sum(fractions)
        return [int(terminal_width * (fraction / total_fractions)) for fraction
                in fractions]
```

### `jarvis_util/util/expand_env.py`

```python
"""
This module contains functions for expanding environment variables for
dictionaries
"""

import os


def expand_env(data):
    """
    Expand environment variables for dictionaries

    :param data: A dict where strings may contain environment variables to
    expand
    :return:
    """
    if isinstance(data, str):
        return os.path.expandvars(data)
    if isinstance(data, dict):
        for key, val in data.items():
            data[key] = expand_env(val)
    if isinstance(data, (list, tuple)):
        for i, val in enumerate(data):
            data[i] = expand_env(val)
    return data
```

### `jarvis_util/util/hostfile.py`

```python
"""
This module contains methods for parsing hostfiles and storing hosts
"""

import os
import socket
import re
import itertools


class Hostfile:
    """
    Parse a hostfile or store a set of hosts passed in manually.
    """

    def __init__(self, hostfile=None, path=None, all_hosts=None, all_hosts_ip=None,
                 text=None, find_ips=True):
        """
        Constructor. Parse hostfile or store existing host list.

        :param hostfile: The path to the hostfile
        :param path: The path to the hostfile (alias to the above)
        :param all_hosts: a list of strings representing all hostnames
        :param all_hosts_ip: a list of strings representing all host IPs
        :param text: Text of a hostfile
        :param find_ips: Whether to construct host_ip and all_host_ip fields
        """
        self.hosts_ip = []
        self.hosts = []
        self.all_hosts = []
        self.all_hosts_ip = []
        self.path = None
        if hostfile:
            self.path = hostfile
        elif path:
            self.path = path
        self.find_ips = find_ips

        # Set the host ips directly
        if all_hosts_ip is not None:
            self.all_hosts_ip = all_hosts_ip
            self.hosts_ip = all_hosts_ip
            self.find_ips = False

        # Direct constructor
        if all_hosts is not None:
            self._set_hosts(all_hosts)

        # From hostfile path
        elif self.path is not None:
            self.path = os.path.abspath(self.path)
            self._load_hostfile(self.path)

        # From hostfile text
        elif text is not None:
            self.parse(text)

        # Both hostfile and hosts are None
        else:
            self._set_hosts(['localhost'])

    def _load_hostfile(self, path):
        """
        Expand a hostfile

        :param path: the path to the hostfile
        :return:
        """
        if not os.path.exists(path):
            print(f'Warning: hostfile not found: {path}')
            return self
        self.path = path
        with open(path, 'r', encoding='utf-8') as fp:
            text = fp.read()
            self.parse(text)
        return self

    def parse(self, text):
        """
        Parse a hostfile text.

        :param text: Hostfile text
        :param set_hosts: Whether or not to set hosts
        :return: None
        """

        lines = text.strip().splitlines()
        hosts = []
        for line in lines:
            line = line.strip()
            if len(line) == 0 or line[0] == '#':
                continue
            self._expand_line(hosts, line)
        self._set_hosts(hosts)

    def _expand_line(self, hosts, line):
        """
        Will expand brackets in a host declaration.
        E.g., host-[0-5,...]-name

        :param hosts: the current set of hosts
        :param line: the line to parse
        :return: None
        """
        toks = re.split(r'[\[\]]', line)
        brkts = [tok for i, tok in enumerate(toks) if i % 2 == 1]
        num_set = []

        # Get the expanded set of numbers for each bracket
        for i, brkt in enumerate(brkts):
            num_set.append([])
            self._expand_set(num_set[-1], brkt)

        # Expand the host string
        host_nums = self._product(num_set)
        for host_num in host_nums:
            host = []
            for i, tok in enumerate(toks):
                if i % 2 == 1:
                    host.append(host_num[int(i/2)])
                else:
                    host.append(tok)
            hosts.append(''.join(host))

    def _expand_set(self, num_set, brkt):
        """
        Expand a bracket set.
        The bracket initially has notation: [0-5,0-9,...]
        """

        rngs = brkt.split(',')
        for rng in rngs:
            self._expand_range(num_set, rng)

    def _expand_range(self, num_set, brkt):
        """
        Expand a range.
        The range has notation: A-B or A

        :param num_set: the numbers in the range
        :param brkt:
        :return:
        """
        if len(brkt) == 0:
            return
        if '-' in brkt:
            min_max = brkt.split('-')
            if len(min_max[0]) == len(min_max[1]):
                nums = range(int(min_max[0]), int(min_max[1]) + 1)
                num_set += [str(num).zfill(len(min_max[0])) for num in nums]
            else:
                nums = range(int(min_max[0]), int(min_max[1]) + 1)
                num_set += [str(num) for num in nums]
        else:
            num_set.append(brkt)

    def _product(self, num_set):
        """
        Return the cartesian product of the number set

        :param num_set: The numbers to product
        :return:
        """
        return list(itertools.product(*num_set))

    def _set_hosts(self, all_hosts):
        self.all_hosts = all_hosts
        if self.find_ips:
            self.all_hosts_ip = [socket.gethostbyname(host)
                                 for host in all_hosts]
        self.hosts = self.all_hosts
        if self.find_ips:
            self.hosts_ip = self.all_hosts_ip
        return self

    def subset(self, count):
        sub = Hostfile()
        sub.path = self.path
        sub.all_hosts = self.all_hosts
        sub.all_hosts_ip = self.all_hosts_ip
        sub.hosts = self.hosts[:count]
        sub.hosts_ip = self.hosts_ip[:count]
        return sub

    def copy(self):
        return self.subset(len(self))

    def is_subset(self):
        return len(self.hosts) != len(self.all_hosts)

    def is_local(self):
        """
        Whether this file contains only 'localhost'

        :return: True or false
        """
        if len(self) == 0:
            return True
        if len(self.hosts) == 1:
            if self.hosts[0] == 'localhost':
                return True
            if self.hosts[0] == socket.gethostbyname('localhost'):
                return True
        if len(self.hosts_ip) == 1:
            if self.hosts_ip[0] == socket.gethostbyname('localhost'):
                return True
        return False

    def save(self, path):
        self.all_hosts = self.hosts
        self.all_hosts_ip = self.hosts_ip
        self.path = path
        with open(path, 'w', encoding='utf-8') as fp:
            fp.write('\n'.join(self.all_hosts))
        return self

    def list(self):
        return [Hostfile(all_hosts=[host]) for host in self.hosts]

    def enumerate(self):
        return enumerate(self.list())

    def host_str(self, sep=','):
        return sep.join(self.hosts)

    def ip_str(self, sep=','):
        return sep.join(self.hosts_ip)

    def __len__(self):
        return len(self.hosts)

    def __getitem__(self, idx):
        return self.hosts[idx]

    def __str__(self):
        return str(self.hosts)

    def __repr__(self):
        return str(self)

    def __eq__(self, other):
        return (self.hosts == other.hosts and
                self.all_hosts == other.all_hosts)
```

### `jarvis_util/util/import_all.py`

```python
"""
This file contains methods to automate large import __init__.py files
"""

import pathlib
import os


def _import_recurse(root_path, root, stmts):
    """
    Identify the set of files in the current "root" directory

    :param root_path: The path to the root of the python package
    :param root: The current subdirectory of the python package
    :param stmts: The current set of import statements
    :return:
    """
    for file in os.listdir(root):
        file = os.path.join(root, file)
        if os.path.isfile(file):
            file = os.path.relpath(file, root_path)
            ext = file.split('.')
            if ext[-1] == 'py':
                toks = ext[0].split('/')
                if toks[-1] == '__init__':
                    continue
                import_stmt = '.'.join(toks)
                stmts.append(f'from {import_stmt} import *')
        elif os.path.isdir(file):
            _import_recurse(root_path, file, stmts)
    return stmts


def import_all(root_path, root):
    """
    Create all import statement to do: from root import *.

    :param root_path: The root of the python repo
    :param root: The current directory we are in within the repo
    :return:
    """
    stmts = []
    _import_recurse(root_path, root, stmts)
    return '\"\"\"Import all modules\"\"\"\n' + '\n'.join(stmts) + '\n'


def build_global_import_file(root_path, pkg_name):
    """
    Build a file to be able to do: from pkg_name import *

    :param root_path: The path to the python package's root directory
    :param pkg_name: The name of the python package
    :return:
    """
    path = os.path.join(root_path, pkg_name)
    imports = import_all(root_path, path)
    with open(os.path.join(path, '__init__.py'), 'w',
              encoding='utf-8') as fp:
        fp.write(imports)


def build_global_import_from_bin(pkg_name):
    """
    Build a file to be able to do: from pkg_name import *
    This function is assumed to be called in the "bin" directory
    of the main python repo

    :param pkg_name: The name of the python package being built
    :return:
    """
    root_path = str(pathlib.Path(__file__).parent.parent.parent.resolve())
    print(root_path)
    build_global_import_file(root_path, pkg_name)
```

### `jarvis_util/util/import_mod.py`

```python
"""
This file contains helper methods to load a class dynamically from a file
"""

import sys, os

# NOTE(llogan): To get the path of the directory this file is in, use
# str(pathlib.Path(__file__).parent.resolve())


def load_class(import_str, path, class_name):
    """
    Loads a class from a python file.

    :param import_str: A python import string. E.g., for "myrepo.dir1.pkg"
    :param path: The absolute path to the directory which contains the
    beginning of the import statement. Let's say you have a git repo located
    at "/home/hello/myrepo". The git repo has a subdirectory called "myrepo",
    so "/home/hello/myrepo/myrepo". In this case, path would be
    "/home/hello/myrepo". The import string "myrepo.dir1.pkg" will find
    the "myrepo" part of the import string at "/home/hello/myrepo/myrepo".
    :param class_name: The name of the class in the file
    :return: The class data type
    """
    fullpath = os.path.join(path, import_str.replace('.', '/') + '.py')
    if not os.path.exists(fullpath):
        return None
    sys.path.insert(0, path)
    module = __import__(import_str, fromlist=[class_name])
    cls = getattr(module, class_name)
    sys.path.pop(0)
    return cls
```

### `jarvis_util/util/logging.py`

```python
from enum import Enum

class Color(Enum):
    BLACK = "\033[30m{}\033[0m"
    RED = "\033[31m{}\033[0m"
    GREEN = "\033[32m{}\033[0m"
    YELLOW = "\033[33m{}\033[0m"
    BLUE = "\033[34m{}\033[0m"
    MAGENTA = "\033[35m{}\033[0m"
    CYAN = "\033[36m{}\033[0m"
    WHITE = "\033[37m{}\033[0m"
    BRIGHT_BLACK = "\033[90m{}\033[0m"
    BRIGHT_RED = "\033[91m{}\033[0m"
    BRIGHT_GREEN = "\033[92m{}\033[0m"
    BRIGHT_YELLOW = "\033[93m{}\033[0m"
    BRIGHT_BLUE = "\033[94m{}\033[0m"
    BRIGHT_MAGENTA = "\033[95m{}\033[0m"
    BRIGHT_CYAN = "\033[96m{}\033[0m"
    BRIGHT_WHITE = "\033[97m{}\033[0m"

class ColorPrinter:
    @staticmethod
    def print(msg, color=None, file=None):
        if color is not None:
            print(color.value.format(msg), file=file)
        else:
            print(msg, file=file)
```

### `jarvis_util/util/naming.py`

```python
"""
This module contains methods to create strings which follow a particular
naming convention.
"""

import re


def to_camel_case(string):
    """
    Convert a string in snake case to camel case

    :param string:
    :return:
    """
    if string is None:
        return
    words = re.sub(r'(_|-)+', ' ', string).split()
    words = [word.capitalize() for word in words]
    return ''.join(words)


def to_snake_case(string):
    """
    Convert a string in CamelCase to snake case
    :param string:
    :return:
    """
    if string is None:
        return
    words = re.split('([A-Z][a-z0-9_]*)', string)
    words = [word for word in words if len(word)]
    string = '_'.join(words)
    return string.lower()
```

### `jarvis_util/util/size_conv.py`

```python
"""
This module provides methods to convert a semantic size string to an integer.
"""


class SizeConv:
    """
    A class which provides methods to convert a semantic size string to an int.
    """

    @staticmethod
    def to_int(text):
        if not isinstance(text, str):
            return int(text)
        text = text.lower()
        if 'k' in text:
            return SizeConv.kb(text)
        if 'm' in text:
            return SizeConv.mb(text)
        if 'g' in text:
            return SizeConv.gb(text)
        if 't' in text:
            return SizeConv.tb(text)
        if 'p' in text:
            return SizeConv.pb(text)
        return int(text)

    @staticmethod
    def kb(num):
        return int(float(num.split('k')[0]) * (1 << 10))

    @staticmethod
    def mb(num):
        return int(float(num.split('m')[0]) * (1 << 20))

    @staticmethod
    def gb(num):
        return int(float(num.split('g')[0]) * (1 << 30))

    @staticmethod
    def tb(num):
        return int(float(num.split('t')[0]) * (1 << 40))

    @staticmethod
    def pb(num):
        return int(float(num.split('p')[0]) * (1 << 50))
```

### `jarvis_util/util/small_df.py`

```python
"""
This module provides a simple database implementation which stored
and saved in a human-readable format.
"""
from jarvis_util.serialize.yaml_file import YamlFile
# from jarvis_util.util.import_mod import load_class
import copy
import yaml


class SmallDf:
    """
    This class provides a simple database implementation which stored
    and saved in a human-readable format.

    :param rows: List[Dict] of entries
    :param columns: List or string of columns
    destroying columns by accident
    """
    def __init__(self, rows=None, columns=None):
        self.rows = []
        self.columns = []
        if columns is not None:
            self.set_columns(columns)
        if rows is not None:
            self.concat(rows)
        if columns is None:
            self.infer_columns()

    def concat(self, df):
        """
        Concatenate a dataframe (or records) to this one
        """
        if len(df) == 0:
            return self
        if isinstance(df, SmallDf):
            self.rows += df.rows
            self.add_columns(df.columns)
        elif isinstance(df, list):
            rows = df
            if not isinstance(rows[0], dict):
                rows = [{col: row[i] for i, col in enumerate(self.columns)}
                        for row in rows]
            self.rows += rows
        self._correct_rows()
        return self

    def drop_duplicates(self):
        """
        Remove duplicate entries
        Modifies in place
        """
        dedup = self._drop_duplicates(self.rows)
        self.rows.clear()
        self.rows += dedup
        return self

    def _drop_duplicates(self, rows):
        dedup = list(set(self._fixed_dict(rows)))
        return self._mutable_dict(dedup)

    def _fixed_dict(self, rows):
        return tuple(tuple((key, row[key]) for key in self.columns) for row in rows)

    def _mutable_dict(self, rows):
        # return [{key:val for key, val in row} for row in rows]
        return [dict(row) for row in rows]

    def set_columns(self, columns):
        """
        Define the set of columns manually, without intrsopection

        :param columns: the list of columns
        :return: self
        """
        if not isinstance(columns, (list, tuple)):
            columns = [columns]
        self.columns = columns
        self._correct_rows()
        return self

    def infer_columns(self, rows=None):
        """
        Infer columns based on the rows

        :return: None
        """
        if rows is None:
            rows = self.rows
        for row in rows:
            self.add_columns(list(row.keys()))

    def add_columns(self, columns):
        """
        Add columns to the table. New columns will be appended to the
        column list.

        :param columns: the set of columns to add
        :return: self
        """
        if columns is None:
            return self
        if not isinstance(columns, (list, tuple)):
            columns = [columns]
        new_cols = [col for col in columns if col not in self.columns]
        self.columns += new_cols
        self._correct_rows()
        return self

    def drop_columns(self, columns):
        """
        Remove columns from the table

        :param columns: The columns to remove
        :return: self
        """
        if not isinstance(columns, (list, tuple, set)):
            columns = [columns]
        if len(columns) == 0:
            return
        self.columns = [col for col in self.columns if col not in columns]
        self._correct_rows()
        return self

    def rename(self, columns):
        """
        Rename a set of columns

        :param columns: New column names. Dict[OrigName, NewName]
        :return: self
        """
        for i, col in enumerate(self.columns):
            if col in columns:
                self.columns[i] = col
        for row in self.rows:
            for old_name, new_name in columns.items():
                row[new_name] = row.pop(old_name)
        return self

    def merge(self, other, on=None):
        """
        Merge this dictionary with another
        Returns a copy of the dataframe

        :param other: The other SmallDf
        :param on: The set of columns to merge on
        :return: SmallDf
        """
        if on is None:
            on = set(self.columns) & set(other.columns)
        if len(on) == 0:
            return SmallDf()
        rows = []
        for row in self.rows:
            for orow in other.rows:
                if all(row[col] == orow[col] for col in on):
                    merge_row = {}
                    merge_row.update(copy.deepcopy(row))
                    merge_row.update(copy.deepcopy(orow))
                    rows.append(merge_row)
                    orow['$#matched'] = True
                    row['$#matched'] = True
        rows += self._find_unmatched(self.rows)
        rows += self._find_unmatched(other.rows)
        for row in rows:
            if '$#matched' in row:
                del row['$#matched']
            else:
                for col in self.columns:
                    if col not in row:
                        row[col] = None
        return SmallDf(rows=rows)

    def _find_unmatched(self, orig_rows):
        unmatched = []
        for row in orig_rows:
            if '$#matched' not in row:
                unmatched.append(row)
        return unmatched

    def match(self, func):
        """
        Identify a subset of rows matching the query

        :param func: A function which takes as input a row and returns bool
        :return: a list of booleans
        """
        return [func(row) for row in self.rows]

    def loc(self, *idxer):
        """
        Identify a subset of rows
        A subset of the dataset is returned
        Values of the original dataframe can be modified

        :param idxer: A row, col selector
        :return: SmallDf
        """
        func, columns = self._query_args(*idxer)
        rows = self.rows
        if func is not None:
            rows = [row for row in rows if func(row)]
        self.add_columns(columns)
        if columns is None:
            columns = self.columns
        df = SmallDf(rows=rows, columns=columns)
        return df

    def _query_args(self, *idxer):
        """
        Parse arguments for querying

        :param idxer: An indexer tuple
        :return:
        """
        if len(idxer) == 1:
            idxer = idxer[0]
            if callable(idxer):
                return idxer, None
            elif isinstance(idxer, (list, tuple, str)):
                return None, idxer
            elif isinstance(idxer, slice):
                return None, None
        if len(idxer) == 2:
            if isinstance(idxer[1], (list, tuple, str)):
                columns = idxer[1]
            elif isinstance(idxer[1], slice):
                columns = None
            else:
                raise Exception('Invlaid parameters to loc')
            if callable(idxer[0]):
                func = idxer[0]
            elif isinstance(idxer[0], slice):
                func = None
            else:
                raise Exception('Invlaid parameters to loc')
            return func, columns
        raise Exception('Invlaid parameters to loc')

    def apply(self, func):
        """
        Apply a function to all rows
        Modifies the dataframe in-place.

        :param func: A lambda which takes as input row + col
        :return: None
        """
        for row in self.rows:
            for col in self.columns:
                row[col] = func(row, col)
        return self

    def fillna(self, val):
        """
        Fill None values with a new value

        :param val: The new default value
        :return: self
        """
        self.apply(lambda r, c: val if r[c] is None else r[c])
        return self

    def unique(self):
        """
        Get unique values

        :return: SmallDf
        """
        df = self.copy()
        df.drop_duplicates()
        return df

    def list(self):
        """
        Convert dataframe to a list of record values
        :return: List of records
        """
        if len(self.columns) > 1:
            return [[row[col] for col in self.columns] for row in self.rows]
        elif len(self.columns) == 1:
            col = list(self.columns)[0]
            return [row[col] for row in self.rows]
        else:
            return []

    def sort_values(self, col):
        """
        Sort the dataframe by a column

        :param col: The column to sort by
        :return: self
        """
        self.rows.sort(key=lambda x: x[col])
        return self

    def groupby(self, columns):
        """
        Group by a combo of columns

        :param columns: the set of columns to group by
        :return: SmallGroupBy
        """
        # smallgrpby = load_class('jarvis_util.util.small_df',
        # '', 'SmallGroupBy')
        return SmallGroupBy(columns, self.rows)

    def __getitem__(self, idxer):
        """
        Analagous to loc

        :param idxer: A row, col selector
        :return: SmallDf
        """
        if isinstance(idxer, tuple):
            return self.loc(*idxer)
        else:
            return self.loc(idxer)

    def __setitem__(self, idxer, other):
        """
        Subsets the dataset and then assigns a value to the subset

        :param idxer: A row, col selector
        :return: SmallDf
        """
        if isinstance(idxer, tuple):
            df = self.loc(*idxer)
        else:
            df = self.loc(idxer)
        if isinstance(other, SmallDf):
            if len(df.rows) != len(other.rows):
                raise Exception('Number of rows in dfs different')
            if len(df.columns) != len(other.columns):
                raise Exception('Column names do not match')
            for row, orow in zip(df.rows, other.rows):
                for col, ocol in zip(df.columns, other.columns):
                    row[col] = orow[ocol]
        else:
            for row in df.rows:
                for col in df.columns:
                    row[col] = other

    def _op(self, other, func):
        """
        Apply an arithmetic op

        :param other: Other SmallDf
        :param func: The operation to perform
        :return: SmallDf
        """
        if isinstance(other, SmallDf):
            if len(self.rows) != len(other.rows):
                raise Exception('Number of rows in dfs different')
            if len(self.columns) != len(other.columns):
                raise Exception('Column names do not match')
            rows = [{col: func(row, col, orow, ocol)
                     for col, ocol in zip(self.columns, other.columns)}
                    for row, orow in zip(self.rows, other.rows)]
        else:
            rows = [{col: row[col] + other for col in self.columns}
                    for row in self.rows]
        return SmallDf(rows=rows, columns=self.columns)

    def _opeq(self, other, func):
        """
        Apply an arithmetic op in-place

        :param other: Other SmallDf
        :param func: The operation to perform
        :return: SmallDf
        """
        df = self._op(other, func)
        for row, orow in zip(self.rows, df.rows):
            for col in df.columns:
                row[col] = orow[col]
        return self
    
    def __contains__(self, row):
        """
        Check if a row is in the dataframe

        :param row: The row to check
        :return: bool
        """
        return row in self.rows

    def __add__(self, other):
        return self._op(other,
                        lambda row, col, orow, ocol: row[col] + orow[ocol])

    def __iadd__(self, other):
        return self._opeq(other,
                          lambda row, col, orow, ocol: row[col] + orow[ocol])

    def __sub__(self, other):
        return self._op(other,
                        lambda row, col, orow, ocol: row[col] - orow[ocol])

    def __isub__(self, other):
        return self._opeq(other,
                          lambda row, col, orow, ocol: row[col] + orow[ocol])

    def __mul__(self, other):
        return self._op(other,
                        lambda row, col, orow, ocol: row[col] * orow[ocol])

    def __imul__(self, other):
        return self._opeq(other,
                          lambda row, col, orow, ocol: row[col] + orow[ocol])

    def __truediv__(self, other):
        return self._op(other,
                        lambda row, col, orow, ocol: row[col] / orow[ocol])

    def __itruediv__(self, other):
        return self._opeq(other,
                          lambda row, col, orow, ocol: row[col] + orow[ocol])

    def __len__(self):
        """
        Length of this df (# rows)

        :return: int
        """
        return len(self.rows)

    def _correct_rows(self):
        """
        Ensure that all rows have the same columns
        :return: None
        """
        for row in self.rows:
            self._correct_row(row)

    def _correct_row(self, row):
        """
        Ensure that a particular row has all columns

        :param row: The row to correct (Dict)
        :return: None
        """
        for col in self.columns:
            if col not in row:
                row[col] = None

    def to_yaml(self, path):
        """
        Save to YAML

        :param path: Output path
        :return:
        """
        YamlFile(path).save(self.rows)

    def load_yaml(self, path):
        """
        Load from YAML

        :param path: The input YAML file
        :return:
        """
        self.rows = YamlFile(path).load()

    def to_string(self):
        return yaml.dump(self.copy().rows)

    def __str__(self):
        return self.to_string()

    def __repr__(self):
        return self.to_string()

    def copy(self):
        # rows = [{col: row[col] for col in self.columns} for row in self.rows]
        rows = [[row[col] for col in self.columns ] for row in self.rows]
        df = SmallDf(rows=rows, columns=self.columns)
        return df


def concat(dfs):
    """
    Concat a list of dfs

    :param dfs: A list or single SmallD
    :return: SmallDf
    """
    if dfs is None:
        return
    if not isinstance(dfs, (list, tuple, set)):
        dfs = [dfs]
    if len(dfs) < 1:
        return
    new_df = SmallDf()
    for df in dfs:
        new_df = new_df.concat(df)
    return new_df


def merge(dfs, on=None, how=None):
    """
    Merge a set of dfs

    :param dfs: A list of dataframes to merge
    :param on: The columns to merge on
    :param how: The merge type. Only None & outer is supported
    :return: SmallDf
    """
    if how is not None and how != 'outer':
        raise Exception('Only outer merge supported')
    if dfs is None:
        return
    if not isinstance(dfs, (list, tuple, set)):
        dfs = [dfs]
    if len(dfs) <= 1:
        return
    base_df = dfs[0]
    for df in dfs[1:]:
        base_df = base_df.merge(df, on=on)
    return base_df


class SmallGroupBy:
    """
    This class groups a df based on columns
    """
    def __init__(self, columns=None, rows=None):
        self.groups = {}
        self.columns = []
        if columns is None and rows is None:
            return
        if isinstance(columns, str):
            self.columns = [columns]
        else:
            self.columns = columns
        for row in rows:
            key = tuple(row[col] for col in self.columns)
            if key not in self.groups:
                self.groups[key] = []
            self.groups[key].append(row)
        for key in self.groups:
            self.groups[key] = SmallDf(rows=self.groups[key])

    def reset_index(self):
        """
        Expand the groupby into a SmallDf

        :return: None
        """
        rows = []
        for grp_df in self.groups.values():
            rows += grp_df.rows
        return SmallDf(rows=rows)

    def filter(self, func):
        """
        Keep only elements meeting the condition

        :param func: A function which takes as input a row and returns bool
        :return: SmallGroupBy
        """
        grp = SmallGroupBy()
        for key, grp_df in self.groups.items():
            grp.groups[key] = SmallDf(
                rows=[row for row in grp_df.rows if func(row)])
        return grp

    def filter_groups(self, func):
        """
        Keep only groups meeting the condition

        :param func: A function which takes as input SmallDf and returns bool
        :return: SmallGroupBy
        """
        grp = SmallGroupBy()
        for key, grp_df in self.groups.items():
            if func(grp_df):
                grp.groups[key] = grp_df
        return grp

    def first(self):
        """
        Get the first element in each group

        :return: SmallGroupBy
        """
        return self.head(1)

    def head(self, n):
        """
        Get the first "n" elements in each group

        :param n: number of elements per-group
        :return:
        """
        grp = SmallGroupBy()
        for key, grp_df in self.groups.items():
            grp.groups[key] = SmallDf(rows=grp_df.rows[0:n])
        return grp

    def __len__(self):
        """
        Get the number of groups

        :return: Number of groups (int)
        """
        return len(self.groups)
```

### `pr.sh`

```bash
#!/bin/bash
# git remote add iowarp https://github.com/iowarp/ppi-jarvis-util.git
# git remote add grc https://github.com/grc-iit/jarvis-util.git
gh pr create --title $1 --body "" --repo=grc-iit/jarvis-util
gh pr create --title $1 --body "" --repo=iowarp/ppi-jarvis-util
```

### `test/unit/ares.yaml`

```yaml
fs:
- avail: null
  dev_type: nvme
  device: /dev/nvme1n1
  fs_size: null
  fs_type: null
  host: localhost
  model: CT500P1SSD8
  mount: /${USER}
  parent: null
  rota: false
  shared: false
  size: 500148941619
  tran: nvme
  uuid: null
- avail: null
  dev_type: nvme
  device: /dev/nvme0n1p1
  fs_size: null
  fs_type: ntfs
  host: localhost
  model: CT1000P1SSD8
  mount: /${USER}
  parent: /dev/nvme0n1
  rota: false
  shared: false
  size: 554696704
  tran: nvme
  uuid: AE9CF70E9CF6CFB7
- avail: null
  dev_type: ssd
  device: /dev/sda1
  fs_size: null
  fs_type: null
  host: localhost
  model: TEAML5Lite3D480G
  mount: /${USER}
  parent: /dev/sda
  rota: false
  shared: false
  size: 16777216
  tran: sata
  uuid: null
- avail: null
  dev_type: hdd
  device: /dev/sdc
  fs_size: null
  fs_type: null
  host: localhost
  model: ST2000DM006-2DM164
  mount: /${USER}
  parent: null
  rota: true
  shared: false
  size: 1979120929996
  tran: sata
  uuid: null
- avail: null
  dev_type: nvme
  device: /dev/nvme1n1p2
  fs_size: null
  fs_type: vfat
  host: localhost
  model: CT500P1SSD8
  mount: /${USER}
  parent: /dev/nvme1n1
  rota: false
  shared: false
  size: 537919488
  tran: nvme
  uuid: 6F5C-CC5C
- avail: null
  dev_type: nvme
  device: /dev/nvme1n1p3
  fs_size: null
  fs_type: ext4
  host: localhost
  model: CT500P1SSD8
  mount: /
  parent: /dev/nvme1n1
  rota: false
  shared: false
  size: 499075199795
  tran: nvme
  uuid: 8debe05d-9177-40b5-8bb0-82fc969ce919
- avail: null
  dev_type: hdd
  device: /dev/sdc1
  fs_size: null
  fs_type: null
  host: localhost
  model: ST2000DM006-2DM164
  mount: /${USER}
  parent: /dev/sdc
  rota: true
  shared: false
  size: 16777216
  tran: sata
  uuid: null
- avail: null
  dev_type: ssd
  device: /dev/sda
  fs_size: null
  fs_type: null
  host: localhost
  model: TEAML5Lite3D480G
  mount: /${USER}
  parent: null
  rota: false
  shared: false
  size: 480069969510
  tran: sata
  uuid: null
- avail: null
  dev_type: ssd
  device: /dev/sdb2
  fs_size: null
  fs_type: ntfs
  host: localhost
  model: CT1000MX500SSD1
  mount: /${USER}
  parent: /dev/sdb
  rota: false
  shared: false
  size: 1000190509056
  tran: sata
  uuid: C2105EBE105EB95D
- avail: null
  dev_type: nvme
  device: /dev/nvme1n1p1
  fs_size: null
  fs_type: null
  host: localhost
  model: CT500P1SSD8
  mount: /${USER}
  parent: /dev/nvme1n1
  rota: false
  shared: false
  size: 499122176
  tran: nvme
  uuid: null
- avail: null
  dev_type: ssd
  device: /dev/sda2
  fs_size: null
  fs_type: ntfs
  host: localhost
  model: TEAML5Lite3D480G
  mount: /${USER}
  parent: /dev/sda
  rota: false
  shared: false
  size: 480069969510
  tran: sata
  uuid: A0A85859A8582FD0
- avail: null
  dev_type: nvme
  device: /dev/nvme0n1p2
  fs_size: null
  fs_type: vfat
  host: localhost
  model: CT1000P1SSD8
  mount: /boot/efi
  parent: /dev/nvme0n1
  rota: false
  shared: false
  size: 103809024
  tran: nvme
  uuid: 66F7-8F41
- avail: null
  dev_type: nvme
  device: /dev/nvme0n1p4
  fs_size: null
  fs_type: ntfs
  host: localhost
  model: CT1000P1SSD8
  mount: /${USER}
  parent: /dev/nvme0n1
  rota: false
  shared: false
  size: 999546263961
  tran: nvme
  uuid: 4C08005F08004A82
- avail: null
  dev_type: nvme
  device: /dev/nvme0n1p3
  fs_size: null
  fs_type: null
  host: localhost
  model: CT1000P1SSD8
  mount: /${USER}
  parent: /dev/nvme0n1
  rota: false
  shared: false
  size: 16777216
  tran: nvme
  uuid: null
- avail: 214748364800
  dev_type: hdd
  device: null
  fs_size: 214748364800
  fs_type: null
  host: localhost
  model: null
  mount: asdf
  parent: null
  rota: true
  shared: true
  size: 214748364800
  tran: sata
  uuid: null
- avail: null
  dev_type: ssd
  device: /dev/sdb1
  fs_size: null
  fs_type: null
  host: localhost
  model: CT1000MX500SSD1
  mount: /${USER}
  parent: /dev/sdb
  rota: false
  shared: false
  size: 16777216
  tran: sata
  uuid: null
- avail: null
  dev_type: ssd
  device: /dev/sdb
  fs_size: null
  fs_type: null
  host: localhost
  model: CT1000MX500SSD1
  mount: /${USER}
  parent: null
  rota: false
  shared: false
  size: 1000190509056
  tran: sata
  uuid: null
- avail: null
  dev_type: nvme
  device: /dev/nvme0n1
  fs_size: null
  fs_type: null
  host: localhost
  model: CT1000P1SSD8
  mount: /${USER}
  parent: null
  rota: false
  shared: false
  size: 1000190509056
  tran: nvme
  uuid: null
net: []
hosts: ['localhost']
```

### `test/unit/print5s.py`

```python
"""
NOTE: this is a helper utility for test_local_exec
"""

import time
import sys


for i in range(5):
    sys.stdout.write(f"COUT: {i}\n")
    sys.stderr.write(f"CERR: {i}\n")
    time.sleep(1)
```

### `test/unit/printNone.py`

```python
from jarvis_util.shell.local_exec import LocalExec, LocalExecInfo

spawn_info = LocalExecInfo(hide_output=True)
LocalExec("echo hello", spawn_info)
```

### `test/unit/test_argparse.py`

```python
from jarvis_util.util.argparse import ArgParse
from unittest import TestCase
import shlex


class MyArgParse(ArgParse):
    def define_options(self):
        self.add_cmd(keep_remainder=True)
        self.add_args([
            {
                'name': 'hi',
                'msg': 'hello',
                'type': str,
                'default': None
            }
        ])

        self.add_cmd('vpic run',
                      keep_remainder=False,
                      aliases=['vpic r', 'vpic runner'])
        self.add_args([
            {
                'name': 'steps',
                'msg': 'Number of checkpoints',
                'type': int,
                'required': True,
                'pos': True,
                'class': 'sim',
                'rank': 0
            },
            {
                'name': 'x',
                'msg': 'The length of the x-axis',
                'type': int,
                'required': False,
                'default': 256,
                'pos': True,
                'class': 'sim',
                'rank': 1
            },
            {
                'name': 'do_io',
                'msg': 'Whether to perform I/O or not',
                'type': bool,
                'required': False,
                'default': False,
                'pos': True,
            },
            {
                'name': 'make_figures',
                'msg': 'Whether to make a figure',
                'type': bool,
                'default': False,
            },
            {
                'name': 'data_size',
                'msg': 'Total amount of data to produce',
                'type': int,
                'default': 1024,
            },
            {
                'name': 'hosts',
                'msg': 'A list of hosts',
                'type': list,
                'args': [
                    {
                        'name': 'host',
                        'msg': 'A string representing a host',
                        'type': str,
                    }
                ],
                'aliases': ['x']
            },
            {
                'name': 'devices',
                'msg': 'A list of devices and counts',
                'type': list,
                'args': [
                    {
                        'name': 'path',
                        'msg': 'The mount point of device',
                        'type': str,
                    },
                    {
                        'name': 'count',
                        'msg': 'The number of devices to search for',
                        'type': int,
                    }
                ]
            }
        ])


class TestArgparse(TestCase):
    def test_default_argparse(self):
        args = MyArgParse(args='hi=\"23528 asfda\"')
        self.assertEqual(args.kwargs['hi'], '23528 asfda')

    def test_help(self):
        MyArgParse(args='vpic run -h')

    def test_bool_kwargs(self):
        args = MyArgParse(args='vpic run 20 512 True +make_figures')
        self.assertEqual(args.kwargs['steps'], 20)
        self.assertEqual(args.kwargs['x'], 512)
        self.assertEqual(args.kwargs['do_io'], True)
        self.assertEqual(args.kwargs['make_figures'], True)
        self.assertEqual(args.kwargs['hosts'], None)
        self.assertEqual(args.kwargs['devices'], None)

    def test_bool_kwargs2(self):
        args = MyArgParse(args='vpic run 20 512 True -make_figures')
        self.assertEqual(args.kwargs['steps'], 20)
        self.assertEqual(args.kwargs['x'], 512)
        self.assertEqual(args.kwargs['do_io'], True)
        self.assertEqual(args.kwargs['make_figures'], False)
        self.assertEqual(args.kwargs['hosts'], None)
        self.assertEqual(args.kwargs['devices'], None)

    def test_bool_kwargs3(self):
        args = MyArgParse(args='vpic run 20 512 True --make_figures=true')
        self.assertEqual(args.kwargs['steps'], 20)
        self.assertEqual(args.kwargs['x'], 512)
        self.assertEqual(args.kwargs['do_io'], True)
        self.assertEqual(args.kwargs['make_figures'], True)
        self.assertEqual(args.kwargs['hosts'], None)
        self.assertEqual(args.kwargs['devices'], None)

    def test_bool_kwargs4(self):
        args = MyArgParse(args='vpic run 20 512 True --make_figures=false')
        self.assertEqual(args.kwargs['steps'], 20)
        self.assertEqual(args.kwargs['x'], 512)
        self.assertEqual(args.kwargs['do_io'], True)
        self.assertEqual(args.kwargs['make_figures'], False)
        self.assertEqual(args.kwargs['hosts'], None)
        self.assertEqual(args.kwargs['devices'], None)

    def test_list_arg(self):
        args = MyArgParse(args='vpic run 15 --hosts=\"[129.15, 1294.124]\"')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual(['129.15', '1294.124'], args.kwargs['hosts'])

    def test_list_arg2(self):
        args = MyArgParse(args='vpic run 15 --hosts=129.15 --hosts=1294.124')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual(['129.15', '1294.124'], args.kwargs['hosts'])

    def test_list_arg3(self):
        args = MyArgParse(args='vpic run 15 --hosts=129.15 --hosts=1294.124 --hosts=')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual([], args.kwargs['hosts'])

    def test_list_arg4(self):
        args = MyArgParse(args='vpic run 15 --hosts=[]')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual([], args.kwargs['hosts'])

    def test_list_arg5(self):
        args = MyArgParse(
            args='vpic run 15 --hosts="*.hdf5" --hosts="*.h5"')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual(['*.hdf5', '*.h5'], args.kwargs['hosts'])

    def test_list_list_arg(self):
        args = MyArgParse(args='vpic run 15 '
                               '--devices=\"[[nvme, 5], [sata, 25]]\"')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual([['nvme', 5], ['sata', 25]], args.kwargs['devices'])

    def test_arg_alias(self):
        args = MyArgParse(args='vpic run 15 -hosts=129.15 -hosts=1294.124')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual(['129.15', '1294.124'], args.kwargs['hosts'])

        args = MyArgParse(args='vpic run 15 -x=129.15 -x=1294.124')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual(['129.15', '1294.124'], args.kwargs['hosts'])

    def test_menu_alias(self):
        args = MyArgParse(args='vpic run 15 -hosts=129.15 -hosts=1294.124')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual(['129.15', '1294.124'], args.kwargs['hosts'])

        args = MyArgParse(args='vpic r 15 -x=129.15 -x=1294.124')
        self.assertEqual(15, args.kwargs['steps'])
        self.assertEqual(['129.15', '1294.124'], args.kwargs['hosts'])
```

### `test/unit/test_hostfile.py`

```python
from jarvis_util.util.hostfile import Hostfile
import pathlib
from unittest import TestCase


class TestHostfile(TestCase):
    def test_no_expand_int(self):
        host = Hostfile(text='0', find_ips=False)
        self.assertTrue(len(host.hosts) == 1)
        self.assertTrue(host.hosts[0] == '0')

    def test_no_expand(self):
        host = Hostfile(text='ares-comp-01', find_ips=False)
        self.assertTrue(len(host.hosts) == 1)
        self.assertTrue(host.hosts[0] == 'ares-comp-01')

    def test_expand_set(self):
        host = Hostfile(text='ares-comp-[01-04]-40g', find_ips=False)
        self.assertTrue(len(host.hosts) == 4)
        self.assertTrue(host.hosts[0] == 'ares-comp-01-40g')
        self.assertTrue(host.hosts[1] == 'ares-comp-02-40g')
        self.assertTrue(host.hosts[2] == 'ares-comp-03-40g')
        self.assertTrue(host.hosts[3] == 'ares-comp-04-40g')

    def test_expand_two_sets(self):
        host = Hostfile(text='ares-comp-[01-02]-40g-[01-02]', find_ips=False)
        self.assertTrue(len(host.hosts) == 4)
        self.assertTrue(host.hosts[0] == 'ares-comp-01-40g-01')
        self.assertTrue(host.hosts[1] == 'ares-comp-01-40g-02')
        self.assertTrue(host.hosts[2] == 'ares-comp-02-40g-01')
        self.assertTrue(host.hosts[3] == 'ares-comp-02-40g-02')

    def test_subset(self):
        host = Hostfile(text='ares-comp-[01-02]-40g-[01-02]', find_ips=False)
        host = host.subset(3)
        self.assertTrue(len(host.hosts) == 3)
        self.assertTrue(host.is_subset())
        self.assertTrue(host.hosts[0] == 'ares-comp-01-40g-01')
        self.assertTrue(host.hosts[1] == 'ares-comp-01-40g-02')
        self.assertTrue(host.hosts[2] == 'ares-comp-02-40g-01')

    def test_read_hostfile(self):
        HERE = str(pathlib.Path(__file__).parent.resolve())
        hf = Hostfile(hostfile=f'{HERE}/test_hostfile.txt', find_ips=False)
        print(hf.hosts)
        self.assertEqual(len(hf), 15)

    def test_save_hostfile(self):
        HERE = str(pathlib.Path(__file__).parent.resolve())
        hf = Hostfile(hostfile=f'{HERE}/test_hostfile.txt', find_ips=False)
        hf_sub = hf.subset(4)
        self.assertEqual(len(hf_sub), 4)
        hf_sub.save('/tmp/test_hostfile.txt')
        hf_sub_reload = Hostfile(hostfile=f'/tmp/test_hostfile.txt',
                                 find_ips=False)
        self.assertEqual(len(hf_sub_reload), 4)
        self.assertEqual(hf_sub, hf_sub_reload)
```

### `test/unit/test_hostfile.txt`

```
ares-comp-[01-10,11,12-15]-40g
```

### `test/unit/test_local_exec.py`

```python
import pathlib
import os
from jarvis_util.shell.local_exec import LocalExec, LocalExecInfo
from jarvis_util.shell.exec import Exec
from unittest import TestCase


class TestLocalExec(TestCase):
    def _setup_files(self):
        self.stdout = '/tmp/test_out.log'
        self.stderr = '/tmp/test_err.log'
        try:
            os.remove(self.stdout)
        except OSError:
            pass
        try:
            os.remove(self.stderr)
        except:
            pass

    def test_default(self):
        ret = Exec("echo hello")
        self.assertEqual(ret.exit_code, 0)
        self.assertEqual(len(ret.stdout['localhost']), 0)

    def test_pipe_stdout(self):
        self._setup_files()
        spawn_info = LocalExecInfo(pipe_stdout=self.stdout,
                                   pipe_stderr=self.stderr,
                                   collect_output=True)
        ret = Exec("echo hello", spawn_info)
        self.assertEqual(ret.stdout['localhost'].strip(), "hello")
        self.assertEqual(ret.stderr['localhost'].strip(), "")
        self.assertFile(self.stdout, "hello")
        self.assertFile(self.stderr, "")

    def test_hide_stdout(self):
        HERE = str(pathlib.Path(__file__).parent.resolve())
        PRINTNONE = os.path.join(HERE, 'printNone.py')
        spawn_info = LocalExecInfo(collect_output=True)
        ret = Exec(f"python3 {PRINTNONE}", spawn_info)
        self.assertEqual(ret.stdout['localhost'].strip(), "")
        self.assertEqual(ret.stderr['localhost'].strip(), "")

    def test_periodic_print(self):
        self._setup_files()
        HERE = str(pathlib.Path(__file__).parent.resolve())
        PRINT5s = os.path.join(HERE, 'print5s.py')
        ret = Exec(f"python3 {PRINT5s}",
                   LocalExecInfo(pipe_stdout=self.stdout,
                                 pipe_stderr=self.stderr))
        stdout_data = "\n".join([f"COUT: {i}" for i in range(5)])
        stderr_data = "\n".join([f"CERR: {i}" for i in range(5)])
        self.assertFile(self.stdout, stdout_data)
        self.assertFile(self.stderr, stderr_data)

    def assertFile(self, path, data, strip=True):
        self.assertTrue(os.path.exists(path))
        with open(path, 'r') as fp:
            if strip:
                data = data.strip()
                file_data = fp.read().strip()
            else:
                file_data = fp.read()
        self.assertEqual(data, file_data)
```

### `test/unit/test_monitor.py`

```python
from jarvis_util.util.argparse import ArgParse
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.local_exec import LocalExecInfo
from jarvis_util.util.hostfile import Hostfile
from jarvis_util.introspect.system_info import Lsblk, \
    ListFses, FiInfo, Blkid, ResourceGraph, StorageDeviceType
from jarvis_util.util.size_conv import SizeConv
import pathlib
import itertools
import os
from unittest import TestCase
from jarvis_util.introspect.monitor import Monitor, MonitorParser

class TestSystemInfo(TestCase):

    def test_monitor_parser(self):
        parser = MonitorParser(os.path.join(os.environ['HOME'], 'monitor'))
        parser.parse()
        avg = parser.avg_memory()
        print(avg)
```

### `test/unit/test_mpi.py`

```python
from jarvis_util.util.argparse import ArgParse
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.local_exec import LocalExecInfo
from jarvis_util.shell.mpi_exec import MpiVersion
from jarvis_util.util.size_conv import SizeConv
import pathlib
import itertools
from unittest import TestCase


class TestSystemInfo(TestCase):
    def test_mpi(self):
        info = MpiVersion(LocalExecInfo())
        print(f'MPI VERSION: {info.version}')
```

### `test/unit/test_small_df.py`

```python
from jarvis_util.util.argparse import ArgParse
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.local_exec import LocalExecInfo
from jarvis_util.util.hostfile import Hostfile
from jarvis_util.introspect.system_info import Lsblk, \
    ListFses, FiInfo, Blkid, ResourceGraph, StorageDeviceType
from jarvis_util.util.size_conv import SizeConv
from jarvis_util.util.small_df import SmallDf
import pathlib
import itertools
from unittest import TestCase


class TestSmallDf(TestCase):
    def test_create(self):
        rows = [{'a': 1, 'b': 2}, {'c': 3}, {'d': 4}]
        df = SmallDf(rows=rows)
        self.assertEqual(3, len(df))
        self.assertEqual(set(['a', 'b', 'c', 'd']), set(df.columns))

    def test_query(self):
        rows = [{'a': 1, 'b': 2}, {'c': 3}, {'d': 4}]
        df = SmallDf(rows=rows)
        sub_df = df['a']
        records = sub_df.list()
        self.assertEqual([1, None, None], records)
        sub_df = df[:, ['a', 'b']]
        records = sub_df.list()
        self.assertEqual([[1, 2], [None, None], [None, None]], records)

    def test_col_assign(self):
        rows = [{'a': 1, 'b': 2}, {'c': 3}, {'d': 4}]
        df = SmallDf(rows=rows)
        df['a'] = 25
        records = df['a'].list()
        self.assertEqual([25, 25, 25], records)

    def test_col_row_assign(self):
        rows = [{'a': 1, 'b': 2}, {'c': 3}, {'d': 4}]
        df = SmallDf(rows=rows)
        sub_df = df['a']
        sub_df[lambda r: r['a'] is None, 'a'] = 25
        records = set(df['a'].list())
        self.assertEqual({1, 25, 25}, records)

    def test_add(self):
        rows = [{'a': 3, 'b': 2}, {'a': 2}, {'d': 4}]
        df = SmallDf(rows=rows)
        df['a'].fillna(0)
        df['b'].fillna(0)
        df['c'] = df['a'] + df['b']
        records = set(df['c'].list())
        self.assertEqual({5, 2, 0}, records)

    def test_addeq(self):
        rows = [{'a': 3, 'b': 2}, {'a': 2}, {'d': 4}]
        df = SmallDf(rows=rows)
        df['a'].fillna(0)
        df['b'].fillna(0)
        df['a'] += df['b']
        records = set(df['a'].list())
        self.assertEqual({5, 2, 0}, records)

    def test_add2(self):
        rows = [{'a': 3, 'b': 2}, {'a': 2}, {'d': 4}]
        df = SmallDf(rows=rows)
        df['a'].fillna(0)
        df['b'].fillna(0)
        df['c'] = df['a'] + df['b'] + 5
        records = set(df['c'].list())
        self.assertEqual({10, 7, 5}, records)

    def test_mul(self):
        rows = [{'a': 3, 'b': 2}, {'a': 2}, {'d': 4}]
        df = SmallDf(rows=rows)
        df['a'].fillna(0)
        df['b'].fillna(0)
        df['c'] = df['a'] * df['b']
        records = set(df['c'].list())
        self.assertEqual({6, 0, 0}, records)

    def test_div(self):
        rows = [{'a': 3, 'b': 2}, {'a': 2}, {'d': 4}]
        df = SmallDf(rows=rows)
        df['a'].fillna(1)
        df['b'].fillna(1)
        df['c'] = df['a'] / df['b']
        records = set(df['c'].list())
        self.assertEqual({1.5, 2, 1}, records)

    def test_merge(self):
        rows = [{'a': 3, 'b': 2}, {'a': 2}, {'d': 4}]
        df1 = SmallDf(rows=rows)
        rows = [{'a': 3, 'e': 2}, {'a': 3, 'e': 4}]
        df2 = SmallDf(rows=rows)
        df3 = df1.merge(df2)
        self.assertEqual(4, len(df3))
        self.assertEqual(1, len(df3[lambda r: r['a'] == 3 and r['e'] == 2]))
        self.assertEqual(1, len(df3[lambda r: r['a'] == 3 and r['e'] == 4]))

    def test_groupby(self):
        rows = [{'a': 3, 'b': 2}, {'a': 3, 'b': 1}, {'a': 2, 'b': 4}]
        df1 = SmallDf(rows=rows)
        grp = df1.groupby('a')
        self.assertEqual(2, len(grp))
        self.assertEqual(set([tuple([2]), tuple([3])]),
                         set(grp.groups.keys()))
```

### `test/unit/test_system_info.py`

```python
from jarvis_util.util.argparse import ArgParse
from jarvis_util.shell.exec import Exec
from jarvis_util.shell.local_exec import LocalExecInfo
from jarvis_util.util.hostfile import Hostfile
from jarvis_util.introspect.system_info import Lsblk, \
    ListFses, FiInfo, Blkid, ResourceGraph, StorageDeviceType
from jarvis_util.util.size_conv import SizeConv
import pathlib
import itertools
from unittest import TestCase


class TestSystemInfo(TestCase):
    def test_lsblk(self):
        Lsblk(LocalExecInfo(hide_output=True))

    def test_list_fses(self):
        ListFses(LocalExecInfo(hide_output=True))

    def test_fi_info(self):
        FiInfo(LocalExecInfo(hide_output=True))

    def test_blkid(self):
        Blkid(LocalExecInfo(hide_output=True))

    def test_resource_graph(self):
        rg = ResourceGraph()
        rg.build(LocalExecInfo(hide_output=True))
        rg.save('/tmp/resource_graph.yaml')
        rg.load('/tmp/resource_graph.yaml')
        rg.filter_fs(r'/$')
        rg.add_suffix(r'/$', '/${USER}')
        rg.save('/tmp/resource_graph.yaml')

    def test_custom_resource_graph(self):
        rg = ResourceGraph()
        all_hosts = ['host1', 'host2', 'host3']
        all_hosts_ip = ['192.168.1.0', '192.168.1.1', '192.168.1.2']
        providers = ['tcp', 'ib', 'roce']
        hosts = Hostfile(all_hosts=all_hosts, all_hosts_ip=all_hosts_ip)

        # Add networks for each node
        rg.set_hosts(hosts)
        rg.add_net(hosts,
                   [{'provider': provider, 'shared': True}
                    for provider in providers])
        rg.add_net(hosts.subset(1),
                   [{'provider': 'uncommon'}])

        # Two HDD, SSD, and NVME per-host
        # 2 * 3 * 3 = 18 devices
        rg.add_storage(hosts, [
            {
                'device': '/dev/sda1',
                'mount': '/',
                'dev_type': 'hdd',
                'size': '10g',
                'shared': False
            },
            {
                'device': '/dev/sda2',
                'mount': '/mnt/hdd/$USER',
                'dev_type': 'hdd',
                'size': '200g',
                'shared': False
            },
            {
                'device': '/dev/sdb1',
                'mount': '/mnt/ssd/$USER',
                'dev_type': 'ssd',
                'size': '50g',
                'shared': False
            },
            {
                'device': '/dev/sdb2',
                'mount': '/mnt/ssd2/$USER',
                'dev_type': 'ssd',
                'size': '50g',
                'shared': False
            },
            {
                'device': '/dev/nvme0n1',
                'mount': '/mnt/nvme/$USER',
                'dev_type': 'nvme',
                'size': '100g',
                'shared': False
            },
            {
                'device': '/dev/nvme0n3',
                'mount': '/mnt/nvme3/$USER',
                'dev_type': 'nvme',
                'size': '100g',
                'shared': False
            }
        ])
        self.assertEqual(18, len(rg.fs))
        # One NVMe on first host
        # 19 devices
        rg.add_storage(hosts.subset(1), [
            {
                'device': '/dev/nvme0n2',
                'mount': '/mnt/nvme2/$USER',
                'dev_type': 'nvme',
                'size': SizeConv.to_int('10g'),
                'shared': False
            }
        ])
        self.assertEqual(19, len(rg.fs))

        # Filter only mounts in '/mnt'
        rg.filter_fs('/mnt/*')
        self.assertEqual(16, len(rg.fs))

        # Find all mounted NVMes
        df = rg.find_storage(dev_types=[StorageDeviceType.NVME])
        self.assertEqual(7, len(df[lambda r: r['dev_type'] == 'nvme']))
        self.assertEqual(0, len(df[lambda r: r['dev_type'] == 'hdd']))
        self.assertEqual(0, len(df[lambda r: r['dev_type'] == 'ssd']))
        self.assertEqual(7, len(df))

        # Find all mounted & common NVMes and SSDs
        df = rg.find_storage([StorageDeviceType.NVME,
                              StorageDeviceType.SSD],
                             common=True)
        self.assertEqual(6, len(df[lambda r: r['dev_type'] == 'nvme']))
        self.assertEqual(6, len(df[lambda r: r['dev_type'] == 'ssd']))
        self.assertEqual(12, len(df))

        # Select a single nvme and ssd per-node
        df = rg.find_storage([StorageDeviceType.NVME,
                              StorageDeviceType.SSD],
                             common=True,
                             count_per_dev=1)
        self.assertEqual(3, len(df[lambda r: r['dev_type'] == 'nvme']))
        self.assertEqual(3, len(df[lambda r: r['dev_type'] == 'ssd']))
        self.assertEqual(6, len(df))

        # Get condensed output
        df = rg.find_storage([StorageDeviceType.NVME,
                              StorageDeviceType.SSD],
                             common=True,
                             condense=True,
                             count_per_dev=1)
        self.assertEqual(1, len(df[lambda r: str(r['dev_type']) == 'nvme']))
        self.assertEqual(1, len(df[lambda r: str(r['dev_type']) == 'ssd']))
        self.assertEqual(2, len(df))
        rg.print_df(df)

        # Find common networks between hosts
        df = rg.find_net_info(hosts, shared=True)
        self.assertEqual(9, len(df))

        # Find common tcp networks
        df = rg.find_net_info(hosts, providers='tcp')
        self.assertEqual(3, len(df))

        # Find common + condensed TCP networks
        df = rg.find_net_info(hosts, providers='tcp', condense=True)
        self.assertEqual(1, len(df))

        rg.print_df(df)

    def test_add_suffix(self):
        rg = ResourceGraph()
        all_hosts = ['host1', 'host2', 'host3']
        all_hosts_ip = ['192.168.1.0', '192.168.1.1', '192.168.1.2']
        providers = ['tcp', 'ib', 'roce']
        hosts = Hostfile(all_hosts=all_hosts, all_hosts_ip=all_hosts_ip)

        # Add networks for each node
        rg.set_hosts(hosts)
        rg.add_net(hosts,
                   [{'provider': provider} for provider in providers])
        rg.add_net(hosts.subset(1),
                   [{'provider': 'uncommon'}])

        # Add storage
        rg.add_storage(hosts, [
            {
                'device': '/dev/sda1',
                'mount': '/',
                'dev_type': 'ssd',
                'size': SizeConv.to_int('10g'),
                'shared': False
            }
        ])

        rg.add_suffix('/', '${USER}')
        df = rg.find_storage(mount_res=r'.*\${USER}')
        self.assertEqual(3, len(df))

    def test_ares(self):
        rg = ResourceGraph()
        TEST_DIR = pathlib.Path(__file__).parent.resolve()
        rg = rg.load(f'{TEST_DIR}/ares.yaml')
        hosts = Hostfile()
        rg.make_common(hosts)
```
