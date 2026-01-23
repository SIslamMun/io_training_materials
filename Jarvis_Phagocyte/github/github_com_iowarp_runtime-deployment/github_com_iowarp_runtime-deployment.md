# runtime-deployment

> Jarvis-cd is a unified platform for deploying various applications

## Repository Info

- **Stars:** 11
- **Forks:** 3
- **Language:** Python
- **License:** Other
- **Topics:** ai4hpc
- **Source:** `https://github.com/iowarp/runtime-deployment`
- **Branch:** `main`
- **Commit:** `e4dcf52927e0`
- **Last Commit:** 2026-01-20 14:25:41 -0600
- **Commits:** 1
- **Extracted:** 2026-01-22T18:43:18.219822


## Directory Structure

```
runtime-deployment/
├── .claude/
│   └── agents/
│       ├── code-documenter.md
│       ├── docker-python-test-expert.md
│       ├── git-expert.md
│       ├── jarvis-pipeline-builder.md
│       └── python-code-updater.md
├── .github/
│   └── workflows/
│       ├── build-containers.yaml
│       └── main.yml
├── .vscode/
│   └── launch.json
├── ai-prompts/
│   ├── docker/
│   │   └── phase1.md
│   ├── new-pipeline.md
│   ├── phase-14-update.md
│   ├── phase1-argparse.md
│   ├── phase10-pipeline-index.md
│   ├── phase11-template.md
│   ├── phase12-pipeline.md
│   ├── phase13-jarvis-mod
│   ├── phase14-jarvis-ppl-pkg.md
│   ├── phase15-containers.md
│   ├── phase16-installer.md
│   ├── phase2-hostfile.md
│   ├── phase2-logging.md
│   ├── phase3-launch.md
│   ├── phase4-resource-graph.md
│   ├── phase5-jarvis-repos.md
│   ├── phase6-jarvis-env.md
│   ├── phase8-paths.md
│   └── phase9-pipeline-scripts.md
├── bin/
│   ├── example.slurm
│   ├── jarvis
│   ├── jarvis-imports
│   └── jarvis_resource_graph
├── builtin/
│   ├── builtin/
│   │   ├── adios2_gray_scott/
│   │   │   ├── config/
│   │   │   ├── INSTALL.md
│   │   │   ├── pkg.py
│   │   │   ├── README.md
│   │   │   └── USE.md
│   │   ├── adios2_pdf_calc/
│   │   │   ├── config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── arldm/
│   │   │   ├── example_config/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── asan/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── builtin_pkg/
│   │   │   └── package.py
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
│   │   ├── example_app/
│   │   │   └── pkg.py
│   │   ├── example_interceptor/
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
│   │   ├── InCompact3D/
│   │   │   ├── config/
│   │   │   ├── spack/
│   │   │   ├── incompact3D.yaml
│   │   │   ├── INSTALL.md
│   │   │   ├── pkg.py
│   │   │   ├── README.md
│   │   │   └── USE.md
│   │   ├── InCompact3D_post/
│   │   │   ├── config/
│   │   │   ├── incompact3d_post.yaml
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── ior/
│   │   │   ├── __init__.py
│   │   │   ├── container.py
│   │   │   ├── default.py
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   ├── lammps/
│   │   │   ├── config/
│   │   │   ├── INSTALL.md
│   │   │   ├── pkg.py
│   │   │   ├── README.md
│   │   │   └── USE.md
│   │   ├── mkfs/
│   │   │   └── pkg.py
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
│   │   ├── paraview/
│   │   │   ├── INSTALL.MD
│   │   │   ├── pkg.py
│   │   │   ├── README.md
│   │   │   ├── server_setup.png
│   │   │   └── USE.MD
│   │   ├── post_wrf/
│   │   │   ├── config/
│   │   │   └── pkg.py
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
│   │   ├── test_pkg/
│   │   │   └── package.py
│   │   ├── wrf/
│   │   │   ├── config/
│   │   │   ├── INSTALL.md
│   │   │   ├── pkg.py
│   │   │   ├── README.md
│   │   │   ├── USE.md
│   │   │   └── wrf_workflow.png
│   │   ├── ycsbc/
│   │   │   ├── pkg.py
│   │   │   └── README.md
│   │   └── __init__.py
│   ├── config/
│   │   ├── ares.yaml
│   │   ├── deception.yaml
│   │   └── polaris.yaml
│   ├── pipelines/
│   │   ├── examples/
│   │   │   ├── ior_container_test.yaml
│   │   │   └── ior_podman_test.yaml
│   │   ├── unit_tests/
│   │   │   └── test_interceptor.yaml
│   │   ├── simple_test.yaml
│   │   ├── test_interceptor.yaml
│   │   └── test_simple.yaml
... (truncated)
```

## File Statistics

- **Files Processed:** 255
- **Files Skipped:** 0


## README

# Jarvis-CD

Jarvis-CD is a unified platform for deploying various applications, including storage systems and benchmarks. Many applications have complex configuration spaces and are difficult to deploy across different machines.

## Installation

```bash
cd /path/to/jarvis-cd
python3 -m pip install -r requirements.txt
python3 -m pip install -e .
```

## Configuration (Build your Jarvis setup)

```bash
jarvis init [CONFIG_DIR] [PRIVATE_DIR] [SHARED_DIR]
```
- CONFIG_DIR: Stores Jarvis metadata for pkgs/pipelines (any path you can access)
- PRIVATE_DIR: Per-machine local data (e.g., OrangeFS state)
- SHARED_DIR: Shared across machines with the same view of data

On a personal machine, these can point to the same directory.

## Hostfile (set target nodes)

The hostfile lists nodes for multi-node pipelines (MPI-style format):

Example:
```text
host-01
host-[02-05]
```

Set the active hostfile:
```bash
jarvis hostfile set /path/to/hostfile
```

After changing the hostfile, update the active pipeline:
```bash
jarvis ppl update
```

## Resource Graph (discover storage)

```bash
jarvis rg build
```

## License

BSD-3-Clause License - see [LICENSE](LICENSE) file for details.

**Copyright (c) 2024, Gnosis Research Center, Illinois Institute of Technology**


## Source Files

Source code files are processed separately by the processor.
File list:

- `builtin/builtin/InCompact3D/README.md` (9,402 bytes)
- `builtin/builtin/InCompact3D_post/README.md` (1,781 bytes)
- `builtin/builtin/adios2_gray_scott/README.md` (2,657 bytes)
- `builtin/builtin/adios2_pdf_calc/README.md` (2,751 bytes)
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
- `builtin/builtin/ior/README.md` (1,134 bytes)
- `builtin/builtin/lammps/README.md` (1,249 bytes)
- `builtin/builtin/nyx_lya/README.md` (2,174 bytes)
- `builtin/builtin/orangefs/README.md` (3,629 bytes)
- `builtin/builtin/paraview/README.md` (257 bytes)
- `builtin/builtin/pyflextrkr/README.md` (16,793 bytes)
- `builtin/builtin/pymonitor/README.md` (0 bytes)
- `builtin/builtin/redis-benchmark/README.md` (130 bytes)
- `builtin/builtin/redis/README.md` (76 bytes)
- `builtin/builtin/spark_cluster/README.md` (1,012 bytes)
- `builtin/builtin/wrf/README.md` (11,521 bytes)
- `builtin/builtin/ycsbc/README.md` (76 bytes)
- `docs/README.md` (9,510 bytes)
- `test/README.md` (7,440 bytes)
- `.gitignore` (2,057 bytes)
- `LICENSE` (1,685 bytes)
- `builtin/builtin/orangefs/Dockerfile` (1,621 bytes)
- `pyproject.toml` (1,615 bytes)
- `requirements.txt` (75 bytes)
- `setup.py` (418 bytes)
- `test/Dockerfile` (3,071 bytes)
- `test/docker-compose.yml` (2,105 bytes)
- `.claude/agents/code-documenter.md` (3,532 bytes)
- `.claude/agents/docker-python-test-expert.md` (4,373 bytes)
- `.claude/agents/git-expert.md` (5,391 bytes)
- `.claude/agents/jarvis-pipeline-builder.md` (5,170 bytes)
- `.claude/agents/python-code-updater.md` (3,375 bytes)
- `.github/workflows/build-containers.yaml` (1,225 bytes)
- `.github/workflows/main.yml` (823 bytes)
- `.vscode/launch.json` (5,585 bytes)
- `CLAUDE.md` (234 bytes)
- `ai-prompts/docker/phase1.md` (1,599 bytes)
- `ai-prompts/new-pipeline.md` (2,098 bytes)
- `ai-prompts/phase-14-update.md` (13,738 bytes)
- ... and 204 more files
