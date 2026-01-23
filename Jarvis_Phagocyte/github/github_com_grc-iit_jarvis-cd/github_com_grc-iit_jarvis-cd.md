# jarvis-cd

> Jarvis-cd is a unified platform for deploying various applications

## Repository Info

- **Stars:** 4
- **Forks:** 8
- **Language:** Python
- **License:** MIT License
- **Topics:** ci-cd, deployment, jarvis, scripting
- **Source:** `https://github.com/grc-iit/jarvis-cd`
- **Branch:** `main`
- **Commit:** `40cd42d2a459`
- **Last Commit:** 2025-05-25 01:40:08 -0500
- **Commits:** 1
- **Extracted:** 2026-01-22T18:42:52.280773


## Directory Structure

```
jarvis-cd/
├── .github/
│   └── workflows/
│       └── main.yml
├── .vscode/
│   └── launch.json
├── bin/
│   ├── example.slurm
│   ├── jarvis
│   └── jarvis-imports
├── builtin/
│   ├── builtin/
│   │   ├── arldm/
│   │   │   ├── example_config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── asan/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── cm1/
│   │   │   ├── config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── cosmic_tagger/
│   │   │   ├── config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── darshan/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── data_stagein/
│   │   │   └── pkg.py
│   │   ├── ddmd/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── dlio_benchmark/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── echo/
│   │   │   └── pkg.py
│   │   ├── filebench/
│   │   │   ├── config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── fio/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── gadget2/
│   │   │   ├── config/
│   │   │   ├── paramfiles/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── gadget2_df/
│   │   │   ├── paramfiles/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── gray_scott/
│   │   │   ├── config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── hermes_api/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── hermes_api_bench/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── hermes_mpiio_tests/
│   │   │   └── pkg.py
│   │   ├── hermes_posix_tests/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── hermes_run/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── hermes_stdio_tests/
│   │   │   └── pkg.py
│   │   ├── hermes_unit_tests/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── hermes_vfd_tests/
│   │   │   └── pkg.py
│   │   ├── hermes_viz/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── ior/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── my_shell/
│   │   │   ├── pkg.py
│   │   │   └── test_scirpt.sh
│   │   ├── nyx_lya/
│   │   │   ├── config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── orangefs/
│   │   │   ├── __init__.py
│   │   │   ├── ares.py
│   │   │   ├── custom_kern.py
│   │   │   ├── Dockerfile
│   │   │   ├── fuse.py
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── pyflextrkr/
│   │   │   ├── example_config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── pymonitor/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── redis/
│   │   │   ├── config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── redis-benchmark/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── spark_cluster/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── ycsbc/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   └── __init__.py
│   ├── config/
│   │   ├── ares.yaml
│   │   ├── deception.yaml
│   │   └── polaris.yaml
│   ├── resource_graph/
│   │   ├── ares.yaml
│   │   ├── deception.yaml
│   │   ├── delta.yaml
│   │   ├── g2-standard-4.yaml
│   │   └── polaris.yaml
│   └── __init__.py
├── ci/
│   ├── cluster/
│   │   ├── docker-compose.yml
│   │   └── Dockerfile
│   ├── install_deps.sh
│   ├── install_jarvis.sh
│   ├── lint.sh
│   └── run_tests.sh
├── docs/
│   ├── source/
│   │   ├── conf.py
│   │   ├── development.rst
│   │   ├── index.rst
│   │   ├── install.rst
│   │   └── usage.rst
│   ├── make.bat
│   └── Makefile
├── jarvis_cd/
│   ├── basic/
│   │   ├── __init__.py
│   │   ├── jarvis_manager.py
│   │   └── pkg.py
│   ├── template/
│   │   ├── __init__.py
│   │   ├── app_templ.py
│   │   ├── interceptor_templ.py
│   │   └── service_templ.py
│   └── __init__.py
├── test/
│   ├── unit/
│   │   ├── test_repo/
│   │   │   ├── test_repo/
│   │   │   └── __init__.py
│   │   ├── __init__.py
│   │   ├── pipeline.yaml
│   │   ├── pipeline_iter.yaml
│   │   └── test_cli.py
│   └── __init__.py
├── .coveragerc
├── .gitignore
├── build.sh
├── lcov.info
├── LICENSE
├── logg.txt
├── meta.yaml
├── pr.sh
├── pylintrc
├── pyproject.toml
├── README.md
├── requirements.txt
└── setup.py
```

## File Statistics

- **Files Processed:** 134
- **Files Skipped:** 0


## README

# The Platform Plugins Interface: Jarvis-CD
Jarvis-CD is a unified platform for deploying various applications, including
storage systems and benchmarks. Many applications have complex configuration
spaces and are difficult to deploy across different machines.

We provide a builtin repo which contains various applications to deploy.
We refer to applications as "jarivs pkgs" which can be connected to form
"deployment pipelines".

Our full guide for installing and bootstrapping is located [here](https://grc.iit.edu/docs/jarvis/jarvis-cd/index).

## Source Files

Source code files are processed separately by the processor.
File list:

- `builtin/builtin/arldm/README.md` (14,132 bytes)
- `builtin/builtin/asan/README.md` (352 bytes)
- `builtin/builtin/cm1/README.md` (639 bytes)
- `builtin/builtin/cosmic_tagger/README.md` (701 bytes)
- `builtin/builtin/darshan/README.md` (1,148 bytes)
- `builtin/builtin/ddmd/README.md` (10,271 bytes)
- `builtin/builtin/dlio_benchmark/README.md` (1,463 bytes)
- `builtin/builtin/filebench/README.md` (94 bytes)
- `builtin/builtin/fio/README.md` (58 bytes)
- `builtin/builtin/gadget2/README.md` (2,009 bytes)
- `builtin/builtin/gadget2_df/README.md` (1,395 bytes)
- `builtin/builtin/gray_scott/README.md` (3,326 bytes)
- `builtin/builtin/hermes_api/README.md` (368 bytes)
- `builtin/builtin/hermes_api_bench/README.md` (1,077 bytes)
- `builtin/builtin/hermes_posix_tests/README.md` (58 bytes)
- `builtin/builtin/hermes_run/README.md` (3,299 bytes)
- `builtin/builtin/hermes_unit_tests/README.md` (49 bytes)
- `builtin/builtin/hermes_viz/README.md` (1,569 bytes)
- `builtin/builtin/ior/README.md` (1,134 bytes)
- `builtin/builtin/nyx_lya/README.md` (2,174 bytes)
- `builtin/builtin/orangefs/README.md` (3,629 bytes)
- `builtin/builtin/pyflextrkr/README.md` (16,793 bytes)
- `builtin/builtin/pymonitor/README.md` (0 bytes)
- `builtin/builtin/redis-benchmark/README.md` (130 bytes)
- `builtin/builtin/redis/README.md` (76 bytes)
- `builtin/builtin/spark_cluster/README.md` (1,012 bytes)
- `builtin/builtin/ycsbc/README.md` (76 bytes)
- `.gitignore` (2,050 bytes)
- `LICENSE` (1,064 bytes)
- `builtin/builtin/orangefs/Dockerfile` (1,644 bytes)
- `ci/cluster/Dockerfile` (1,345 bytes)
- `ci/cluster/docker-compose.yml` (287 bytes)
- `docs/Makefile` (638 bytes)
- `pyproject.toml` (944 bytes)
- `requirements.txt` (158 bytes)
- `setup.py` (1,431 bytes)
- `.github/workflows/main.yml` (823 bytes)
- `.vscode/launch.json` (1,419 bytes)
- `build.sh` (26 bytes)
- `builtin/__init__.py` (0 bytes)
- `builtin/builtin/__init__.py` (0 bytes)
- `builtin/builtin/arldm/example_config/config.yml` (1,297 bytes)
- `builtin/builtin/arldm/example_config/config_template.yml` (1,940 bytes)
- `builtin/builtin/arldm/pkg.py` (19,610 bytes)
- `builtin/builtin/asan/pkg.py` (1,352 bytes)
- `builtin/builtin/cm1/pkg.py` (6,113 bytes)
- `builtin/builtin/cosmic_tagger/config/config.yaml` (1,174 bytes)
- `builtin/builtin/cosmic_tagger/config/default.yaml` (104 bytes)
- `builtin/builtin/cosmic_tagger/pkg.py` (2,688 bytes)
- `builtin/builtin/darshan/pkg.py` (2,008 bytes)
- ... and 83 more files
