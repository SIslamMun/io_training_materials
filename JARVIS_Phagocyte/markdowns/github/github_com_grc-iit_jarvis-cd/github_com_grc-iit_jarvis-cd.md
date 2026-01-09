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
- **Extracted:** 2026-01-08T11:59:40.666382


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

### `builtin/builtin/arldm/README.md`

```markdown
The AR-LDM (Auto-Regressive Latent Diffusion Models) is a latent diffusion model auto-regressively conditioned on history captions and generated images.
See the [official repo](https://github.com/xichenpan/ARLDM) for more detail.

# Table of Content
0. [Dependencies](#0-dependencies)
1. [Installation](#1-installation)
2. [Running ARLDM](#2-running-arldm)
3. [ARLDM with Slurm](#3-arldm-with-slurm)
4. [ARLDM + Hermes](#4-arldm--hermes)
5. [ARLDM on Node Local Storage](#5-arldm-on-node-local-storage)
6. [ARLDM + Hermes on Node Local Storage](#6-arldm--hermes-on-node-local-storage)
7. ARLDM + Hermes with Multinodes Slurm (Not supported)



# 0. Dependencies

## 0.1. conda
- Prepare Conda
Get the miniconda3 installation script and run it
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh.sh
```

## 0.2. jarvis-cd & scspkg
Follow steps here: https://github.com/grc-iit/jarvis-cd


## 0.3. spack
Spack is used to install HDF5, MPICH, and Hermes.
Install spack steps are here: https://spack.readthedocs.io/en/latest/getting_started.html#installation

## 0.4. HDF5 (1.14.0+)
HDF5 is require, (1.14.0+) is required by Hermes and h5py==3.8.0.

Use spack to install hdf5
```bash
spack install hdf5@1.14.0+hl~mpi
```

## 0.5. MPI
Either OpenMPI or MPICH works, this is required by Hermes and mpi4py


Use spack to install mpich
```bash
spack install mpich@3.4.3
```

## 0.6. Installation Tools
You need `wget` and `gdown` to download the datasets online:
- wget
You can install wget either with `apt-get` or `spack`
```bash
sudo apt-get install wget
# or
spack install wget
spack load wget
# check if wget is usable
which wget
```
- gdown
```shell
python3 -m pip install gdown==4.5.1 # or 4.6.0
pip show gdown
```


# 1. Installation

## 1.1 create arldm scs package
```bash
scspkg create arldm
cd `scspkg pkg src arldm`
git clone https://github.com/candiceT233/ARLDM
cd ARLDM
git switch ares # Use the ares branch
export ARLDM_PATH=`scspkg pkg src arldm`/ARLDM
scspkg env set arldm ARLDM_PATH=$ARLDM_PATH HDF5_USE_FILE_LOCKING=FALSE
```


## 1.2 Prepare conda environment and python packages:
```bash
cd `scspkg pkg src arldm`/ARLDM

YOUR_HDF5_DIR="`which h5cc |sed 's/.\{9\}$//'`"
conda env create -f arldm_conda.yaml -n arldm
conda activate arldm
pip uninstall h5py;
HDF5_MPI="OFF" HDF5_DIR=${YOUR_HDF5_DIR} pip install --no-cache-dir --no-binary=h5py h5py==3.8.0
conda deactivate
```



# 2. Running ARLDM

## 2.1.0 Internet Access
Internet access is required when running this program for the first time, you will encounter below error:
```log
  File "/home/$USER/miniconda3/envs/arldm/lib/python3.8/site-packages/transformers/tokenization_utils_base.py", line 1761, in from_pretrained
    raise EnvironmentError(
OSError: Can't load tokenizer for 'runwayml/stable-diffusion-v1-5'. If you were trying to load it from 'https://huggingface.co/models', make sure you don't have a local directory with the same name. Otherwise, make sure 'runwayml/stable-diffusion-v1-5' is the correct path to a directory containing all relevant files for a CLIPTokenizer tokenizer.
```

## 2.1. Setup Environment
Currently setup input path in a shared storage, below is a example on Ares cluster.
Setup experiment input and ouput paths:
```bash
EXPERIMENT_PATH=~/experiments/arldm_run
export EXPERIMENT_INPUT_PATH=$EXPERIMENT_PATH/input_data

scspkg env set arldm EXPERIMENT_INPUT_PATH=$EXPERIMENT_INPUT_PATH

mkdir -p $EXPERIMENT_INPUT_PATH $EXPERIMENT_INPUT_PATH/zippack
```

## 2.2. Download Pretrain Model
The pretrain model is ~ 3.63 GB (~ 10 mins on Ares)
```bash
cd $EXPERIMENT_PATH
conda activate arldm
wget https://storage.googleapis.com/sfr-vision-language-research/BLIP/models/model_large.pth
export PRETRAIN_MODEL_PATH=`realpath model_large.pth`
scspkg env set arldm PRETRAIN_MODEL_PATH=$PRETRAIN_MODEL_PATH
conda deactivate
```

## 2.3. Download Input Data
You should prepare at least one dataset to run the script. There are 4 available datasets for download `vistsis`, `vistdii`, `pororo`, and `flintstones`.

### 2.3.1 VISTSIS and VISTDII

1. Download VISTSIS, original VIST-SIS (~23MB) url links [here](https://visionandlanguage.net/VIST/json_files/story-in-sequence/SIS-with-labels.tar.gz)
```shell
cd $EXPERIMENT_INPUT_PATH
wget https://visionandlanguage.net/VIST/json_files/story-in-sequence/SIS-with-labels.tar.gz
tar -vxf SIS-with-labels.tar.gz
mv sis vistsis # ~ 172M

# save downloaded package to different directory
mv SIS-with-labels.tar.gz $EXPERIMENT_INPUT_PATH/zippack
```

2. Download VISTSIS, original VIST-DII (~18MB) url links [here](https://visionandlanguage.net/VIST/json_files/description-in-isolation/DII-with-labels.tar.gz)
```shell
cd $EXPERIMENT_INPUT_PATH
wget https://visionandlanguage.net/VIST/json_files/description-in-isolation/DII-with-labels.tar.gz
tar -vxf DII-with-labels.tar.gz
mv dii vistdii # ~ 125M

# save downloaded package to different directory
mv DII-with-labels.tar.gz $EXPERIMENT_INPUT_PATH/zippack
```

3. Download the VIST images by running below command (this will take over 2 hours on Ares)
```shell
cd $ARLDM_PATH
conda activate arldm
python data_script/vist_img_download.py --json_dir $EXPERIMENT_INPUT_PATH/vistdii --img_dir $EXPERIMENT_INPUT_PATH/visit_img --num_process 12
```

### 2.3.3 flintstones 
* Original FlintstonesSV dataset [here](https://drive.google.com/file/d/1kG4esNwabJQPWqadSDaugrlF4dRaV33_/view?usp=sharing).
```shell
cd $EXPERIMENT_INPUT_PATH
gdown "1kG4esNwabJQPWqadSDaugrlF4dRaV33_&confirm=t" # ~10 mins on Ares
unzip flintstones_data.zip # 4.9G, ~2 mins on Ares
mv flintstones_data flintstones # 6.6G
mv flintstones_data.zip $EXPERIMENT_INPUT_PATH/zippack
```
<!-- gdown https://drive.google.com/u/0/uc?id=1kG4esNwabJQPWqadSDaugrlF4dRaV33_&export=download -->


### 2.3.2 pororo 
* Original PororoSV dataset [here](https://drive.google.com/file/d/11Io1_BufAayJ1BpdxxV2uJUvCcirbrNc/view?usp=sharing).
```shell
cd $EXPERIMENT_INPUT_PATH
gdown "11Io1_BufAayJ1BpdxxV2uJUvCcirbrNc&confirm=t" # ~30 mins on Ares
unzip pororo.zip # 15GB
mv pororo_png pororo # 17GB
mv pororo.zip $EXPERIMENT_INPUT_PATH/zippack
```
<!-- gdown https://drive.google.com/u/0/uc?id=11Io1_BufAayJ1BpdxxV2uJUvCcirbrNc&export=download -->


## 2.3. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

For details building resource graph, please refer to https://github.com/grc-iit/jarvis-cd/wiki/2.-Resource-Graph.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 2.4 Create a Pipeline

The Jarvis pipeline will store all configuration data needed by ARLDM.

```bash
jarvis pipeline create arldm_test
```

## 2.5. Save Environment
Create the environment variables needed by ARLDM.
```bash
spack load hdf5@1.14.0+hl~mpi
module load arldm
```
<!-- conda activate arldm -->

Store the current environment in the pipeline.
```bash
jarvis env build arldm \
+EXPERIMENT_PATH +EXPERIMENT_INPUT_PATH +EXPERIMENT_OUTPUT_PATH \
+ARLDM_PATH +PRETRAIN_MODEL_PATH
jarvis pipeline env copy arldm
```

## 2.6. Add pkgs to the Pipeline
Create a Jarvis pipeline with ARLDM.
```bash
jarvis pipeline append arldm runscript=vistsis
```

## 2.7. Run Experiment

Run the experiment, output are generated in `$EXPERIMENT_INPUT_PATH/output_data`.
```bash
jarvis pipeline run
```

## 2.8. Clean Data

Clean data produced by ARLDM
```bash
jarvis pipeline clean
```



# 3. ARLDM With Slurm

## 3.1 Local Cluster
`ppn` must equal or greater than `num_workers`,which is default to 1.
```bash
jarvis pipeline sbatch job_name=arldm_test nnodes=1 ppn=2 output_file=./arldm_test.out error_file=./arldm_test.err
```

## 3.2 Multi Nodes Cluster (TODO)
ARLDM with jarvis-cd is currently only set to run with single node and using CPU.
    - Multiple CPU worker not tested
    - GPU not tested



# 4. ARLDM + Hermes

## 4.0. Dependencies
### 4.0.1 HDF5
Hermes must compile with HDF5, makesure [download HDF5-1.14.0 with spack](#04-hdf5-1140).

### 4.0.2 Install Hermes dependencies with spack
```bash
spack load hdf5@1.14.0+hl~mpi mpich@3.4.3
spack install hermes_shm ^hdf5@1.14.0+hl~mpi ^mpich@3.4.3
```

### 4.0.3 Install Hermes with scspkg
1. Option 1: build with POSIX adaptor
```bash
spack load hermes_shm
scspkg create hermes
cd `scspkg pkg src hermes`
git clone https://github.com/HDFGroup/hermes
cd hermes
mkdir build
cd build
cmake ../ -DCMAKE_BUILD_TYPE="Release" \
    -DCMAKE_INSTALL_PREFIX=`scspkg pkg root hermes` \
    -DHERMES_MPICH="ON" \
    -DHERMES_ENABLE_POSIX_ADAPTER="ON" \
```

2. Option 2: build with VFD adaptor (This is not working yet)
```bash
spack load hermes_shm
scspkg create hermes
cd `scspkg pkg src hermes`
git clone https://github.com/HDFGroup/hermes
cd hermes
mkdir build
cd build
cmake ../ -DCMAKE_BUILD_TYPE="Release" \
    -DCMAKE_INSTALL_PREFIX=`scspkg pkg root hermes` \
    -DHERMES_ENABLE_MPIIO_ADAPTER="ON" \
    -DHERMES_MPICH="ON" \
    -DHERMES_ENABLE_POSIX_ADAPTER="ON" \
    -DHERMES_ENABLE_STDIO_ADAPTER="ON" \
    -DHERMES_ENABLE_VFD="ON" \
```

## 4.1. Setup Environment

Create the environment variables needed by Hermes + ARLDM
```bash
RUN_SCRIPT=vistsis # can change to other datasets
spack load hermes_shm
module load hermes arldm
```

## 4.2. Create a Resource Graph

Same as [above](#2-create-a-resource-graph).

## 4.3. Create a Pipeline

The Jarvis pipeline will store all configuration data needed by Hermes
and ARLDM.

```bash
jarvis pipeline create hermes_arldm_test
```

## 4.4. Save Environment

Store the current environment in the pipeline.
```bash
jarvis pipeline env build +PRETRAIN_MODEL_PATH +EXPERIMENT_INPUT_PATH +ARLDM_PATH
```

## 4.5. Add pkgs to the Pipeline

Create a Jarvis pipeline with Hermes, using the Hermes POSIX interceptor.
```bash
jarvis pipeline append hermes_run --sleep=10 include=$EXPERIMENT_INPUT_PATH/${RUN_SCRIPT}_out.h5
jarvis pipeline append hermes_api +posix
jarvis pipeline append arldm runscript=vistsis with_hermes=true
```

## 4.6. Run the Experiment

Run the experiment, output are generated in `$EXPERIMENT_INPUT_PATH/output_data`.
```bash
jarvis pipeline run
```

## 4.7. Clean Data

To clean data produced by Hermes + ARLDM:
```bash
jarvis pipeline clean
```



# 5. ARLDM on Node Local Storage
For cluster that has node local storage, you can stagein data from shared storage, then run arldm.

## 5.1 Setup Environment
Currently setup DEFAULT input path in a shared storage, below is a example on Ares cluster using node local nvme.
```bash
RUN_SCRIPT=vistsis # can change to other datasets
EXPERIMENT_PATH=~/experiments/arldm_run # NFS
SHARED_INPUT_PATH=$EXPERIMENT_PATH/input_data # NFS
cd $EXPERIMENT_PATH; export PRETRAIN_MODEL_PATH=`realpath model_large.pth`

LOCAL_EXPERIMENT_PATH=/mnt/nvme/$USER/arldm_run
LOCAL_INPUT_PATH=$LOCAL_EXPERIMENT_PATH/input_data
```

## 5.2. Download Pretrain Model and Input Data
Same as above [download pretrain](#22-download-pretrain-model) and [download input](#23-download-input-data).

## 5.3. Create a Resource Graph
Same as [above](#23-create-a-resource-graph)

## 5.4. Create a Pipeline

The Jarvis pipeline will store all configuration data needed by ARLDM.

```bash
jarvis pipeline create arldm_local
```

## 5.5. Save Environment
Create the environment variables needed by ARLDM.
```bash
spack load hdf5@1.14.0+hl~mpi mpich@3.4.3
module load arldm
```


Store the current environment in the pipeline.
```bash
jarvis pipeline env build +PRETRAIN_MODEL_PATH +EXPERIMENT_INPUT_PATH +ARLDM_PATH
```


## 5.6. Add pkgs to the Pipeline
Add data_stagein to pipeline before arldm.
- For `RUN_SCRIPT=vistsis` you need to stage in three different input directories:
```bash 
jarvis pipeline append data_stagein dest_data_path=$LOCAL_INPUT_PATH \
user_data_paths=$SHARED_INPUT_PATH/vistdii,$SHARED_INPUT_PATH/vistsis,$SHARED_INPUT_PATH/visit_img,$PRETRAIN_MODEL_PATH \
mkdir_datapaths=$LOCAL_INPUT_PATH
```

- For other `RUN_SCRIPT`, you only need to stagein one directory:
```bash 
RUN_SCRIPT=pororo
jarvis pipeline append data_stagein dest_data_path=$LOCAL_INPUT_PATH \
user_data_paths=$SHARED_INPUT_PATH/$RUN_SCRIPT \
mkdir_datapaths=$LOCAL_INPUT_PATH
```


Create a Jarvis pipeline with ARLDM.
```bash
jarvis pipeline append arldm runscript=$RUN_SCRIPT local_exp_dir=$LOCAL_INPUT_PATH
```

## 5.7. Run the Experiment

Run the experiment, output are generated in `$LOCAL_INPUT_PATH/output_data`.
```bash
jarvis pipeline run
```

## 5.8. Clean Data

To clean data produced by Hermes + ARLDM:
```bash
jarvis pipeline clean
```



# 6. ARLDM + Hermes on Node Local Storage
Every step the same as [ARLDM + Hermes](#4-arldm-with-hermes), except for when creating a Jarvis pipeline with Hermes, using the Hermes VFD interceptor:
- Example using `RUN_SCRIPT=vistsis` you need to stage in three different input directories.
```bash
# Setup env
RUN_SCRIPT=vistsis # can change to other datasets
EXPERIMENT_PATH=~/experiments/arldm_run # NFS
SHARED_INPUT_PATH=$EXPERIMENT_PATH/input_data # NFS
cd $EXPERIMENT_PATH; export PRETRAIN_MODEL_PATH=`realpath model_large.pth`

LOCAL_EXPERIMENT_PATH=/mnt/nvme/$USER/arldm_run
LOCAL_INPUT_PATH=$LOCAL_EXPERIMENT_PATH/input_data

# add pkg to pipeline
jarvis pipeline append data_stagein dest_data_path=$LOCAL_INPUT_PATH \
user_data_paths=$SHARED_INPUT_PATH/vistdii,$SHARED_INPUT_PATH/vistsis,$SHARED_INPUT_PATH/visit_img,$PRETRAIN_MODEL_PATH \
mkdir_datapaths=$LOCAL_INPUT_PATH

jarvis pipeline append hermes_run --sleep=10 include=$LOCAL_INPUT_PATH/${RUN_SCRIPT}_out.h5

jarvis pipeline append hermes_api +posix

jarvis pipeline append arldm runscript=vistsis arldm_path="`scspkg pkg src arldm`/ARLDM" with_hermes=true local_exp_dir=$LOCAL_INPUT_PATH
```


# 7. ARLDM + Hermes with Multinodes Slurm (TODO)
Multinodes ARLDM is not supported yet.
```

### `builtin/builtin/asan/README.md`

```markdown
Hermes is a multi-tiered I/O buffering platform. This is module encompasses the
interceptors (MPI-IO, STDIO, POSIX, and VFD) provided in Hermes.

# Installation

```bash
spack install hermes@master
```

```bash
jarvis pipeline create hermes
jarvis pipeline append hermes --sleep=5
jarvis pipeline append hermes_api +posix -mpich
jarvis pipeline run
```
```

### `builtin/builtin/cm1/README.md`

```markdown
CM1 is a simulation code.

# Dependencies

```bash
spack install intel-oneapi-compilers
spack load intel-oneapi-compilers
spack compilers add
spack install h5z-zfp%intel
```

# Compiling / Installing

```bash
git clone git@github.com:lukemartinlogan/cm1r19.8-LOFS.git
cd cm1r19.8-LOFS
# COREX * COREY is the number of cores you intend to use on the system
# They do not need to be 2 and 2 here, but this is how our configurations are compiled for now
COREX=2 COREY=2 bash buildCM1-spack.sh
export PATH=${PWD}/run:${PATH}
export CM1_PATH=${PWD}
```

# Usage

```bash
jarvis pipeline create cm1
jarvis pipeline append cm1 corex=2 corey=2
```
```

### `builtin/builtin/cosmic_tagger/README.md`

```markdown
# Conda
Get the miniconda3 installation script and run it
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

# Cosmic Tagger
[Cosmic Tagger](https://github.com/coreyjadams/CosmicTagger) trains a CNN to separate cosmic pixels.

Conda:
```
conda create -n cosmic_tagger python==3.7
conda activate cosmic_tagger
conda install cmake hdf5 scikit-build numpy
```

Install Larc3
```
git clone https://github.com/DeepLearnPhysics/larcv3.git
cd larcv3
git submodule update --init
pip install -e .
```

Download cosmic tagger
```
git clone https://github.com/coreyjadams/CosmicTagger.git
cd CosmicTagger
pip install -r requirements.txt
```
```

### `builtin/builtin/darshan/README.md`

```markdown
Darshan is an I/O profiling tool. This repo intercepts application I/O and
dumps them into a log that can be parsed to collect metrics such as I/O time.

# Dependencies

# Compiling / Installing

```bash
scspkg create darshan
cd $(scspkg pkg src darshan)
git clone https://github.com/darshan-hpc/darshan.git
cd darshan
git fetch --all --tags --prune
git checkout tags/darshan-3.4.4
./prepare.sh

cd darshan-runtime
./configure --with-log-path=/darshan-logs \
--with-jobid-env=PBS_JOBID \
--with-log-path-by-env=DARSHAN_LOG_DIR \
--prefix=$(scspkg pkg root darshan) \
--enable-hdf5-mod \
CC=mpicc
# --enable-pnetcdf-mod \
make -j32
make install

cd ../darshan-util
./configure \
--prefix=$(scspkg pkg root darshan) \
--enable-pydarshan
make -j32
make install
```

# Usage

Create darshan environment:
```bash
module load darshan
jarvis env build darshan
```

Create a pipeline:
```bash
jarvis pipeline append darshan log_dir=${HOME}/darshan_logs
jarvis pipeline append ior
```

Run the pipeline:
```bash
jarvis pipeline run
```

# Analysis

There are several ways to analyze the output of Darshan:
```
darshan-job-summary.pl ${HOME}/darshan_logs
```
```

### `builtin/builtin/ddmd/README.md`

```markdown
# DeepDriveMD-F (DDMD)
DeepDriveMD: Deep-Learning Driven Adaptive Molecular Simulations (file-based continual learning loop).
See the [official repo](https://github.com/DeepDriveMD/DeepDriveMD-pipeline) for more detail.

# Table of Content
0. [Dependencies](#0-dependencies)
1. [Installation](#1-installation)
2. [Running DDMD](#2-running-ddmd)
3. [DDMD with Slurm](#3-ddmd-with-slurm)
4. [DDMD + Hermes](#4-ddmd--hermes)
5. [DDMD on Node Local Storage (FIXME)](#5-ddmd-on-node-local-storage)
6. [DDMD + Hermes on Node Local Storage (FIXME)](#6-ddmd--hermes-on-node-local-storage)
7. DDMD + Hermes with Multinodes Slurm (TODO)



# 0. Dependencies

## 0.1. conda
- Prepare Conda
Get the miniconda3 installation script and run it
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh.sh
```

## 0.2. jarvis-cd & scspkg
Follow steps here: https://github.com/grc-iit/jarvis-cd


## 0.3. spack
Spack is used to install HDF5, MPICH, and Hermes.
Install spack steps are here: https://spack.readthedocs.io/en/latest/getting_started.html#installation

## 0.4. HDF5 (1.14.0+)
HDF5 is require, (1.14.0+) is required by Hermes and h5py==3.8.0.

Use spack to install hdf5
```bash
spack install hdf5@1.14.0+hl~mpi
```


## 0.5. MPI
Either OpenMPI or MPICH works, this is required by Hermes(VFD depend on MPIIO adaptor)


Use spack to install mpich
```bash
spack install mpich@3.4.3
``` 



# 1. Installation

## 1.1 create ddmd scs package
```bash
scspkg create ddmd
cd `scspkg pkg src ddmd`
git clone https://github.com/candiceT233/deepdrivemd_pnnl.git deepdrivemd
cd deepdrivemd
export DDMD_PATH="`pwd`"
scspkg env set ddmd DDMD_PATH=$DDMD_PATH HDF5_USE_FILE_LOCKING=FALSE
```


## 1.2 Prepare conda environment and python packages
### 1.2.1 Set conda environment variable
```bash
export CONDA_OPENMM=hermes_openmm7_ddmd
export CONDA_PYTORCH=hm_ddmd_pytorch
```


### 1.2.2 Create the respective conda environment with YML files
```bash
cd "`scspkg pkg src ddmd`/deepdrivemd"
conda env create -f ddmd_openmm7.yaml --name=${CONDA_OPENMM}
conda env create -f ddmd_pytorch.yaml --name=${CONDA_PYTORCH}
```



### 1.2.2 Update the conda environment python packages
- for `CONDA_OPENMM`
```bash
cd `scspkg pkg src ddmd`
conda activate $CONDA_OPENMM
export DDMD_PATH="`pwd`"

cd $DDMD_PATH/submodules/MD-tools
pip install -e .

cd $DDMD_PATH/submodules/molecules
pip install -e .

pip uninstall h5py;
HDF5_MPI="OFF" HDF5_DIR=${YOUR_HDF5_DIR} pip install --no-cache-dir --no-binary=h5py h5py==3.8.0

conda deactivate
```


- for `CONDA_PYTORCH`
```bash
cd `scspkg pkg src ddmd`
conda activate $CONDA_PYTORCH
export DDMD_PATH="`pwd`"

cd $DDMD_PATH/submodules/MD-tools
pip install .

cd $DDMD_PATH/submodules/molecules
pip install .

cd $DDMD_PATH
pip install .

pip uninstall h5py;
HDF5_MPI="OFF" HDF5_DIR=${YOUR_HDF5_DIR} pip install --no-cache-dir --no-binary=h5py h5py==3.8.0

conda deactivate
```


# 2. Running DDMD

## 2.1. Setup Environment
Currently setup input path in a shared storage.
Setup experiment input and ouput paths:
```bash
EXPERIMENT_PATH=~/experiments/ddmd_runs #NFS
mkdir -p $EXPERIMENT_PATH
```


## 2.2. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

For details building resource graph, please refer to https://github.com/grc-iit/jarvis-cd/wiki/2.-Resource-Graph.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 2.3 Create a Pipeline

The Jarvis pipeline will store all configuration data needed by DDMD.

```bash
jarvis pipeline create ddmd_test
```

## 2.4. Save Environment
Create the environment variables needed by DDMD.
```bash
spack load hdf5@1.14.0+hl~mpi mpich
module load ddmd
```

Store the current environment in the pipeline.
```bash
jarvis pipeline env build +CONDA_OPENMM +CONDA_PYTORCH +DDMD_PATH
```

## 2.5. Add pkgs to the Pipeline
Create a Jarvis pipeline with DDMD.
```bash
jarvis pipeline append ddmd
```

## 2.6. Run Experiment

Run the experiment
```bash
jarvis pipeline run
```

## 2.8. Clean Data

Clean data produced by DDMD
```bash
jarvis pipeline clean
```



# 3. DDMD With Slurm

## 3.1 Local Cluster
`ppn` must equal or greater than `num_workers`,which is default to 1.
```bash
jarvis pipeline sbatch job_name=ddmd_test nnodes=1 ppn=2 output_file=./ddmd_test.out error_file=./ddmd_test.err
```

## 3.2 Multi Nodes Cluster (TODO)
DDMD with jarvis-cd is currently only set to run with single node and using CPU.
    - Multiple CPU worker not tested
    - GPU not tested



# 4. DDMD + Hermes

## 4.0. Dependencies
### 4.0.1 HDF5
Hermes must compile with HDF5, makesure [download HDF5-1.14.0 with spack](#04-hdf5-1140).

### 4.0.2 Install Hermes dependencies with spack
```bash
spack load hdf5@1.14.0+hl~mpi mpich@3.4.3
spack install hermes_shm ^hdf5@1.14.0+hl~mpi ^mpich@3.4.3
```

### 4.0.3 Install Hermes with scspkg
```bash
spack load hermes_shm
scspkg create hermes
cd `scspkg pkg src hermes`
git clone https://github.com/HDFGroup/hermes
cd hermes
mkdir build
cd build
cmake ../ -DCMAKE_BUILD_TYPE="Release" \
    -DCMAKE_INSTALL_PREFIX=`scspkg pkg root hermes` \
    -DHERMES_ENABLE_MPIIO_ADAPTER="ON" \
    -DHERMES_MPICH="ON" \
    -DHERMES_ENABLE_POSIX_ADAPTER="ON" \
    -DHERMES_ENABLE_STDIO_ADAPTER="ON" \
    -DHERMES_ENABLE_VFD="ON" \

```

## 4.1. Setup Environment

Create the environment variables needed by Hermes + DDMD
```bash
spack load hermes_shm
module load hermes ddmd
```

## 4.2. Create a Resource Graph

Same as [above](#2-create-a-resource-graph).

## 4.3. Create a Pipeline

The Jarvis pipeline will store all configuration data needed by Hermes
and DDMD.

```bash
jarvis pipeline create hermes_ddmd_test
```

## 4.4. Save Environment

Store the current environment in the pipeline.
```bash
jarvis pipeline env build +CONDA_OPENMM +CONDA_PYTORCH +DDMD_PATH
```

## 4.5. Add pkgs to the Pipeline

Create a Jarvis pipeline with Hermes, using the Hermes VFD interceptor.
```bash
jarvis pipeline append hermes_run --sleep=10 include=$EXPERIMENT_PATH
jarvis pipeline append hermes_api +vfd
jarvis pipeline append ddmd update_envar=true
```

## 4.6. Run the Experiment (TODO)

Run the experiment
```bash
jarvis pipeline run
```

## 4.7. Clean Data

To clean data produced by DDMD:
```bash
jarvis pipeline clean
```



# 5. DDMD on Node Local Storage
For cluster that has node local storage, you can stagein data from shared storage, then run ddmd.

## 5.1 Setup Environment
Currently setup DEFAULT input path in a shared storage, below is a example on Ares cluster using node local nvme.
```bash
RUN_SCRIPT=vistsis # can change to other datasets
EXPERIMENT_PATH=~/experiments/ddmd_run # NFS
INPUT_PATH=$EXPERIMENT_PATH/input_data # NFS
cd $EXPERIMENT_PATH; export PRETRAIN_MODEL_PATH=`realpath model_large.pth`

LOCAL_EXPERIMENT_PATH=/mnt/nvme/$USER/ddmd_run
LOCAL_INPUT_PATH=$LOCAL_EXPERIMENT_PATH/input_data
LOCAL_OUTPUT_PATH=$LOCAL_EXPERIMENT_PATH/output_data
```

## 5.2. Download Pretrain Model and Input Data
Same as above [download pretrain](#22-download-pretrain-model) and [download input](#23-download-input-data).

## 5.3. Create a Resource Graph
Same as [above](#23-create-a-resource-graph)

## 5.4. Create a Pipeline

The Jarvis pipeline will store all configuration data needed by DDMD.

```bash
jarvis pipeline create ddmd_local
```

## 5.5. Save Environment
Create the environment variables needed by DDMD.
```bash
spack load hdf5@1.14.0+hl~mpi mpich@3.4.3
module load ddmd
```


Store the current environment in the pipeline.
```bash
jarvis pipeline env build +CONDA_OPENMM +CONDA_PYTORCH +DDMD_PATH
```


## 5.6. Add pkgs to the Pipeline
Add data_stagein to pipeline before ddmd.
- For `RUN_SCRIPT=vistsis` you need to stage in three different input directories:
```bash 
jarvis pipeline append data_stagein dest_data_path=$LOCAL_INPUT_PATH \
user_data_paths=$INPUT_PATH/vistdii,$INPUT_PATH/vistsis,$INPUT_PATH/visit_img,$PRETRAIN_MODEL_PATH \
mkdir_datapaths=$LOCAL_INPUT_PATH,$LOCAL_OUTPUT_PATH
```

- For other `RUN_SCRIPT`, you only need to stagein one directory:
```bash 
RUN_SCRIPT=pororo
jarvis pipeline append data_stagein dest_data_path=$LOCAL_INPUT_PATH \
user_data_paths=$INPUT_PATH/$RUN_SCRIPT \
mkdir_datapaths=$LOCAL_INPUT_PATH,$LOCAL_OUTPUT_PATH
```


Create a Jarvis pipeline with DDMD.
```bash
jarvis pipeline append ddmd runscript=$RUN_SCRIPT ddmd_path="`scspkg pkg src ddmd`/DDMD" local_exp_dir=$LOCAL_EXPERIMENT_PATH
```

## 5.7. Run the Experiment

Run the experiment
```bash
jarvis pipeline run
```

## 5.8. Clean Data

To clean data produced by Hermes + DDMD:
```bash
jarvis pipeline clean
```



# 6. DDMD + Hermes on Node Local Storage
Every step the same as [DDMD + Hermes](#4-ddmd-with-hermes), except for when creating a Jarvis pipeline with Hermes, using the Hermes VFD interceptor:
- Example using `RUN_SCRIPT=vistsis` you need to stage in three different input directories.
```bash
# Setup env
RUN_SCRIPT=vistsis # can change to other datasets
EXPERIMENT_PATH=~/experiments/ddmd_run # NFS
INPUT_PATH=$EXPERIMENT_PATH/input_data # NFS
cd $EXPERIMENT_PATH; export PRETRAIN_MODEL_PATH=`realpath model_large.pth`

LOCAL_EXPERIMENT_PATH=/mnt/nvme/$USER/ddmd_run
LOCAL_INPUT_PATH=$LOCAL_EXPERIMENT_PATH/input_data
LOCAL_OUTPUT_PATH=$LOCAL_EXPERIMENT_PATH/output_data

# add pkg to pipeline
jarvis pipeline append data_stagein dest_data_path=$LOCAL_INPUT_PATH \
user_data_paths=$INPUT_PATH/vistdii,$INPUT_PATH/vistsis,$INPUT_PATH/visit_img,$PRETRAIN_MODEL_PATH \
mkdir_datapaths=$LOCAL_INPUT_PATH,$LOCAL_OUTPUT_PATH

jarvis pipeline append hermes_run --sleep=10 include=$LOCAL_EXPERIMENT_PATH

jarvis pipeline append hermes_api +vfd

jarvis pipeline append ddmd runscript=vistsis ddmd_path="`scspkg pkg src ddmd`/DDMD" update_envar=true local_exp_dir=$LOCAL_EXPERIMENT_PATH
```


# 7. DDMD + Hermes with Multinodes Slurm (TODO)
Multinodes DDMD is not supported yet.
```

### `builtin/builtin/dlio_benchmark/README.md`

```markdown
DLIO is an I/O benchmark for Deep Learning, aiming at emulating the I/O behavior of various deep learning applications.

# Installation

```bash
git clone https://github.com/argonne-lcf/dlio_benchmark
cd dlio_benchmark/
pip install .
```

# DLIO

## 1. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 2. Create a Pipeline

The Jarvis pipeline will store all configuration data.
```bash
jarvis pipeline create dlio_test
```

## 4. Add pkgs to the Pipeline

Create a Jarvis pipeline
```bash
jarvis pipeline append dlio_benchmark workload=unet3d_a100 generate_data=True data_path=/path/to/generated_data checkpoint_path=/path/to/checkpoints
```
Note: you can modify the dlio_benchmark configuration file by changing the modifying the dlio_benchmark.yaml file directly, and then execute `jarvis ppl update` to update the configuration. 

## 5. Run Experiment

Run the experiment
```bash
jarvis pipeline run
```

## 6. Clean Data

Clean produced data
```bash
jarvis pipeline clean
```
```

### `builtin/builtin/filebench/README.md`

```markdown
Filebench is a cloud workload generator.

# Installation

```bash
spack install filebench
```
```

### `builtin/builtin/fio/README.md`

```markdown
FIO

# Installation

```bash
spack install fio
```

# FIO
```

### `builtin/builtin/gadget2/README.md`

```markdown
GADGET is a freely available code for cosmological N-body/SPH simulations on massively parallel computers with distributed memory. GADGET uses an explicit communication model that is implemented with the standardized MPI communication interface. The code can be run on essentially all supercomputer systems presently in use, including clusters of workstations or individual PCs.

GADGET computes gravitational forces with a hierarchical tree algorithm (optionally in combination with a particle-mesh scheme for long-range gravitational forces) and represents fluids by means of smoothed particle hydrodynamics (SPH). The code can be used for studies of isolated systems, or for simulations that include the cosmological expansion of space, both with or without periodic boundary conditions. In all these types of simulations, GADGET follows the evolution of a self-gravitating collisionless N-body system, and allows gas dynamics to be optionally included. Both the force computation and the time stepping of GADGET are fully adaptive, with a dynamic range which is, in principle, unlimited.

https://wwwmpa.mpa-garching.mpg.de/gadget/

# Installation

```bash
spack install hdf5@1.14.1 gsl@2.1 fftw@2
scspkg create gadget2
cd $(scspkg pkg src gadget2)
git clone https://github.com/lukemartinlogan/gadget2.git
export GADGET2_PATH=$(scspkg pkg src gadget2)/gadget2
export FFTW_PATH=$(spack find --format "{PREFIX}" fftw@2)
```

# Create environment

```bash
spack load hdf5@1.14.1 gsl@2.1 fftw@2
jarvis env build gadget2 +GADGET2_PATH +FFTW_PATH
```

# Gassphere Pipeline

```bash
jarvis pipeline create gassphere
jarvis pipeline env copy gadget2
jarvis pipeline append gadget2
jarvis pkg configure gadget2 \
test_case=gadget2 \
out=${HOME}/gadget2
jarvis pipeline run
```

# NGenIC Pipeline

```bash
jarvis pipeline create gassphere
jarvis pipeline env copy gadget2
jarvis pipeline append gadget2
jarvis pkg configure gadget2 \
test_case=gassphere-ngen \
out=${HOME}/gadget2 \
ic=hello
jarvis pipeline run
```
```

### `builtin/builtin/gadget2_df/README.md`

```markdown
GADGET is a freely available code for cosmological N-body/SPH simulations on massively parallel computers with distributed memory. GADGET uses an explicit communication model that is implemented with the standardized MPI communication interface. The code can be run on essentially all supercomputer systems presently in use, including clusters of workstations or individual PCs.

GADGET computes gravitational forces with a hierarchical tree algorithm (optionally in combination with a particle-mesh scheme for long-range gravitational forces) and represents fluids by means of smoothed particle hydrodynamics (SPH). The code can be used for studies of isolated systems, or for simulations that include the cosmological expansion of space, both with or without periodic boundary conditions. In all these types of simulations, GADGET follows the evolution of a self-gravitating collisionless N-body system, and allows gas dynamics to be optionally included. Both the force computation and the time stepping of GADGET are fully adaptive, with a dynamic range which is, in principle, unlimited.

https://wwwmpa.mpa-garching.mpg.de/gadget/

# Installation

Check the README for gadget2.

# Create Pipeline

```bash
jarvis pipeline create ngenic
jarvis pipeline env copy gadget2
jarvis pipeline append gadget2_df
jarvis pkg configure gadget2_df \
nparticles=100000 \
nprocs=4
jarvis pipeline run
```
```

### `builtin/builtin/gray_scott/README.md`

```markdown
Gray-Scott is a 3D 7-Point stencil code

# Installation

```bash
scspkg create gray-scott
cd `scspkg pkg src gray-scott`
git clone https://github.com/pnorbert/adiosvm
cd adiosvm/Tutorial/gs-mpiio
mkdir build
pushd build
cmake ../ -DCMAKE_BUILD_TYPE=Release
make -j8
export GRAY_SCOTT_PATH=`pwd`
scspkg env set gray_scott GRAY_SCOTT_PATH="${GRAY_SCOTT_PATH}"
scspkg env prepend gray_scott PATH "${GRAY_SCOTT_PATH}"
module load gray_scott
spack load mpi adios2
```

# Gray Scott

## 1. Setup Environment

Create the environment variables needed by Gray Scott
```bash
module load gray_scott
spack load mpi
```````````

## 1. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 2. Create a Pipeline

The Jarvis pipeline will store all configuration data needed by Gray Scott.

```bash
jarvis pipeline create gray-scott-test
```

## 3. Save Environment

Store the current environment in the pipeline.
```bash
jarvis pipeline env build
```

## 4. Add pkgs to the Pipeline

Create a Jarvis pipeline with Gray Scott
```bash
jarvis pipeline append gray_scott
```

## 5. Run Experiment

Run the experiment
```bash
jarvis pipeline run
```

## 6. Clean Data

Clean data produced by Gray Scott
```bash
jarvis pipeline clean
```

# Gray Scott With Hermes

## 1. Setup Environment

Create the environment variables needed by Hermes + Gray Scott
```bash
# On personal
spack install hermes@master adios2
spack load hermes adios2
# On Ares
module load hermes/master-feow7up adios2/2.9.0-mmkelnu
# export GRAY_SCOTT_PATH=${HOME}/adiosvm/Tutorial/gs-mpiio/build
export PATH="${GRAY_SCOTT_PATH}:$PATH"
```

## 2. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile.txt
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 3. Create a Pipeline

The Jarvis pipeline will store all configuration data needed by Hermes
and Gray Scott.

```bash
jarvis pipeline create gs-hermes
```

## 3. Save Environment

Store the current environment in the pipeline.
```bash
jarvis pipeline env build
```

## 4. Add pkgs to the Pipeline

Create a Jarvis pipeline with Hermes, the Hermes MPI-IO interceptor,
and gray-scott
```bash
jarvis pipeline append hermes --sleep=10 --output_dir=${HOME}/gray-scott
jarvis pipeline append hermes_api +mpi
jarvis pipeline append gray_scott
```

## 5. Run the Experiment

Run the experiment
```bash
jarvis pipeline run
```

## 6. Clean Data

To clean data produced by Hermes + Gray-Scott:
```bash
jarvis pipeline clean
```
```

### `builtin/builtin/hermes_api/README.md`

```markdown
Hermes is a multi-tiered I/O buffering platform. This is module encompasses the
interceptors (MPI-IO, STDIO, POSIX, and VFD) provided in Hermes.

# Installation

Check either the hermes or hermes_run jarvis package.

# Usage

```bash
jarvis pipeline create hermes
jarvis pipeline append hermes --sleep=5
jarvis pipeline append hermes_api +posix
jarvis pipeline run
```
```

### `builtin/builtin/hermes_api_bench/README.md`

```markdown
Hermes is a multi-tiered I/O buffering platform. This module encompasses
a series of microbenchmarks used to test the performance of the Hermes
native API

# Installation

Check the hermes_run jarvis package.

# Usage

```
spack load hermes
jarvis pipeline create hermes_bench
jarvis pipeline env build
jarvis pipeline append hermes --sleep=5
jarvis pipeline append hermes_api_bench
jarvis pipeline run
```

## PutGet benchmark

```
jarvis pkg configure hermes_api_bench \
mode=putget \
blob_size=4k \
blobs_per_rank=16 \
nprocs=2
```

## PartialPutGet benchmark

```
jarvis pkg configure hermes_api_bench \
mode=pputget \
blobs_per_rank=64 \
blob_size=1m \
part_size=4k \
nprocs=64
```

## Create Bucket benchmark

```
jarvis pkg configure hermes_api_bench \
mode=create_bkt \
bkts_per_rank=256 \
nprocs=16
```

## Get Bucket benchmark

```
jarvis pkg configure hermes_api_bench \
mode=get_bkt \
bkts_per_rank=1024 \
nprocs=64
```

## Delete Bucket benchmark

```
jarvis pkg configure hermes_api_bench \
mode=del_bkt \
bkts_per_rank=1024 \
blobs_per_bkt=1024 \
nprocs=64
```
```

### `builtin/builtin/hermes_posix_tests/README.md`

```markdown
These unit tests validate the POSIX interceptor of Hermes.
```

### `builtin/builtin/hermes_run/README.md`

```markdown
Hermes 1.1 is built on top of a distributed microkernel for data services.

# Installation

```bash
spack install hermes@dev-1.1
```

OR

```bash 
spack install hermes_shm
spack load hermes_shm
git clone https://github.com/lukemartinlogan/hermes.git -b hermes-1.1
cd hermes
mkdir build
cd build
cmake ../
make -j8
cd ../

scspkg create hermes_run
scspkg env set hermes_run HERMES_PATH=${PWD}
scspkg env prepend hermes_run PATH ${PWD}/build/bin
scspkg env prepend hermes_run LD_LIBRARY_PATH ${PWD}/build/bin
scspkg env prepend hermes_run LIBRARY_PATH ${PWD}/build/bin
module load hermes_run
```

# Hermes Runtime

## 1. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 2. Create a Pipeline

The Jarvis pipeline will store all configuration data.
```bash
jarvis pipeline create hermes_run_test
```

## 3. Load Environment

Create the environment variables
```bash
spack load hermes@dev-1.1
# OR 
spack load mochi-thallium~cereal@0.10.1 cereal catch2@3.0.1 mpich \
yaml-cpp boost hermes_shm
module load hermes_run
```````````

Store the current environment in the pipeline.
```bash
jarvis pipeline env build
```

## 4. Add pkgs to the Pipeline

Create a Jarvis pipeline
```bash
jarvis pipeline append hermes_run --sleep=5
```

## 5. Run Experiment

Run the experiment
```bash
jarvis pipeline run
```

## 6. Clean Data

Clean produced data
```bash
jarvis pipeline clean
```

# Hermes Runtime (+IOR)

To install IOR:
```
spack install ior
```

## 1. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 2. Create a Pipeline

The Jarvis pipeline will store all configuration data.
```bash
jarvis pipeline create hermes_ior_test
```

## 3. Load Environment

Create the environment variables
```bash
spack load hermes@dev-1.1 ior
# OR 
spack load mochi-thallium~cereal@0.10.1 cereal catch2@3.0.1 mpich \
yaml-cpp boost hermes_shm ior
module load hermes_run
```````````

Store the current environment in the pipeline.
```bash
jarvis pipeline env build
```

## 4. Add pkgs to the Pipeline

Create a Jarvis pipeline
```bash
jarvis pipeline append hermes_run --sleep=5
jarvis pipeline append hermes_api +posix -mpi
jarvis pipeline append ior api=posix xfer=4k block=1m out=/tmp/test_hermes/ior.bin
```

## 5. Run Experiment

Run the experiment
```bash
jarvis pipeline run
```

## 6. Clean Data

Clean produced data
```bash
jarvis pipeline clean
```
```

### `builtin/builtin/hermes_unit_tests/README.md`

```markdown

Some basic unit tests for the Hermes native API.
```

### `builtin/builtin/hermes_viz/README.md`

```markdown

This is the visualizer used for Hermes.

# 1. Installation
```bash
# git clone https://github.com/JaimeCernuda/HermesViz
scspkg create HermesViz
cd $(scspkg pkg src HermesViz)
git clone https://github.com/JaimeCernuda/hermes -b visualizer
scspkg env prepend HermesViz HERMES_VIZ_ROOT "${PWD}/hermes/visualizer"
scspkg env prepend HermesViz PATH "${PWD}/hermes/visualizer"
scspkg env prepend HermesViz PYTHONPATH "${PWD}/hermes/visualizer"
module load HermesViz
python3 -m pip install flask
# NOTE(llogan): flask depends on click2, which may conflict with coverage-lcov installed by jarvis-util
# Just unintall coverage-lcov
python3 -m pip install -r hermes/visualizer/requirments.txt
```

# 2. Usage

## 2.1. Master Node
```
local_port=5001
remote_port=5001
ares_node=ares-comp-18
ssh -L ${local_port}:localhost:${remote_port} -fN ${ares_node}

local_port=4000
remote_port=4000
ares_node=ares-comp-25
ssh -L ${local_port}:localhost:${remote_port} -fN ${ares_node}
```

## 2.2. Compute Node

For spack installs:
```
spack load hermes
spack unload python
jarvis pipeline create hermes_viz
jarvis pipeline append hemres_viz
```

For manual installs:
```
spack load hermes_shm
module load hermes_run
spack unload python
```

## 2.3. Personal Machine
```
local_port=4000
remote_port=4000
ares_node=llogan@ares.cs.iit.edu
ssh -L ${local_port}:localhost:${remote_port} -fN ${ares_node}

local_port=5001
remote_port=5001
ares_node=llogan@ares.cs.iit.edu
ssh -L ${local_port}:localhost:${remote_port} -fN ${ares_node}
```

Locate process spawned by ssh -L
```
lsof -i :5001
```
```

### `builtin/builtin/ior/README.md`

```markdown
LabStor is a distributed semi-microkernel for building data processing services.

# Installation

```bash
spack install ior mpi
```

# IOR

## 1. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 2. Create a Pipeline

The Jarvis pipeline will store all configuration data.
```bash
jarvis pipeline create ior
```

## 3. Load Environment

Create the environment variables
```bash
spack load ior mpi
```````````

## 4. Add pkgs to the Pipeline

Create a Jarvis pipeline
```bash
jarvis pipeline append ior
```

## 5. Run Experiment

Run the experiment
```bash
jarvis pipeline run
```

## 6. Clean Data

Clean produced data
```bash
jarvis pipeline clean
```
```

### `builtin/builtin/nyx_lya/README.md`

```markdown
Nyx is an adaptive mesh, massively-parallel, cosmological simulation code. 

# Installation

To compile the code we require C++11 compliant compilers that support MPI-2 or higher implementation. If threads or accelerators are used, we require OpenMP 4.5 or higher, Cuda 9 or higher, or HIP-Clang.

## 1. Install Dependencies


## 1. Install AMReX

```bash
git clone https://github.com/AMReX-Codes/amrex.git
pushd amrex
mkdir build
pushd build
cmake .. -DAMReX_HDF5=ON -DAMReX_PARTICLES=ON -DAMReX_PIC=ON -DBUILD_SHARED_LIBS=ON -DCMAKE_INSTALL_PREFIX=/path/to/amrex/install
make -j8
make install
popd
popd
```

## 2. Install Nyx

```bash
git clone https://github.com/AMReX-astro/Nyx.git
pushd Nyx
mkdir build
pushd build
cmake .. -DCMAKE_PREFIX_PATH=/path/to/amrex/install -DAMReX_DIR=/path/to/amrex/install/Tools/CMake/ -DNyx_SINGLE_PRECISION_PARTICLES=OFF -DNyx_OMP=OFF
make -j8
export NYX_PATH=`pwd`/Exec
popd
popd
```

# Nyx LyA

## 1. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 2. Create a Pipeline

The Jarvis pipeline will store all configuration data needed by Nyx LyA.

```bash
jarvis pipeline create nyx-lya-test
```

## 4. Add pkgs to the Pipeline

Create a Jarvis pipeline with Nyx LyA
```bash
jarvis pipeline append nyx_lya --nyx_install_path=$NYX_PATH --initial_z=190.0 --final_z=180.0 --plot_z_values="188.0 186.0" --output=/path/to/output_files
```
**nyx_install_path**: this argument is required, otherwise it will report an error.
You can use the default arguments for other arguments. But it may take a while.

## 5. Run Experiment

Run the experiment
```bash
jarvis pipeline run
```

## 6. Clean Data

Clean data produced by Nyx LyA
```bash
jarvis pipeline clean
```
```

### `builtin/builtin/orangefs/README.md`

```markdown
In this section we go over how to install and deploy OrangeFS.
NOTE: if running in Ares, OrangeFS is already installed, so skip
to section 5.3.

# Install Various Dependencies

```bash
sudo apt update
sudo apt install -y fuse
sudo apt install gcc flex bison libssl-dev libdb-dev linux-headers-$(uname -r) perl make libldap2-dev libattr1-dev
```

For fuse
```bash
sudo apt -y install fuse
spack install libfuse@2.9
```

NOTE: This package expects a working, passwordless SSH setup if you are using multiple nodes. On systems like Chameleon Cloud, you
must distribute the keys and set this up yourself before using jarvis. On single-node systems, SSH is not required.

# Install OrangeFS (Linux)

OrangeFS is located [on this website](http://www.orangefs.org/?gclid=CjwKCAjwgqejBhBAEiwAuWHioDo2uu8wel6WhiFqoBDgXMiVXc7nrykeE3sf3mIfDFVEt0_7SwRN8RoCdRYQAvD_BwE)
The official OrangeFS github is [here](https://github.com/waltligon/orangefs/releases/tag/v.2.9.8).

```bash
scspkg create orangefs
cd `scspkg pkg src orangefs`
wget https://github.com/waltligon/orangefs/releases/download/v.2.10.0/orangefs-2.10.0.tar.gz
tar -xvzf orangefs-2.10.0.tar.gz
cd orangefs
./prepare
./configure --prefix=`scspkg pkg root orangefs` --enable-shared --enable-fuse
make -j8
make install
scspkg env prepend orangefs ORANGEFS_PATH `scspkg pkg root orangefs`
```

# Using MPICH with OrangeFS

MPICH requires a special build when using OrangeFS. Apparantly it's for
performance, but it's a pain to have to go through the extra step.

```bash
scspkg create orangefs-mpich
cd `scspkg pkg src orangefs-mpich`
wget http://www.mpich.org/static/downloads/3.2/mpich-3.2.tar.gz --no-check-certificate
tar -xzf mpich-3.2.tar.gz
cd mpich-3.2
./configure --prefix=`scspkg pkg root orangefs-mpich` --enable-fast=O3 --enable-romio --enable-shared --with-pvfs2=`scspkg pkg root orangefs` --with-file-system=pvfs2
make -j8
make install
```

# Creating a pipeline

## Main Parmaeters
There are a few main parameters:
* ``ofs_data_dir``: The place where orangefs should store data or metadata. 
This needs to be a directory private to each node. For example, like /tmp or a burst buffer.
* ``mount``: Where the client should be mounted. This is where users will typically place data.
* ``ofs_mode``: The deployment method to use. Either fuse, kern, or ares.
* ``name``: The semantic name of the OrangeFS deployment. Typically just leave as default unless 
you have multiple deployments

## Performance Parameters
* ``stripe_size``: Size in bytes for stripes. Default 65536 (i.e., 64KB). 
* ``protocol``: Either tcp or ib. Only tcp has been tested.

## The Hostfile
OrangeFS can be picky about the hostfile. We recommend using only IP addresses
in your jarvis hostfile at this time when using OrangeFS.

An example hostfile for a single-node deployment is below:
```bash
echo '127.0.0.1' > ~/hostfile.txt
jarvis hostfile set ~/hostfile.txt
```

## libfuse
```bash
module load orangefs
jarvis pipeline create orangefs
jarvis pipeline env build +ORANGEFS_PATH
jarvis pipeline append orangefs \
mount=${HOME}/orangefs_client \
ofs_data_dir=${HOME}/ofs_data \
ofs_mode=fuse
```

## For kernel module
```bash
module load orangefs
jarvis pipeline create orangefs
jarvis pipeline env build +ORANGEFS_PATH
jarvis pipeline append orangefs \
mount=${HOME}/orangefs_client \
ofs_data_dir=/mnt/nvme/$USER/ofs_data \
ofs_mode=kern
```

## Ares Machine at IIT
```bash
module load orangefs
jarvis pipeline create orangefs
jarvis pipeline env build +ORANGEFS_PATH
jarvis pipeline append orangefs \
mount=${HOME}/orangefs_client \
ofs_data_dir=/mnt/nvme/$USER/ofs_data \
ofs_mode=ares
```
```

### `builtin/builtin/pyflextrkr/README.md`

```markdown
The Python FLEXible object TRacKeR (PyFLEXTRKR) is a flexible atmospheric feature tracking software package.
See the [official repo](https://github.com/FlexTRKR/PyFLEXTRKR) for more detail.

# Table of Content
0. [Dependencies](#0-dependencies)
1. [Installation](#1-installation)
2. [Running Pyflextrkr](#2-running-pyflextrkr)
3. [Pyflextrkr with Slurm](#3-pyflextrkr-with-slurm)
4. [Pyflextrkr + Hermes](#4-pyflextrkr--hermes)
5. [Pyflextrkr on Node Local Storage](#5-pyflextrkr-on-node-local-storage)
6. [Pyflextrkr + Hermes on Node Local Storage](#6-pyflextrkr--hermes-on-node-local-storage)
7. [Pyflextrkr + Hermes with Multinodes Slurm (TODO)](#7-pyflextrkr--hermes-on-multinodes-slurm-todo)



# 0. Dependencies

## 0.1. conda
- Prepare Conda
Get the miniconda3 installation script and run it
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh.sh
```

## 0.2. jarvis-cd & scspkg
Follow steps here: https://github.com/grc-iit/jarvis-cd


## 0.3. spack
Spack is used to install HDF5, MPICH, and Hermes.
Install spack steps are here: https://spack.readthedocs.io/en/latest/getting_started.html#installation

## 0.4. HDF5 (1.14.0+)
HDF5 is require, (1.14.0+) is required by Hermes and h5py==3.8.0.

Use spack to install hdf5
```bash
spack install hdf5@1.14.0+hl~mpi
```

## 0.5. MPI
Either OpenMPI or MPICH works, this is required by Hermes and mpi4py


Use spack to install mpich
```bash
spack install mpich@3.4.3
```

## 0.6. Installation Tools
You need `wget` to download the datasets online:
- wget
You can install wget either with `apt-get` or `spack`
```bash
sudo apt-get install wget
# or
spack install wget
spack load wget
# check if wget is usable
which wget
```



# 1. Installation

## 1.1 create pyflextrkr scs package
```bash
scspkg create pyflextrkr
cd `scspkg pkg src pyflextrkr`
git clone https://github.com/candiceT233/PyFLEXTRKR
cd PyFLEXTRKR
git switch ares # User the ares branch
scspkg env set pyflextrkr PYFLEXTRKR_PATH="`pwd`"
```


## 1.2 Prepare conda environment and python packages:
```bash
cd `scspkg pkg src pyflextrkr`/PyFLEXTRKR

YOUR_HDF5_DIR="`which h5cc |sed 's/.\{9\}$//'`"

conda env create -f ares_flextrkr.yml -n flextrkr
conda activate flextrkr
pip install -e .
HDF5_MPI="OFF" HDF5_DIR=${YOUR_HDF5_DIR} pip install --no-cache-dir --no-binary=h5py h5py==3.8.0
pip install xarray[io] mpi4py
conda deactivate
```



# 2. Running Pyflextrkr
Example is using `TEST_NAME=run_mcs_tbpfradar3d_wrf` (only supported with dataset download).
## 2.1. Setup Environment
Currently setup input path in a shared storage, below is a example on Ares cluster.
```bash
TEST_NAME=run_mcs_tbpfradar3d_wrf
EXPERIMENT_PATH=~/experiments/pyflex_run # NFS

export EXPERIMENT_INPUT_PATH=$EXPERIMENT_PATH/input_data # NFS
scspkg env set pyflextrkr EXPERIMENT_INPUT_PATH=$EXPERIMENT_INPUT_PATH
mkdir -p $EXPERIMENT_INPUT_PATH
```

## 2.2. Download Input Data
Setup example input data `wrf_tbradar.tar.gz` and path.to `run_mcs_tbpfradar3d_wrf.tar.gz`
```bash
cd $EXPERIMENT_INPUT_PATH
wget https://portal.nersc.gov/project/m1867/PyFLEXTRKR/sample_data/tb_radar/wrf_tbradar.tar.gz -O $TEST_NAME.tar.gz
mkdir $TEST_NAME
tar -xvzf $TEST_NAME.tar.gz -C $TEST_NAME

# Remove downloaded tar file
rm -rf $EXPERIMENT_INPUT_PATH/$TEST_NAME.tar.gz
```


## 2.3. Create a Resource Graph

If you haven't already, create a resource graph. This only needs to be done
once throughout the lifetime of Jarvis. No need to repeat if you have already
done this for a different pipeline.

For details building resource graph, please refer to https://github.com/grc-iit/jarvis-cd/wiki/2.-Resource-Graph.

If you are running distributed tests, set path to the hostfile you are  using.
```bash
jarvis hostfile set /path/to/hostfile
```

Next, collect the resources from each of those pkgs. Walkthrough will give
a command line tutorial on how to build the hostfile.
```bash
jarvis resource-graph build +walkthrough
```

## 2.4 Create a Pipeline

The Jarvis pipeline will store all configuration data needed by Pyflextrkr.

```bash
jarvis pipeline create pyflextrkr_test
```

## 2.5. Save Environment
Create the environment variables needed by Pyflextrkr.
```bash
spack load hdf5@1.14.0+hl~mpi mpich@3.4.3
module load pyflextrkr
```
<!-- conda activate flextrkr -->

Store the current environment in the pipeline.
```bash
jarvis env build pyflextr +PYFLEXTRKR_PATH +EXPERIMENT_INPUT_PATH
jarvis pipeline env copy pyflextr
```

## 2.6. Add pkgs to the Pipeline
** Currently only support running `runscript=run_mcs_tbpfradar3d_wrf` **

Create a Jarvis pipeline with Pyflextrkr.
```bash
jarvis pipeline append pyflextrkr runscript=run_mcs_tbpfradar3d_wrf
```


## 2.7. Run Experiment

Run the experiment, output are generated in `$EXPERIMENT_INPUT_PATH/output_data`.
```bash
jarvis pipeline run
```

## 2.8. Clean Data

Clean data produced by Pyflextrkr
```bash
jarvis pipeline clean
```



# 3. Pyflextrkr With Slurm

## 3.1 Local Cluster
Do the above and `ppn` must match `nprocesses`
```bash
jarvis pipeline sbatch job_name=pyflex_test nnodes=1 ppn=8 output_file=./pyflex_test.out error_file=./pyflex_test.err
```

## 3.2 Multi Nodes Cluster
Do the above and `ppn` must greater than match `nprocesses`/`nnodes` 
    (e.g. `nnodes=2 ppn=8` allocates 16 processes in total, and `nprocesses` must not greater than 16)

Configure Pyflextrkr to parallel run mode with MPI-Dask (0: serial, 1: Dask one-node cluster, 2: Dask multinode cluster)
```bash
jarvis pkg configure pyflextrkr run_parallel=2 nprocesses=8
```

```bash
jarvis pipeline sbatch job_name=pyflex_2ntest nnodes=2 ppn=4 output_file=./pyflex_2ntest.out error_file=./pyflex_2ntest.err
```



# 4. Pyflextrkr + Hermes

## 4.0. Dependencies
### 4.0.1 HDF5
Hermes must compile with HDF5, makesure [download HDF5-1.14.0 with spack](#4-hdf5-1140).

### 4.0.2 Install Hermes dependencies with spack
```bash
spack load hdf5@1.14.0+hl~mpi mpich@3.4.3
spack install hermes_shm ^hdf5@1.14.0+hl~mpi ^mpich@3.4.3
```

### 4.0.3 Install Hermes with scspkg
```bash
spack load hermes_shm
scspkg create hermes
cd `scspkg pkg src hermes`
git clone https://github.com/HDFGroup/hermes
cd hermes
mkdir build
cd build
cmake ../ -DCMAKE_BUILD_TYPE="Release" \
    -DCMAKE_INSTALL_PREFIX=`scspkg pkg root hermes` \
    -DHERMES_ENABLE_MPIIO_ADAPTER="ON" \
    -DHERMES_MPICH="ON" \
    -DHERMES_ENABLE_POSIX_ADAPTER="ON" \
    -DHERMES_ENABLE_STDIO_ADAPTER="ON" \
    -DHERMES_ENABLE_VFD="ON" \

```

## 4.1. Setup Environment

Create the environment variables needed by Hermes + Pyflextrkr
```bash
spack load hermes_shm
module load hermes pyflextrkr
```

## 4.2. Create a Resource Graph

Same as [above](#2-create-a-resource-graph).

## 4.3. Create a Pipeline

The Jarvis pipeline will store all configuration data needed by Hermes
and Pyflextrkr.

```bash
jarvis pipeline create hermes_pyflextrkr_test
```

## 4.4. Save Environment

Store the current environment in the pipeline.
```bash
jarvis pipeline env build +PYFLEXTRKR_PATH
```

## 4.5. Add pkgs to the Pipeline

Create a Jarvis pipeline with Hermes, the Hermes VFD interceptor,
and pyflextrkr (must use `flush_mode=sync` to prevent [this error](#oserror-log))
```bash
jarvis pipeline append hermes_run --sleep=10 include=$EXPERIMENT_PATH flush_mode=sync
jarvis pipeline append hermes_api +vfd
jarvis pipeline append pyflextrkr runscript=$TEST_NAME update_envar=true
```

## 4.6. Run the Experiment

Run the experiment, output are generated in `$EXPERIMENT_INPUT_PATH/output_data`.
```bash
jarvis pipeline run
```

## 4.7. Clean Data

To clean data produced by Hermes + Pyflextrkr:
```bash
jarvis pipeline clean
```



# 5. Pyflextrkr on Node Local Storage
For cluster that has node local storage, you can stagein data from shared storage, then run pyflextrkr.

## 5.1 Setup Environment
Currently setup DEFAULT input path in a shared storage, below is a example on Ares cluster using node local nvme.


The shared storage path is same as before:
```bash
export TEST_NAME=run_mcs_tbpfradar3d_wrf
EXPERIMENT_PATH=~/experiments/pyflex_run # NFS
EXPERIMENT_INPUT_PATH=$EXPERIMENT_PATH/input_data # NFS
mkdir -p $EXPERIMENT_INPUT_PATH
```
Setup the node local experiment paths:
```bash
LOCAL_EXPERIMENT_PATH=/mnt/nvme/$USER/pyflex_run
LOCAL_INPUT_PATH=$LOCAL_EXPERIMENT_PATH/input_data
```

## 5.2. Download Input Data
Same as [above](#22-download-input-data).

## 5.3. Create a Resource Graph
Same as [above](#23-create-a-resource-graph)

## 5.4. Create a Pipeline

The Jarvis pipeline will store all configuration data needed by Pyflextrkr.

```bash
jarvis pipeline create pyflextrkr_local
```

## 5.5. Save Environment
Create the environment variables needed by Pyflextrkr.
```bash
spack load hdf5@1.14.0+hl~mpi mpich@3.4.3
module load pyflextrkr
```


Store the current environment in the pipeline.
```bash
jarvis pipeline env build +PYFLEXTRKR_PATH
```

## 5.6. Add pkgs to the Pipeline
Add data_stagein to pipeline before pyflextrkr.
```bash 
jarvis pipeline append data_stagein dest_data_path=$LOCAL_INPUT_PATH \
user_data_paths=$EXPERIMENT_INPUT_PATH/$TEST_NAME \
mkdir_datapaths=$LOCAL_INPUT_PATH
```

Create a Jarvis pipeline with Pyflextrkr.
```bash
jarvis pipeline append pyflextrkr runscript=$TEST_NAME local_exp_dir=$LOCAL_INPUT_PATH
```

## 5.7. Run the Experiment

Run the experiment, output are generated in `$LOCAL_INPUT_PATH/output_data`.
```bash
jarvis pipeline run
```

## 5.8. Clean Data

To clean data produced by Hermes + Pyflextrkr:
```bash
jarvis pipeline clean
```



# 6. Pyflextrkr + Hermes on Node Local Storage
Every step the same as [Pyflextrkr + Hermes](#4-pyflextrkr--hermes), except for when creating a Jarvis pipeline with Hermes, using the Hermes VFD interceptor:
```bash
# Setup env
TEST_NAME=run_mcs_tbpfradar3d_wrf
EXPERIMENT_PATH=~/experiments/pyflex_run # NFS
INPUT_PATH=$EXPERIMENT_PATH/input_data # NFS
mkdir -p $EXPERIMENT_INPUT_PATH

LOCAL_EXPERIMENT_PATH=/mnt/nvme/$USER/pyflex_run
LOCAL_INPUT_PATH=$LOCAL_EXPERIMENT_PATH/input_data

# add pkg to pipeline
jarvis pipeline append data_stagein dest_data_path=$LOCAL_INPUT_PATH \
user_data_paths=$EXPERIMENT_INPUT_PATH/$TEST_NAME \
mkdir_datapaths=$LOCAL_INPUT_PATH

jarvis pipeline append hermes_run --sleep=10 include=$LOCAL_EXPERIMENT_PATH

jarvis pipeline append hermes_api +vfd

jarvis pipeline append pyflextrkr runscript=$TEST_NAME update_envar=true local_exp_dir=$LOCAL_INPUT_PATH
```



# 7. Pyflextrkr + Hermes on Multinodes Slurm (TODO)
Steps are the same as [Pyflextrkr with Slurm](#3-pyflextrkr-With-slurm), but not working yet due to OSError.

## OSError Log
```log
2024-01-03 18:49:03,523 - pyflextrkr.idfeature_driver - INFO - Identifying features from raw data
2024-01-03 18:49:04,969 - pyflextrkr.idfeature_driver - INFO - Total number of files to process: 17
free(): invalid size
2024-01-03 18:49:07,944 - distributed.worker - WARNING - Compute Failed
Key:       idclouds_tbpf-0bb7839d-ac6e-4e51-b309-ec2bc6667641
Function:  execute_task
args:      ((<function idclouds_tbpf at 0x7fce75d6da80>, '/home/mtang11/experiments/pyflex_runs/input_data/run_mcs_tbpfradar3d_wrf/wrfout_rainrate_tb_zh_mh_2015-05-06_04:00:00.nc', (<class 'dict'>, [['ReflThresh_lowlevel_gap', 20.0], ['abs_ConvThres_aml', 45.0], ['absolutetb_threshs', [160, 330]], ['area_thresh', 36], ['background_Box', 12.0], ['clouddata_path', '/home/mtang11/experiments/pyflex_runs/input_data/run_mcs_tbpfradar3d_wrf/'], ['clouddatasource', 'model'], ['cloudidmethod', 'label_grow'], ['cloudtb_cloud', 261.0], ['cloudtb_cold', 241.0], ['cloudtb_core', 225.0], ['cloudtb_warm', 261.0], ['col_peakedness_frac', 0.3], ['dask_tmp_dir', '/tmp/pyflextrkr_test'], ['databasename', 'wrfout_rainrate_tb_zh_mh_'], ['datatimeresolution', 1.0], ['dbz_lowlevel_asl', 2.0], ['dbz_thresh', 10], ['duration_range', [2, 300]], ['echotop_gap', 1], ['enddate', '20150506.1600'], ['etop25dBZ_Thresh', 10.0], ['feature_type', 'tb_pf_radar3d'], ['feature_varname', 'feature_number'], ['featuresize_varname',
kwargs:    {}
Exception: "OSError('Unable to synchronously open file (file signature not found)')"

Traceback (most recent call last):
  File "/mnt/common/mtang11/scripts/scspkg/packages/pyflextrkr/src/PyFLEXTRKR/runscripts/run_mcs_tbpfradar3d_wrf.py", line 115, in <module>
    idfeature_driver(config)
  File "/mnt/common/mtang11/scripts/scspkg/packages/pyflextrkr/src/PyFLEXTRKR/pyflextrkr/idfeature_driver.py", line 66, in idfeature_driver
    final_result = dask.compute(*results)
                   ^^^^^^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/dask/base.py", line 595, in compute
    results = schedule(dsk, keys, **kwargs)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/distributed/client.py", line 3243, in get
    results = self.gather(packed, asynchronous=asynchronous, direct=direct)
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/distributed/client.py", line 2368, in gather
    return self.sync(
           ^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/distributed/utils.py", line 351, in sync
    return sync(
           ^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/distributed/utils.py", line 418, in sync
    raise exc.with_traceback(tb)
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/distributed/utils.py", line 391, in f
    result = yield future
             ^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/tornado/gen.py", line 767, in run
    value = future.result()
            ^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/distributed/client.py", line 2231, in _gather
    raise exception.with_traceback(traceback)
  File "/mnt/common/mtang11/scripts/scspkg/packages/pyflextrkr/src/PyFLEXTRKR/pyflextrkr/idclouds_tbpf.py", line 98, in idclouds_tbpf
    rawdata = xr.open_dataset(filename, engine='h5netcdf') # , engine='h5netcdf' netcdf4 h5netcdf
      ^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/xarray/backends/api.py", line 566, in open_dataset
    backend_ds = backend.open_dataset(
      ^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/xarray/backends/h5netcdf_.py", line 413, in open_dataset
    store = H5NetCDFStore.open(
  ^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/xarray/backends/h5netcdf_.py", line 176, in open
    return cls(manager, group=group, mode=mode, lock=lock, autoclose=autoclose)
  ^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/xarray/backends/h5netcdf_.py", line 127, in __init__
    self._filename = find_root_and_group(self.ds)[0].filename
  ^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/xarray/backends/h5netcdf_.py", line 187, in ds
    return self._acquire()
  ^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/xarray/backends/h5netcdf_.py", line 179, in _acquire
    with self._manager.acquire_context(needs_lock) as root:
  ^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/contextlib.py", line 137, in __enter__
    return next(self.gen)
^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/xarray/backends/file_manager.py", line 198, in acquire_context
    file, cached = self._acquire_with_cache_info(needs_lock)
  ^^^^^^^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/xarray/backends/file_manager.py", line 216, in _acquire_with_cache_info
    file = self._opener(*self._args, **kwargs)
^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/h5netcdf/core.py", line 1051, in __init__
    self._h5file = self._h5py.File(
^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/h5py/_hl/files.py", line 567, in __init__
    fid = make_fid(name, mode, userblock_size, fapl, fcpl, swmr=swmr)
^^^^^^^^^^^
  File "/home/mtang11/miniconda3/envs/flextrkr/lib/python3.11/site-packages/h5py/_hl/files.py", line 231, in make_fid
    fid = h5f.open(name, flags, fapl=fapl)
  ^^^^^^^^^^^^^^^^^
  File "h5py/_objects.pyx", line 54, in h5py._objects.with_phil.wrapper
  File "h5py/_objects.pyx", line 55, in h5py._objects.with_phil.wrapper
  File "h5py/h5f.pyx", line 106, in h5py.h5f.open
OSError: Unable to synchronously open file (file signature not found)
```
```

### `builtin/builtin/pymonitor/README.md`

```markdown

```

### `builtin/builtin/redis-benchmark/README.md`

```markdown
LabStor is a distributed semi-microkernel for building data processing services.

# Installation

```bash
spack install redis
```
```

### `builtin/builtin/redis/README.md`

```markdown
Redis is a key-value store

# Installation

```bash
spack install redis
```
```

### `builtin/builtin/spark_cluster/README.md`

```markdown
# Installation

Manual build:
```
spack install openjdk@11
spack load openjdk@11
scspkg create spark
cd `scspkg pkg src spark`
wget https://dlcdn.apache.org/spark/spark-3.5.1/spark-3.5.1.tgz
tar -xzf spark-3.5.1.tgz
cd spark-3.5.1
./build/mvn -T 16 -DskipTests clean package
scspkg env set spark SPARK_SCRIPTS=${PWD}
scspkg env prepend spark PATH "${PWD}/bin"
module load spark
```
NOTE: this took 30min in Ares.

With spack (doesn't seem to work, sorry):
```
spack install spark
spack load spark
scspkg create spark-env
scspkg env set spark-env SPARK_SCRIPTS=`spack find --format "{PREFIX}" spark`
module load spark-env
```

Additional configuration documentation 
[here](https://spark.apache.org/docs/latest/spark-standalone.html).

# Create the Jarvis pipeline

```
jarvis pipeline create spark
```

# Build the Jarvis environment

```
jarvis pipeline env build +SPARK_SCRIPTS
```

# Append the Spark Cluster Pkg

```
jarvis pipeline append spark_cluster
```

# Run the pipeline

```
jarvis pipeline run
```
```

### `builtin/builtin/ycsbc/README.md`

```markdown
Redis is a key-value store

# Installation

```bash
spack install redis
```
```

### `.gitignore`

```
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class
.idea
/config
jarvis_repos
jarvis_envs
.jarvis_env
hostfile.txt

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
MIT License

Copyright (c) 2020 scs-lab

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### `builtin/builtin/orangefs/Dockerfile`

```dockerfile
FROM iowarp/iowarp-deps:latest

# Set non-interactive frontend to avoid prompts
ENV DEBIAN_FRONTEND=noninteractive

# Set timezone to avoid prompt during package installation
ENV TZ=Etc/UTC

# Update package lists
RUN apt-get update && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Reset frontend
ENV DEBIAN_FRONTEND=dialog

# SCSPKG + lmod
RUN echo $'\n\
if ! shopt -q login_shell; then\n\
    if [ -d /etc/profile.d ]; then\n\
        for i in /etc/profile.d/*.sh; do\n\
            if [ -r $i ]; then\n\
                . $i\n\
            fi\n\
        done\n\
    fi\n\
fi\n\
' >> /root/.bashrc
RUN . "${SPACK_DIR}/share/spack/setup-env.sh" && \
    spack load iowarp && \
    echo "module use $(scspkg module dir)" >> /root/.bashrc && \
    scspkg init tcl

# Install OFS dependencies
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y automake bison flex \
    libdb-dev \
    libsqlite3-dev libfuse-dev fuse

# Install libfuse
RUN . "${SPACK_DIR}/share/spack/setup-env.sh" && \
    spack install libfuse@2.9

# Install OFS
RUN . "${SPACK_DIR}/share/spack/setup-env.sh" && \
    spack load iowarp libfuse && \
    scspkg create orangefs && \
    cd $(scspkg pkg src orangefs) && \
    wget https://github.com/waltligon/orangefs/releases/download/v.2.10.0/orangefs-2.10.0.tar.gz && \
    tar -xvzf orangefs-2.10.0.tar.gz && \
    cd orangefs && \
    ./prepare && \
    ./configure --prefix=$(scspkg pkg root orangefs) --enable-shared --enable-fuse && \
    make -j8 && \
    make install && \
    scspkg env prepend orangefs ORANGEFS_PATH $(scspkg pkg root orangefs)

# Install OFS with openmpi
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
  pkg1:
    build: .
    links:
      - pkg2
    networks:
      - net
    hostname: pkg1
    stdin_open: true
    tty: true

  pkg2:
    build: .
    networks:
      - net
    hostname: pkg2
    stdin_open: true
    tty: true

networks:
  net:
    driver: bridge
```

### `docs/Makefile`

```makefile
# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line, and also
# from the environment for the first two.
SPHINXOPTS    ?=
SPHINXBUILD   ?= sphinx-build
SOURCEDIR     = source
BUILDDIR      = build

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: help Makefile

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
```

### `pyproject.toml`

```toml
[project]
name = "jarvis_cd"
description = "IOWarp Platform Plugins Interface"
readme = "README.md"
requires-python = ">=3.7"
dynamic = ["version"]
authors = [
  {name = "H. Joe Lee", email = "hyoklee@hdfgroup.org"},
]
classifiers = [
  "Operating System :: OS Independent",
  "Intended Audience :: Science/Research",
  "Programming Language :: Python",
  "Topic :: Scientific/Engineering",
  "Development Status :: 3 - Alpha",
  "Topic :: Scientific/Engineering",
]
dependencies = [
  "pyyaml",
  "pandas",
]

[project.urls]
Documentation = "https://iowarp.github.io/"
issue-tracker = "https://github.com/iowarp/platform-plugins-interface/issues"
source-code = "https://github.com/iowarp/platform-plugins-interface"

[build-system]
build-backend = "setuptools.build_meta"
requires = [
  "setuptools>=42",
  "setuptools-scm>=7",
]

[tool.setuptools]
packages = ["jarvis_cd", "jarvis_cd.basic", "jarvis_cd.template"]
include-package-data = true
```

### `requirements.txt`

```
pyyaml
pandas
jarvis-util @ git+https://github.com/scs-lab/jarvis-util.git#egg=jarvis-util
#pylint==2.15.0
#coverage==5.5
#coverage-lcov==0.2.4
#pytest==6.2.5
```

### `setup.py`

```python
import setuptools
import os
import sys 
import shutil
import sysconfig
from pathlib import Path


ret = setuptools.setup(
    name="jarvis_cd",
    packages=setuptools.find_packages(),
    scripts=['bin/jarvis'],
    version="0.0.1",
    author="Luke Logan",
    author_email="llogan@hawk.iit.edu",
    description="Create basic for applications",
    long_description=open('README.md').read(),
    long_description_content_type='text/markdown',
    url="https://github.com/scs-lab/jarvis-cd",
    classifiers = [
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
    install_requires=[
        'pandas',
        'pyyaml'
    ]
)

# Install the builtin directory to ~/.jarvis
project_dir = os.path.dirname(os.path.realpath(__file__))
local_builtin_path = os.path.join(project_dir, 'builtin')
install_builtin_path = os.path.join(Path.home(), '.jarvis', 'builtin')  
if not os.path.exists(os.path.dirname(install_builtin_path)):
    os.makedirs(os.path.dirname(install_builtin_path))
shutil.copytree(local_builtin_path, install_builtin_path, dirs_exist_ok=True)
```

### `.github/workflows/main.yml`

```yaml
name: main

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

      - name: Install Apt Dependencies
        run: bash ci/install_deps.sh

      - name: Install Jarvis
        run: bash ci/install_jarvis.sh

      - name: Run pylint
        run: bash ci/lint.sh

      - name: Test
        run: bash ci/run_tests.sh

#      - name: Coveralls
#        uses: coverallsapp/github-action@master
#        with:
#          path-to-lcov: lcov.info
#          github-token: ${{ secrets.GITHUB_TOKEN }}
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
                "ppl",
                "append",
                "chimaera_run"
            ],
            "console": "integratedTerminal",
            "justMyCode": false,
            "env": {
                "PATH": "/home/llogan/.scspkg/packages/iowarp_runtime/sbin:/home/llogan/.scspkg/packages/iowarp_runtime/bin:/usr/local/cuda/bin:/usr/local/cuda/gds/tools:/home/llogan/Documents/Projects/scspkg/packages/cuda/sbin:/home/llogan/Documents/Projects/scspkg/packages/cuda/bin:/opt/rocm/bin:/home/llogan/Documents/Projects/scspkg/packages/rocm/sbin:/home/llogan/Documents/Projects/scspkg/packages/rocm/bin:/home/llogan/.venv/bin:/home/llogan/.local/bin:/mnt/home/Projects/spack/bin:/home/llogan/.vscode-server/cli/servers/Stable-848b80aeb52026648a8ff9f7c45a9b0a80641e2e/server/bin/remote-cli:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/llogan/.vscode-server/extensions/ms-python.debugpy-2025.8.0-linux-x64/bundled/scripts/noConfigScripts:/home/llogan/.vscode-server/data/User/globalStorage/github.copilot-chat/debugCommand"
            }
        }
    ]
}
```

### `build.sh`

```bash
#!/bin/bash
pip install .
```

### `builtin/__init__.py`

```python

```

### `builtin/builtin/__init__.py`

```python

```

### `builtin/builtin/arldm/example_config/config.yml`

```yaml
batch_size: 1
calculate_fid: true
ckpt_dir: /mnt/nvme/mtang11/arldm_run/save_ckpt
dataset: vistsis
flintstones:
  blip_embedding_tokens: 30525
  clip_embedding_tokens: 49412
  hdf5_file: FLINTSTONES_HDF5
  max_length: 91
  new_tokens:
  - fred
  - barney
  - wilma
  - betty
  - pebbles
  - dino
  - slate
freeze_blip: true
freeze_clip: true
freeze_resnet: true
gpu_ids: []
guidance_scale: 6
hydra:
  output_subdir: null
  run:
    dir: .
hydra/hydra_logging: disabled
hydra/job_logging: disabled
init_lr: 1e-5
max_epochs: 50
mode: train
num_cpu_cores: -1
num_inference_steps: 250
num_workers: 1
pororo:
  blip_embedding_tokens: 30530
  clip_embedding_tokens: 49416
  hdf5_file: PORORO_HDF5
  max_length: 85
  new_tokens:
  - pororo
  - loopy
  - eddy
  - harry
  - poby
  - tongtong
  - crong
  - rody
  - petty
run_name: vistsis_train
sample_output_dir: /mnt/nvme/mtang11/arldm_run/output_data/sample_out_vistsis_train
scheduler: ddim
seed: 0
task: continuation
test_model_file: null
train_model_file: null
vistdii:
  blip_embedding_tokens: 30524
  clip_embedding_tokens: 49408
  hdf5_file: VISTDII_HDF5
  max_length: 65
vistsis:
  blip_embedding_tokens: 30524
  clip_embedding_tokens: 49408
  hdf5_file: /mnt/nvme/mtang11/arldm_run/output_data/vistsis_out.h5
  max_length: 100
warmup_epochs: 1
```

### `builtin/builtin/arldm/example_config/config_template.yml`

```yaml
# device
mode: MODE  # train sample
gpu_ids: []  # gpu ids, 4 GPU uses [ 0, 1, 2, 3 ]
batch_size: 1  # batch size each item denotes one story
num_workers: WORKERS  # number of workers
num_cpu_cores: -1  # -1 number of cpu cores
seed: 0  # random seed
ckpt_dir: CKPT_DIR # checkpoint directory
run_name: TEST_NAME # name for this run

# task
dataset: DATASET  # pororo flintstones vistsis vistdii
task: continuation  # continuation visualization

# train
init_lr: 1e-5  # initial learning rate
warmup_epochs: 1  # warmup epochs
max_epochs: 50  # max epochs
train_model_file:  # model file for resume, none for train from scratch
freeze_clip: True  # whether to freeze clip, True to reduce vram usage
freeze_blip: True  # whether to freeze blip, True to reduce vram usage
freeze_resnet: True  # whether to freeze resnet, True to reduce vram usage

# sample
test_model_file:  # model file for test
calculate_fid: True  # whether to calculate FID scores
scheduler: ddim  # ddim pndm
guidance_scale: 6  # guidance scale
num_inference_steps: 250  # number of inference steps
# sample_output_dir: ./output_data/train_visit # output directory
sample_output_dir: SAMPLE_OUT_DIR # output directory

pororo:
  hdf5_file: PORORO_HDF5
  max_length: 85
  new_tokens: [ "pororo", "loopy", "eddy", "harry", "poby", "tongtong", "crong", "rody", "petty" ]
  clip_embedding_tokens: 49416
  blip_embedding_tokens: 30530

flintstones:
  hdf5_file: FLINTSTONES_HDF5
  max_length: 91
  new_tokens: [ "fred", "barney", "wilma", "betty", "pebbles", "dino", "slate" ]
  clip_embedding_tokens: 49412
  blip_embedding_tokens: 30525

vistsis:
  hdf5_file: VISTSIS_HDF5
  max_length: 100
  clip_embedding_tokens: 49408
  blip_embedding_tokens: 30524

vistdii:
  hdf5_file: VISTDII_HDF5
  max_length: 65
  clip_embedding_tokens: 49408
  blip_embedding_tokens: 30524

hydra:
  run:
    dir: .
  output_subdir: null
hydra/job_logging: disabled
hydra/hydra_logging: disabled
```

### `builtin/builtin/arldm/pkg.py`

```python
"""
This module provides classes and methods to launch the Arldm application.
Arldm is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *
import os, pathlib
import time
import yaml
from scspkg.pkg import Package
import sys # for stdout, stderr

class Arldm(Application):
    """
    This class provides methods to launch the Arldm application.
    """
    def _init(self):
        """
        Initialize paths
        """
        self.pkg_type = 'arldm'
        self.hermes_env_vars = ['HERMES_ADAPTER_MODE', 'HERMES_CLIENT_CONF', 
                                'HERMES_CONF', 'LD_PRELOAD']
        # self.hermes_env_vars = ['HDF5_DRIVER', 'HDF5_PLUGIN_PATH', 
        #                   'HERMES_ADAPTER_MODE', 'HERMES_CLIENT_CONF',
        #                   'HERMES_CONF', 'HERMES_VFD', 'HERMES_POSIX'
        #                   ]
        
    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'conda_env',
                'msg': 'Name of the conda environment for running ARLDM',
                'type': str,
                'default': "arldm",
            },
            {
                'name': 'config',
                'msg': 'The config file for running analysis',
                'type': str,
                'default': f'{self.pkg_dir}/example_config/config_template.yml',
            },
            {
                'name': 'update_envar_yml',
                'msg': 'Update the conda environment variables',
                'type': str,
                'default': f'{self.pkg_dir}/example_config/update_envar.yml',
            },
            {
                'name': 'with_hermes',
                'msg': 'Whether it is used with Hermes (e.g. needs to update environment variables)',
                'type': bool,
                'default': False,
            },
            {
                'name': 'with_dayu',
                'msg': 'Whether it is used with DaYu (e.g. needs to update task files)',
                'type': bool,
                'default': False,
            },
            {
                'name': 'runscript',
                'msg': 'The name of the ARLDM script to run',
                'type': str,
                'default': 'vistsis', # smallest dataset
                'choices': ['flintstones', 'pororo', 'vistsis', 'vistdii'],
            },
            {
                'name': 'flush_mem',
                'msg': 'Flushing the memory after each stage',
                'type': bool,
                'default': False,
            },
            {
                'name': 'flush_mem_cmd',
                'msg': 'Command to flush the node memory',
                'type': str,
                'default': "ml user-scripts; sudo drop_caches", # for Ares
            },
            {
                'name': 'arldm_path',
                'msg': 'Absolute path to the ARLDM source code (can set to `scspkg pkg src arldm`/ARLDM)',
                'type': str,
                'default': f"{Package(self.pkg_type).pkg_root}/src/ARLDM",
            },
            {
                'name': 'mode',
                'msg': 'Mode of running ARLDM: train(D) or sample',
                'type': str,
                'default': 'train',
                'choice': ['train', 'sample'],
            },
            {
                'name': 'num_workers',
                'msg': 'Number of CPU workers to use for parallel processing',
                'type': int,
                'default': 1,
                'choices': [0, 1, 2],
            },
            {
                'name': 'experiment_input_path',
                'msg': 'Absolute path to the experiment where you put all data',
                'type': str,
                'default': None,
            },
            {
                'name': 'sample_output_dir',
                'msg': 'Directory to save samples',
                'type': str,
                'default': None, 
            },
            {
                'name': 'hdf5_file',
                'msg': 'HDF5 file to save samples',
                'type': str,
                'default': None,
            },
            {
                'name': 'prep_hdf5',
                'msg': 'Prepare the HDF5 file for the ARLDM run',
                'type': bool,
                'default': True,
            },
            {
                'name': 'local_exp_dir',
                'msg': 'Local experiment directory',
                'type': str,
                'default': None,
            },
            {
                'name': 'pretrain_model_path',
                'msg': 'Pretrained model path',
                'type': str,
                'default': None,
            },
        ]

    def _configure_yaml(self):
        yaml_file = self.config['config']

        if "_template.yml" not in str(yaml_file):
            yaml_file = yaml_file.replace(".yml", "_template.yml")
        
        self.log(f"ARLDM template.yml: {yaml_file}")

        with open(yaml_file, "r") as stream:
            try:
                config_vars = yaml.safe_load(stream)
                
                run_test = self.config['runscript']
                
                config_vars['mode'] = self.config['mode']
                config_vars['num_workers'] = self.config['num_workers']
                config_vars['run_name'] = f"{self.config['runscript']}_{self.config['mode']}"
                config_vars['dataset'] = run_test

                experiment_input_path = self.config['experiment_input_path']
                if self.config['local_exp_dir'] is not None:
                    experiment_input_path = self.config['local_exp_dir']
                    self.config['ckpt_dir'] = experiment_input_path + f"/{self.config['runscript']}_save_ckpt"
                    self.config['sample_output_dir'] = experiment_input_path + f"/sample_out_{self.config['runscript']}_{self.config['mode']}"
                    self.config['hdf5_file'] = f"{experiment_input_path}/{self.config['runscript']}_out.h5"

                config_vars['ckpt_dir'] = self.config['ckpt_dir']
                config_vars['sample_output_dir'] = self.config['sample_output_dir']
                config_vars[run_test]['hdf5_file'] = self.config['hdf5_file']
                
                # save config_vars back to yaml file
                new_yaml_file = yaml_file.replace("_template.yml", ".yml")
                yaml.dump(config_vars, open(new_yaml_file, 'w'), default_flow_style=False)
            except yaml.YAMLError as exc:
                self.log(exc)
        self.config['config'] = new_yaml_file
        

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        # self.env['HDF5_USE_FILE_LOCKING'] = "FALSE" 
        # self.env['HYDRA_FULL_ERROR'] = "1" # complete stack trace.
        
        self.log(f"ARLDM _configure")
        
        self.setenv('HDF5_USE_FILE_LOCKING', "FALSE") # set HDF5 locking: FALSE, TRUE, BESTEFFORT
        self.setenv('HYDRA_FULL_ERROR', "1")
        
        if self.config['pretrain_model_path'] is None:
            pretrain_model_path = os.getenv('PRETRAIN_MODEL_PATH')
            if pretrain_model_path is not None:
                if self.config['local_exp_dir'] is not None:
                    pretrain_model_path = self.config['local_exp_dir'] + "/model_large.pth"
                self.log(f"PRETRAIN_MODEL_PATH: {pretrain_model_path}")
                self.config['pretrain_model_path'] = pretrain_model_path
                # self.env['PRETRAIN_MODEL_PATH'] = pretrain_model_path
                self.setenv('PRETRAIN_MODEL_PATH', pretrain_model_path)
            else:
                raise Exception("Must set the pretrain_model_path")
        else:
            if self.config['local_exp_dir'] is None:
                pretrain_model_path = os.getenv('PRETRAIN_MODEL_PATH')
                if pretrain_model_path is not None:
                    self.log(f"PRETRAIN_MODEL_PATH: {pretrain_model_path}")
                    self.config['pretrain_model_path'] = pretrain_model_path
                    # self.env['PRETRAIN_MODEL_PATH'] = pretrain_model_path
                    self.setenv('PRETRAIN_MODEL_PATH', pretrain_model_path)
        
        experiment_input_path = os.getenv('EXPERIMENT_INPUT_PATH')
        if experiment_input_path is None:
            raise Exception("Must set the experiment_input_path")
        else:
            self.config['experiment_input_path'] = experiment_input_path
        
        if self.config['conda_env'] is None:
            raise Exception("Must set the conda environment for running ARLDM")
        if self.config['config'] is None:
            raise Exception("Must set the ARLDM config file")
        if self.config['runscript'] is None:
            raise Exception("Must set the ARLDM script to run")
            
        if self.config['flush_mem'] == False:
            self.env['FLUSH_MEM'] = "FALSE"
        else:
            if self.config['flush_mem_cmd'] is None:
                raise Exception("Must add the command to flush memory using flush_mem_cmd")
        
        if self.config['arldm_path'] is None:
            raise Exception("Must set the `'arldm_path'` to the ARLDM source code")
        else:
            # check that path exists
            if not pathlib.Path(self.config['arldm_path']).exists():
                raise Exception(f"`'arldm_path'` does not exist: {self.config['arldm_path']}")
        
        # check and make -p experiment_input_path
        pathlib.Path(self.config['experiment_input_path']).mkdir(parents=True, exist_ok=True)
        
        # set ckpt_dir
        self.config['ckpt_dir'] = f'{self.config["experiment_input_path"]}/{self.config["runscript"]}_save_ckpt'
        pathlib.Path(self.config['ckpt_dir']).mkdir(parents=True, exist_ok=True)
        
        # set sample_output_dir
        self.config['sample_output_dir'] = f'{self.config["experiment_input_path"]}/sample_out_{self.config["runscript"]}_{self.config["mode"]}'
        pathlib.Path(self.config['sample_output_dir']).mkdir(parents=True, exist_ok=True)
        
        # set sample_output_dir
        self.config['hdf5_file'] = f'{self.config["experiment_input_path"]}/{self.config["runscript"]}_out.h5'
                
        self._configure_yaml()
        

    def _prep_hdf5_file(self):
        """
        Prepare the HDF5 file for the ARLDM run
        """
        if self.config['with_dayu'] == True:
            self._set_curr_task_file("arldm_saveh5")
        
        self.log(f"ARLDM _prep_hdf5_file input from to {self.config['hdf5_file']}")
        
        experiment_input_path = self.config['experiment_input_path']
        if self.config['local_exp_dir'] is not None:
            experiment_input_path = self.config['local_exp_dir']
        
        cmd = [
            # f"cd {self.config['arldm_path']}; echo Executing from directory `pwd`;",
            'conda','run', '-n', self.config['conda_env'], # conda environment
            'python',
        ]

        if self.config['runscript'] == 'pororo':
            cmd.append(f'{self.config["arldm_path"]}/data_script/pororo_hdf5.py')
            cmd.append(f'--data_dir {experiment_input_path}/pororo')
            cmd.append(f'--save_path {self.config["hdf5_file"]}')
        elif self.config['runscript'] == 'flintstones':
            cmd.append(f'{self.config["arldm_path"]}/data_script/flintstones_hdf5.py')
            cmd.append(f'--data_dir {experiment_input_path}/flintstones')
            cmd.append(f'--save_path {self.config["hdf5_file"]}')
        elif self.config['runscript'] == 'vistsis' or self.config['runscript'] == 'vistdii':
            cmd.append(f'{self.config["arldm_path"]}/data_script/vist_hdf5.py')
            # experiment_input_path = f'{experiment_input_path}/{self.config["runscript"]}'
            cmd.append(f'--sis_json_dir {experiment_input_path}/vistsis')
            cmd.append(f'--dii_json_dir {experiment_input_path}/vistdii')
            cmd.append(f'--img_dir {experiment_input_path}/visit_img')
            cmd.append(f'--save_path {self.config["hdf5_file"]}')
        else:
            raise Exception("Must set the correct ARLDM script to run")
        
        prep_cmd = ' '.join(cmd)
        
        start = time.time()
        Exec(prep_cmd, LocalExecInfo(
            env=self.mod_env,
            cwd=self.config['arldm_path']))
        
        end = time.time()
        diff = end - start
        self.log(f'TIME: {diff} seconds') # color=Color.GREEN
        
        # check if hdf5_file exists
        if pathlib.Path(self.config['hdf5_file']).exists():
           self.log(f"HDF5 file created: {self.config['hdf5_file']}")
        else:
            raise Exception(f"HDF5 file not created: {self.config['hdf5_file']}") 
    
    def _train(self):
        """
        Run the ARLDM training run
        """
        if self.config['with_dayu'] == True:
            self._set_curr_task_file("arldm_train")
        
        self.log(f"ARLDM _train: dataset[{self.config['runscript']}]")
        
        # Move config file to arldm_path
        Exec(f"cp {self.config['config']} {self.config['arldm_path']}/config.yaml",
             LocalExecInfo(env=self.mod_env,))
        
        
        cmd = [
            'conda','run', '-n', self.config['conda_env'], # conda environment
            'python'
        ]

        if self.config['arldm_path'] and self.config['runscript']:
            cmd.append(f'{self.config["arldm_path"]}/main.py')
        
        conda_cmd = ' '.join(cmd)
        
        start = time.time()

        self.jutil.debug_local_exec = True
        Exec(conda_cmd,
             LocalExecInfo(env=self.mod_env,
                           do_dbg=self.config['do_dbg'],
                           dbg_port=self.config['dbg_port'],
                           pipe_stdout=self.config['stdout'],
                           pipe_stderr=self.config['stderr'],
                           cwd=self.config['arldm_path']))
        self.jutil.debug_local_exec = False
        
        end = time.time()
        diff = end - start
        self.log(f'TIME: {diff} seconds') # color=Color.GREEN
    
    def _sample(self):
        """
        Run the ARLDM sampling run
        
        This step can only be run when training is fully completed. 
        Currently train is set to fast_dev_run.
        """
        self.log(f"ARLDM sampling run: not implemented yet")

    def _set_curr_task_file(self,task):
        
        workflow_name = self.mod_env['WORKFLOW_NAME']
        path_for_task_files = self.mod_env['PATH_FOR_TASK_FILES']
        vfd_task_file = None
        vol_task_file = None
        
        if workflow_name and path_for_task_files:
            vfd_task_file = os.path.join(path_for_task_files, f"{workflow_name}_vfd.curr_task")
            vol_task_file = os.path.join(path_for_task_files, f"{workflow_name}_vol.curr_task")
            # Create file and parent file if it does not exist
            pathlib.Path(vfd_task_file).mkdir(parents=True, exist_ok=True)
            pathlib.Path(vol_task_file).mkdir(parents=True, exist_ok=True)
            

        # vfd_task_file = /tmp/$USER/pyflextrkr_vfd.curr_task
        
        if vfd_task_file and os.path.exists(vfd_task_file):
            if os.path.isfile(vfd_task_file):
                with open(vfd_task_file, "w") as file:
                    file.write(task)
                print(f"Overwrote: {vfd_task_file} with {task}")

        if vol_task_file and os.path.exists(vol_task_file):
            if os.path.isfile(vol_task_file):
                with open(vol_task_file, "w") as file:
                    file.write(task)
                print(f"Overwrote: {vol_task_file} with {task}")
        else:
            print("Invalid or missing PATH_FOR_TASK_FILES environment variable.")    

    def _unset_vfd_vars(self,env_vars_toset):
        cmd = ['conda', 'env', 'config', 'vars', 'unset',]
        
        for env_var in env_vars_toset:
            cmd.append(f'{env_var}')
        cmd.append('-n')
        cmd.append(self.config['conda_env'])
        
        cmd = ' '.join(cmd)
        Exec(cmd, LocalExecInfo(env=self.mod_env,))
        self.log(f"ARLDM _unset_vfd_vars: {cmd}")

    def _set_env_vars(self, env_vars_toset):
        
        self.log(f"ARLDM _set_env_vars")
        
        # Unset all env_vars_toset first        
        self._unset_vfd_vars(env_vars_toset)

        cmd = [ 'conda', 'env', 'config', 'vars', 'set']
        for env_var in env_vars_toset:
            env_var_val = self.mod_env[env_var]
            cmd.append(f'{env_var}={env_var_val}')
        
        cmd.append('-n')
        cmd.append(self.config['conda_env'])
        cmd = ' '.join(cmd)
        self.log(f"ARLDM _set_env_vars: {cmd}")
        Exec(cmd, LocalExecInfo(env=self.mod_env,))

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        
        self._configure_yaml()
        
        if self.config['with_hermes'] == True:
            self._set_env_vars(self.hermes_env_vars)
        else:
            self._unset_vfd_vars(self.hermes_env_vars)
        
        
        self.log(f"ARLDM start")
        
        start = time.time()
        
        if self.config['prep_hdf5']:
            self._prep_hdf5_file()
        
        if self.config['mode'] == 'train':
            self._train()
        
        if self.config['mode'] == 'sample':
            self._sample()
        
        end = time.time()
        diff = end - start
        self.log(f'TOTAL RUN TIME: {diff} seconds')


    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        output_h5 = self.config['experiment_input_path'] + f"/{self.config['runscript']}_out.h5"
        output_dir = self.config['experiment_input_path'] + f"/sample_out_{self.config['runscript']}_{self.config['mode']}"
        if self.config['local_exp_dir'] is not None:
            output_dir = self.config['local_exp_dir'] + f"/sample_out_{self.config['runscript']}_{self.config['mode']}"
        
        # recursive remove all files in output_data directory
        if os.path.exists(output_dir):
            self.log(f'Removing {output_dir}')
            Rm(output_dir)
        else:
            self.log(f'No directory to remove: {output_dir}')
        
        if os.path.exists(output_h5):     
            self.log(f'Removing {output_h5}')
            Rm(output_h5)
        else:
            self.log(f'No file to remove: {output_h5}')
        
        ## Clear cache manually
        # # Clear cache
        # self.log(f'Clearing cache')
        # Exec(self.config['flush_mem_cmd'], LocalExecInfo(env=self.mod_env,))
```

### `builtin/builtin/asan/pkg.py`

```python
"""
This module provides classes and methods to inject the Asan interceptor.
Asan is a library to detect memory errors.
"""
from jarvis_cd.basic.pkg import Interceptor
from jarvis_util import *


class Asan(Interceptor):
    """
    This class provides methods to inject the Asan interceptor.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return []

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        self.config['LIBASAN'] = self.find_library('asan')
        if self.config['LIBASAN'] is None:
            raise Exception('Could not find libasan')
        print(f'Found libasan.so at {self.config["LIBASAN"]}')

    def modify_env(self):
        """
        Modify the jarvis environment.

        :return: None
        """
        self.prepend_env('LD_PRELOAD', self.config['LIBASAN'])
```

### `builtin/builtin/cm1/pkg.py`

```python
"""
This module provides classes and methods to launch the Cm1 application.
Cm1 is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class Cm1(Application):
    """
    This class provides methods to launch the Cm1 application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'nx',
                'msg': 'x dimension of 3-D grid',
                'type': int,
                'default': 16,
            },
            {
                'name': 'ny',
                'msg': 'y dimension of 3-D grid',
                'type': int,
                'default': 16,
            },
            {
                'name': 'nz',
                'msg': 'z dimension of 3-D grid',
                'type': int,
                'default': 16,
            },
            {
                'name': 'corex',
                'msg': 'Number of cores for x dimension',
                'type': int,
                'default': 2,
            },
            {
                'name': 'corey',
                'msg': 'Number of cores for x dimension',
                'type': int,
                'default': 2,
            },
            {
                'name': 'file_type',
                'msg': 'The file type to use',
                'type': str,
                'choices': ['grads', 'netcdf', 'lofs'],
                'default': 'netcdf',
            },
            {
                'name': 'file_count',
                'msg': 'The number of files to generate',
                'type': str,
                'choices': ['shared', 'fpo', 'fpp', 'lofs'],
                'default': 'shared',
            },
            {
                'name': 'TEST_CASE',
                'msg': 'The test to run',
                'type': str,
                'choices': ['nssl3'],
                'default': None,
            },
            {
                'name': 'ppn',
                'msg': 'The number of processes per node',
                'type': int,
                'default': 1,
            },
            {
                'name': 'output',
                'msg': 'The directory to output data to',
                'type': str,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        # Create output directories
        if self.config['output'] is None:
            self.config['output'] = f'{self.shared_dir}/cm1_out'
        out_parent = str(pathlib.Path(self.config['output']).parent)
        self.config['restart'] = os.path.join(out_parent, 'restart_dir')
        Mkdir([self.config['output'], self.config['restart']],
              LocalExecInfo())

        # Create CM1 compilation
        self.config['CM1_PATH'] = self.env['CM1_PATH']
        Exec(f'bash {self.config["CM1_PATH"]}/buildCM1-spack.sh',
             LocalExecInfo(env=self.env))

        # Create CM1 configuration
        self.env['COREX'] = self.config['corex']
        self.env['COREY'] = self.config['corey']
        corex = self.config['corex']
        corey = self.config['corey']
        namelist_in = os.path.join(self.pkg_dir, 'config',
                                   'namelist.input.nssl3')
        namelist_out = os.path.join(self.shared_dir, 'namelist.input.nssl3')
        if self.config['file_format'] == 'grads':
            file_format = 1
        elif self.config['file_format'] == 'netcdf':
            file_format = 2
        elif self.config['file_format'] == 'lofs':
            file_format = 5
        else:
            raise Exception("Invalid file format")

        if self.config['file_count'] == 'shared':
            file_count = 1
        elif self.config['file_count'] == 'fpo':
            file_count = 2
        elif self.config['file_count'] == 'fpp':
            file_count = 3
        elif self.config['file_count'] == 'lofs':
            file_count = 4
        else:
            raise Exception("Invalid file count")

        self.copy_template_file(namelist_in, namelist_out, replacements=[
            ('file_format', file_format),
            ('file_count', file_count),
            ('nx', self.config['nx']),
            ('ny', self.config['ny']),
            ('nz', self.config['nz']),
            ('nodex', corex),
            ('nodey', corey),
            ('rankx', corex),
            ('ranky', corey),
            ('ppn', self.config['ppn']),
        ])

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        cmd = [
            f'{self.config["CM1_PATH"]}/run/cm1.exe',
            self.config['namelist'],
            self.config['output'],
            'cm1_data',
            self.config['restart']
        ]
        cmd = ' '.join(cmd)
        corex = self.config['corex']
        corey = self.config['corey']
        Exec(cmd, MpiExecInfo(env=self.env,
                              nprocs=corex * corey,
                              ppn=self.config['ppn'],
                              hostfile=self.jarvis.hostfile))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/cosmic_tagger/config/config.yaml`

```yaml
defaults:
  - base_config
  - _self_
data:
  aux_file: ##TEST_FILE##
  data_directory: ##DATASET_DIR##
  data_format: channels_last
  downsample: 1
  file: ##TRAIN_FILE##
  synthetic: False
framework: 
  inter_op_parallelism_threads: 2
  intra_op_parallelism_threads: 24
  name: tensorflow
mode:
  checkpoint_iteration: 500
  logging_iteration: 1
  name: train
  no_summary_images: False
  optimizer:
    gradient_accumulation: 1
    learning_rate: 0.0003
    loss_balance_scheme: focal
    name: adam
  summary_iteration: 1
  # weights_location:
network: 
  batch_norm: True
  bias: True
  block_concat: False
  blocks_deepest_layer: 5
  blocks_final: 5
  blocks_per_layer: 2
  bottleneck_deepest: 256
  connections: concat
  conv_mode: conv_2D
  data_format: channels_last
  downsampling: max_pooling
  filter_size_deepest: 5
  growth_rate: additive
  n_initial_filters: 16
  name: uresnet
  network_depth: 6
  residual: True
  upsampling: interpolation
  weight_decay: 0.0
output_dir: output/tensorflow/uresnet/test/
run: 
  aux_iterations: 10
  compute_mode: CPU
  distributed: False
  id: test
  iterations: 500
  minibatch_size: 2
  precision: float32
  profile: False
```

### `builtin/builtin/cosmic_tagger/config/default.yaml`

```yaml
defaults:
  - base_config
  - _self_

# output_dir: output/${framework.name}/${network.name}/${run.id}/
```

### `builtin/builtin/cosmic_tagger/pkg.py`

```python
"""
This module provides classes and methods to launch the DataStagein application.
DataStagein is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *
import os
import pathlib
import time


class CosmicTagger(Application):
    """
    This class provides methods to launch the DataStagein application.
    """
    def _init(self):
        pass
        

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'train_file',
                'msg': 'Train filename (not abspath)',
                'type': str,
                'default': 'cosmic_tagging_light.h5',
            },
            {
                'name': 'test_file',
                'msg': 'Test filename (not abspath)',
                'type': str,
                'default': 'cosmic_tagging_test.h5',
            },
            {
                'name': 'dataset_dir',
                'msg': 'Dataset directory (abspath)',
                'type': str,
                'default': '/home/llogan/Documents/Apps/CosmicTagger/example_data/',
            },
        ]
            
    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        src_path = f'{self.pkg_dir}/config/config.yaml'
        dst_path = f'{self.env["TAGGER_ROOT"]}/src/config/config.yaml'
        self.copy_template_file(src_path, dst_path, replacements= {
            'TRAIN_FILE': self.config['train_file'],
            'TEST_FILE': self.config['test_file'],
            'DATASET_DIR': self.config['dataset_dir'],
        })
        self.log(dst_path, Color.YELLOW)
    
    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        # Exec('conda ')

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/darshan/pkg.py`

```python
"""
This module provides classes and methods to inject the Darshan interceptor.
Darshan is ....
"""
from jarvis_cd.basic.pkg import Interceptor
from jarvis_util import *
import os


class Darshan(Interceptor):
    """
    This class provides methods to inject the Darshan interceptor.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'log_dir',
                'msg': 'Where darshan should place data',
                'type': str,
                'default': f'{os.getenv("HOME")}/darshan_logs',
            },
            {
                'name': 'job_id',
                'msg': 'A semantic ID for the job to identify log files',
                'type': str,
                'default': 'myjob',
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        self.env['DARSHAN_LOG_DIR'] = self.config['log_dir']
        self.env['PBS_JOBID'] = self.config['job_id']
        self.config['DARSHAN_LIB'] = self.find_library('darshan')
        if self.config['DARSHAN_LIB'] is None:
            raise Exception('Could not find darshan')
        Mkdir(self.env['DARSHAN_LOG_DIR'],
              PsshExecInfo(hostfile=self.jarvis.hostfile))
        print(f'Found libdarshan.so at {self.config["DARSHAN_LIB"]}')

    def modify_env(self):
        """
        Modify the jarvis environment.

        :return: None
        """
        self.append_env('LD_PRELOAD', self.config['DARSHAN_LIB'])
```

### `builtin/builtin/data_stagein/pkg.py`

```python
"""
This module provides classes and methods to launch the DataStagein application.
DataStagein is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *
import os
import pathlib
import time


class DataStagein(Application):
    """
    This class provides methods to launch the DataStagein application.
    """
    def _init(self):
        """
        Initialize paths
        """
        
        # Convert user_data_paths to list
        try:
            user_data_paths = self.config['user_data_paths']
            if user_data_paths is not None:
                self.user_data_list = user_data_paths.split(',')
        except KeyError:
            self.user_data_list = []
        
        try:
            # Convert mkdir_datapaths to list
            mkdir_datapaths = self.config['mkdir_datapaths']
            if mkdir_datapaths is not None:
                self.mkdir_datapaths_list = mkdir_datapaths.split(',')
        except KeyError:
            self.mkdir_datapaths_list = []
        

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'user_data_paths',
                'msg': 'List of paths of user datas to stage in, delimitated by comma',
                'type': str,
                'default': None,
            },
            {
                'name': 'dest_data_path',
                'msg': 'The destination path for all user datas to be staged in',
                'type': str,
                'default': None,
            },
            {
                'name': 'mkdir_datapaths',
                'msg': 'List of paths tp create if it does not exist, delimitated by comma',
                'type': str,
                'default': None,
            },
        ]
    
    def _print_required_params(self):
        required_params = ['dest_data_path', 'user_data_paths', 'mkdir_datapaths']
        print("data_stagein Required parameters: ")
        for param in required_params:
            print(f"    {param}")
            
    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        # Convert user_data_paths to list
        try:
            user_data_paths = self.config['user_data_paths']
            if user_data_paths is not None:
                self.user_data_list = user_data_paths.split(',')
        except KeyError:
            self.user_data_list = []
        
        try:
            # Convert mkdir_datapaths to list
            mkdir_datapaths = self.config['mkdir_datapaths']
            if mkdir_datapaths is not None:
                self.mkdir_datapaths_list = mkdir_datapaths.split(',')
        except KeyError:
            self.mkdir_datapaths_list = []

        self.log(f"user_data_list: {self.user_data_list}")
        self.log(f"mkdir_datapaths_list: {self.mkdir_datapaths_list}")
        
        if self.config['dest_data_path'] is None:
            self._print_required_params()
            raise ValueError("dest_data_path is not set")
        if self.config['user_data_paths'] is None:
            self._print_required_params()
            raise ValueError("user_data_paths is not set")
        if self.config['mkdir_datapaths'] is None:
            self._print_required_params()
            raise ValueError("mkdir_datapaths is not set")
        
        self.config['dest_data_path'] = self.config['dest_data_path']
    
    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        print("Data stagein starting")
        
        user_data_list = self.user_data_list
        dest_data_path = self.config['dest_data_path']
        mkdir_datapaths_list = self.mkdir_datapaths_list
        
        print(f"dest_data_path: {dest_data_path}")
        print(f"user_data_list: {user_data_list}")
        print(f"mkdir_datapaths_list: {mkdir_datapaths_list}")
        
        
        # create paths for user
        for datapath in mkdir_datapaths_list:
            if not pathlib.Path(datapath).exists():
                pathlib.Path(datapath).mkdir(parents=True, exist_ok=True)
            else:
                print(f"Path {datapath} already exists")
        
        # create destination path if it does not exist
        if not pathlib.Path(dest_data_path).exists():
            pathlib.Path(dest_data_path).mkdir(parents=True, exist_ok=True)
        
        start = time.time()
        
        for data_path in user_data_list:
            if not os.path.exists(data_path):
                raise FileNotFoundError(f"Data path {data_path} does not exist")
            else:
                # check if data_path is a directory
                if os.path.isdir(data_path):
                    # Check if the path is empty (e.g. does not contain any files)
                    if len(os.listdir(data_path)) == 0:
                        raise ValueError(f"Data path {data_path} is empty")
                else:
                    # Check if the file is not empty
                    if os.stat(data_path).st_size == 0:
                        raise ValueError(f"Data file {data_path} is empty")
            
            # Check if two directory contains the same files
            dest_files = os.listdir(dest_data_path)
            if os.path.isdir(data_path) and set(dest_files) == set(os.listdir(data_path)):
                # data_files = os.listdir(data_path)
                # if set(dest_files) == set(data_files):
                print(f"Data path {data_path} already exists in {dest_data_path}")
                continue
            
            # Move data to destination path
            cmd = f"cp -r {data_path} {dest_data_path}"
            print(f"Copying data from {data_path} to {dest_data_path}")
            Exec(cmd,LocalExecInfo(env=self.mod_env,))
            
            copied_items = 1
            if os.path.isdir(data_path): copied_items = len(os.listdir(data_path))
            print(f"Copied {copied_items} items ... ")
        
        end = time.time()
        diff = end - start
        self.log(f'data_stagein TIME: {diff} seconds')
            
        print("Data stagein complete")

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/ddmd/pkg.py`

```python
"""
This module provides classes and methods to launch the Ddmd application.
Ddmd is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *
import os
import yaml
import time
import pathlib, glob, shutil

class Ddmd(Application):
    """
    This class provides methods to launch the Ddmd application.
    """
    def _init(self):
        """
        Initialize paths
        """
        self.openmm_list = []
        self.aggregate = None
        self.train = None
        self.prev_model_json = None
        self.inference = None
        self.hermes_env_vars = ['HERMES_ADAPTER_MODE', 'HERMES_CLIENT_CONF', 'HERMES_CONF', 'LD_PRELOAD']

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'conda_openmm',
                'msg': 'Name of the conda environment for running OpenMM',
                'type': str,
                'default': None,
            },
            {
                'name': 'conda_pytorch',
                'msg': 'Name of the conda environment for running PyTorch',
                'type': str,
                'default': None,
            },
            {
                'name': 'ddmd_path',
                'msg': 'Path to the DDMD source code',
                'type': str,
                'default': None, # `scspkg pkg src ddmd`deepdrivemd/
            },
            {
                'name': 'experiment_path',
                'msg': 'Absolute path to the experiment run input and output files',
                'type': str,
                'default': '${HOME}/experiments/ddmd_test',
            },
            {
                'name': 'local_exp_dir',
                'msg': 'Local experiment directory',
                'type': str,
                'default': None,
            },
            {
                'name': 'molecules_path',
                'msg': 'Absolute path to the molecules submodule directory',
                'type': str,
                'default': None,
            },
            {
                'name': 'md_runs',
                'msg': 'Number of MD runs to perform',
                'type': int,
                'default': 12,
            },
            {
                'name': 'iter_count',
                'msg': 'Number of iterations to perform',
                'type': int,
                'default': 1,
            },
            {
                'name': 'sim_len',
                'msg': 'Length of simulation size (e.g., 0.1. 1)',
                'type': float,
                'default': 0.1,
            },
            {
                'name': 'nnodes',
                'msg': 'Number of nodes to use',
                'type': int,
                'default': 1,
            },
            {
                'name': 'gpu_per_node',
                'msg': 'Number of GPUs per node',
                'type': int,
                'default': 1,
            },
            {
                'name': 'md_start',
                'msg': 'Starting MD run',
                'type': int,
                'default': 0,
            },
            {
                'name': 'md_slide',
                'msg': 'Number of MD runs to slide',
                'type': int,
                'default': 0, # $MD_RUNS/$NODE_COUNT
            },
            {
                'name': 'stage_idx',
                'msg': 'Stage index (starting at 0)',
                'type': int,
                'default': 0, # Usually don't change this
            },
            {
                'name': 'skip_sim',
                'msg': 'Skip the simulation stage',
                'type': bool,
                'default': False,
            },
            {
                'name': 'short_pipe',
                'msg': 'Use a shorted pipeline',
                'type': bool,
                'default': False,
            },
            {
                'name': 'with_hermes',
                'msg': 'Whether it is used with Hermes (e.g. needs to update environment variables)',
                'type': bool,
                'default': False,
            },
            
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        
        if self.config['conda_openmm'] is None:
            # check if CONDA_OPENMM is set in the environment
            if os.environ.get('CONDA_OPENMM') is not None:
                self.config['conda_openmm'] = os.environ.get('CONDA_OPENMM') 
                self.env['CONDA_OPENMM'] = os.environ.get('CONDA_OPENMM')
            else:
                raise Exception('No conda_openmm environment specified')
            
        if self.config['conda_pytorch'] is None:
            if os.environ.get('CONDA_PYTORCH') is not None:
                self.config['conda_pytorch'] = os.environ.get('CONDA_PYTORCH')
                self.env['CONDA_PYTORCH'] = self.config['conda_pytorch']
            else:
                raise Exception('No conda_pytorch environment specified')
        
        if self.config['ddmd_path'] is None:
            if os.environ.get('DDMD_PATH') is not None:
                self.config['ddmd_path'] = os.environ.get('DDMD_PATH')
                self.env['DDMD_PATH'] = self.config['ddmd_path']
                self.config['molecules_path'] = self.config['ddmd_path'] + '/submodules/molecules'
                self.env['MOLECULES_PATH'] = self.config['molecules_path']
            else:
                raise Exception('No ddmd_path specified')
        else:
            self.env['DDMD_PATH'] = self.config['ddmd_path']
            self.config['molecules_path'] = self.config['ddmd_path'] + '/submodules/molecules'
            self.env['MOLECULES_PATH'] = self.config['molecules_path']
        
        if self.config['experiment_path'] is not None:
            self.config['experiment_path'] = os.path.expandvars(self.config['experiment_path'])
            self.env['EXPERIMENT_PATH'] = self.config['experiment_path']
            pathlib.Path(self.config['experiment_path']).mkdir(parents=True, exist_ok=True)
            
        if self.config['experiment_path'] is None:
            raise Exception('No experiment_path specified')
        
        if self.config['md_runs'] < 12:
            raise Exception('md_runs must be at least 12')
        
        if self.config['iter_count'] < 1:
            raise Exception('iter_count must be at least 1')
        
        if self.config['sim_len'] < 0.1:
            raise Exception('sim_len must be at least 0.1')
        
        if self.config['nnodes'] < 1:
            raise Exception('nnodes must be at least 1')
        
        self.config['md_slide'] = self.config['md_runs'] / self.config['nnodes']
    
    def _run_openmm(self):
        """
        Run the OpenMM simulation. This method is called by the run method.

        :return: None
        """
        
        all_tasks = []
        
        for task in range(self.config['md_start'], self.config['md_runs']):
        
            task_idx = "task" + str(task).zfill(4)
            stage_idx = "stage" + str(self.config['stage_idx']).zfill(4)
            gpu_idx = 0 # dummy now
            stage_name="molecular_dynamics"
            
            node_idx = len(self.jarvis.hostfile) % self.config['nnodes']
            node_name = self.jarvis.hostfile[node_idx]
            
            yaml_path = self.config['ddmd_path'] + "/test/bba/" + stage_name + "_stage_test.yaml"
            dest_path= self.config['experiment_path'] + "/" + stage_name + "_runs/" + stage_idx + "/" + task_idx
            
            # create the dest_path
            pathlib.Path(dest_path).mkdir(parents=True, exist_ok=True)
            
            # load yaml file to change the parameters
            with open(yaml_path, 'r') as f:
                config_vars = yaml.load(f, Loader=yaml.FullLoader)
                # sed -e "s/\$SIM_LENGTH/${SIM_LENGTH}/" -e "s/\$OUTPUT_PATH/${dest_path//\//\\/}/" -e "s/\$EXPERIMENT_PATH/${EXPERIMENT_PATH//\//\\/}/" -e "s/\$DDMD_PATH/${DDMD_PATH//\//\\/}/" -e "s/\$GPU_IDX/${gpu_idx}/" -e "s/\$STAGE_IDX/${STAGE_IDX}/" $yaml_path  > $dest_path/$(basename $yaml_path)
                config_vars['output_path'] = dest_path
                config_vars['experiment_directory'] = self.config['experiment_path']
                config_vars['initial_pdb_dir'] = self.config['ddmd_path'] + "/data/bba"
                config_vars['pdb_file'] = self.config['ddmd_path'] + "/data/bba/system/1FME-unfolded.pdb"
                config_vars['ddmd_path'] = self.config['ddmd_path']
                config_vars['reference_pdb_file'] = self.config['ddmd_path'] + "/data/bba/1FME-folded.pdb"
                
                config_vars['simulation_length_ns'] = self.config['sim_len']
                config_vars['gpu_idx'] = gpu_idx
                config_vars['stage_idx'] = self.config['stage_idx']
                config_vars['task_idx'] = task
                
                new_yaml_file = dest_path + "/" + stage_name + "_stage_test.yaml"
                yaml.dump(config_vars, open(new_yaml_file, 'w'), default_flow_style=False)
            
            logfile = dest_path + "/" + task_idx + "_OPENMM.log"
            
            cmd = [
                f'cd {dest_path};',
                'conda','run', '-n', self.config['conda_openmm'],
                'mpirun',
                '--host', node_name,
                '-np', str(1),
                '-env',
                f'PYTHONPATH={self.config["ddmd_path"]}:{self.config["molecules_path"]}',
                'python',
                f'{self.config["ddmd_path"]}/deepdrivemd/sim/openmm/run_openmm.py',
                '-c', new_yaml_file,
            ]
            
            conda_cmd = ' '.join(cmd)
            print(F"Running OpenMM on {node_name}: {dest_path}")
            print(f"{conda_cmd} > {logfile}")
            cur_task = Exec(conda_cmd, LocalExecInfo(env=self.mod_env,
                                          pipe_stdout=logfile,
                                          exec_async=True))
            
            all_tasks.append(cur_task)
        
        return all_tasks
        
    
    
    def _run_aggregate(self):
        """
        Aggregate the results of the OpenMM simulation.
        
        :return: None
        """
        task_idx = "task0000" # fix to 0
        stage_name="aggregate"
        
        stage_idx = "stage" + str((self.config['stage_idx'])).zfill(4)
        node_idx = 0 # TODO: allow specify nodes?
        node_name = self.jarvis.hostfile[node_idx]
        yaml_path = self.config['ddmd_path'] + "/test/bba/" + stage_name + "_stage_test.yaml"
        dest_path= self.config['experiment_path'] + "/" + stage_name + "_runs/" + stage_idx + "/" + task_idx
        # create the dest_path
        pathlib.Path(dest_path).mkdir(parents=True, exist_ok=True)
        
        # load yaml file to change the parameters
        with open(yaml_path, 'r') as f:
            config_vars = yaml.load(f, Loader=yaml.FullLoader)
            # sed -e "s/\$SIM_LENGTH/${SIM_LENGTH}/" -e "s/\$OUTPUT_PATH/${dest_path//\//\\/}/" -e "s/\$EXPERIMENT_PATH/${EXPERIMENT_PATH//\//\\/}/" -e "s/\$DDMD_PATH/${DDMD_PATH//\//\\/}/" -e "s/\$GPU_IDX/${gpu_idx}/" -e "s/\$STAGE_IDX/${STAGE_IDX}/" $yaml_path  > $dest_path/$(basename $yaml_path)
            config_vars['experiment_directory'] = self.config['experiment_path']
            config_vars['stage_idx'] = self.config['stage_idx']
            config_vars['task_idx'] = 0 # fix to 0
            config_vars['output_path'] = dest_path + "/aggregated.h5"
            config_vars['pdb_file'] = self.config['ddmd_path'] + "/data/bba/system/1FME-unfolded.pdb"
            config_vars['reference_pdb_file'] = self.config['ddmd_path'] + "/data/bba/1FME-folded.pdb"
            config_vars['simulation_length_ns'] = self.config['sim_len']
            
            
            new_yaml_file = dest_path + "/" + stage_name + "_stage_test.yaml"
            yaml.dump(config_vars, open(new_yaml_file, 'w'), default_flow_style=False)
            
            logfile = dest_path + "/" + task_idx + "_AGGREGATE.log"
            
            cmd = [
                f'cd {dest_path};',
                'conda','run', '-n', self.config['conda_openmm'],
                'mpirun',
                '--host', node_name,
                '-np', str(1),
                '-env',
                f'PYTHONPATH={self.config["ddmd_path"]}',
                'python',
                f'{self.config["ddmd_path"]}/deepdrivemd/aggregation/basic/aggregate.py',
                '-c', new_yaml_file,
            ]
            
            conda_cmd = ' '.join(cmd)
            print(F"Running Aggregate on {node_name}: {dest_path}")
            print(f"{conda_cmd} > {logfile}")
            Exec(conda_cmd, LocalExecInfo(env=self.mod_env,
                                        pipe_stdout=logfile))
    
    
    def _run_train(self):
        """
        Train the model.
        
        :return: None
        """
        task_idx = "task0000" # fix to 0
        
        stage_idx = "stage" + str((self.config['stage_idx'])).zfill(4)
        model_tag = stage_idx + "_" + task_idx
        node_idx = 0 # TODO: allow specify nodes?
        node_name = self.jarvis.hostfile[node_idx]
        dest_path= self.config['experiment_path'] + "/" + "machine_learning" + "_runs/" + stage_idx + "/" + task_idx
        stage_name="machine_learning" # "machine_learning" : faster, "training" : slower
        yaml_path = self.config['ddmd_path'] + "/test/bba/" + stage_name + "_stage_test.yaml"
        # create the dest_path
        pathlib.Path(dest_path).mkdir(parents=True, exist_ok=True)
        
        model_select_path = self.config['experiment_path'] + "/model_selection_runs/" + stage_idx + "/" + task_idx
        pathlib.Path(model_select_path).mkdir(parents=True, exist_ok=True)
        
        cp_cmd = [
            'cp','-p',
            f'{self.config["ddmd_path"]}/test/bba/stage0000_task0000.json',
            f'{model_select_path}/{model_tag}.json',
        ]
        cp_cmd = ' '.join(cp_cmd)
        print(f"Copying {model_tag}.json to {model_select_path}")
        Exec(cp_cmd, LocalExecInfo(env=self.mod_env))
        
        self.prev_model_json = f'{model_select_path}/{model_tag}.json'
        
        try:
            # load yaml file to change the parameters
            with open(yaml_path, 'r') as f:
                config_vars = yaml.load(f, Loader=yaml.FullLoader)
                # sed -e "s/\$SIM_LENGTH/${SIM_LENGTH}/" -e "s/\$OUTPUT_PATH/${dest_path//\//\\/}/" -e "s/\$EXPERIMENT_PATH/${EXPERIMENT_PATH//\//\\/}/" -e "s/\$DDMD_PATH/${DDMD_PATH//\//\\/}/" -e "s/\$GPU_IDX/${gpu_idx}/" -e "s/\$STAGE_IDX/${STAGE_IDX}/" $yaml_path  > $dest_path/$(basename $yaml_path)
                config_vars['experiment_directory'] = self.config['experiment_path']
                config_vars['stage_idx'] = self.config['stage_idx']
                config_vars['task_idx'] = 0 # fix to 0
                config_vars['output_path'] = dest_path
                config_vars['model_tag'] = model_tag
                config_vars['init_weights_path'] = "none"
                
                new_yaml_file = dest_path + "/" + stage_name + "_stage_test.yaml"
                yaml.dump(config_vars, open(new_yaml_file, 'w'), default_flow_style=False)
                
                logfile = dest_path + "/" + task_idx + "_TRAIN.log"
                
                cmd = [
                    f'cd {dest_path};',
                    'conda','run', '-n', self.config['conda_pytorch'],
                    'mpirun',
                    '--host', node_name,
                    '-np', str(1),
                    '-env',
                    f'PYTHONPATH={self.config["ddmd_path"]}:{self.config["molecules_path"]}',
                    'python',
                    f'{self.config["ddmd_path"]}/deepdrivemd/models/aae/train.py',
                    '-c', new_yaml_file,
                ]
                
                conda_cmd = ' '.join(cmd)
                print(F"Running Training on {node_name}: {dest_path}")
                print(f"{conda_cmd} > {logfile}")
                curr_task = Exec(conda_cmd, LocalExecInfo(env=self.mod_env,
                                            pipe_stdout=logfile,
                                            exec_async=True))
                return curr_task
        except Exception as e:
            print("ERROR: " + str(e))
            print("ERROR: Training failed")
            return None
    
    def _run_inference(self):
        """
        Run inference on the model.
        
        :return: None
        """
        task_idx = "task0000" # fix to 0
        
        stage_idx = "stage" + str((self.config['stage_idx'])).zfill(4)
        model_tag = stage_idx + "_" + task_idx
        node_idx = 0 
        if len(self.jarvis.hostfile) > 1:
            node_idx = 1 # TODO: allow specify nodes?
        node_name = self.jarvis.hostfile[node_idx]
        stage_name="inference" 
        dest_path= self.config['experiment_path'] + f"/{stage_name}_runs/" + stage_idx + "/" + task_idx
        yaml_path = self.config['ddmd_path'] + "/test/bba/" + stage_name + "_stage_test.yaml"
        # create the dest_path
        pathlib.Path(dest_path).mkdir(parents=True, exist_ok=True)
        
        agent_run_path = self.config['experiment_path'] + "/agent_runs/" + stage_idx + "/" + task_idx
        pathlib.Path(agent_run_path).mkdir(parents=True, exist_ok=True)
        
        pretrained_model = self.config['ddmd_path'] + "/data/bba/epoch-130-20201203-150026.pt"
        
        checkpoint_path_pattern = os.path.join(self.config['experiment_path'], "machine_learning_runs", "*", "*", "checkpoint")
        # Find all matching checkpoint directories
        matching_checkpoint_dirs = glob.glob(checkpoint_path_pattern)
        if matching_checkpoint_dirs:
            # Construct the complete file path pattern for checkpoint files
            checkpoint_pattern = os.path.join(matching_checkpoint_dirs[0], '*.pt')
            # Find all matching checkpoint files
            checkpoint_files = glob.glob(checkpoint_pattern)
            # Check if there are any .pt files in the matching checkpoint directory
            if checkpoint_files:

                # Sort files by epoch and timestamp and get the latest checkpoint
                # latest_checkpoint = max(checkpoint_files, key=os.path.getmtime) # getctime, this does not get epoch 10
                latest_checkpoint = max(checkpoint_files, key=lambda x: (int(x.split('-')[1]), int(x.split('-')[2]), int(x.split('-')[3].split('.')[0])))
                print(f"Latest checkpoint: {latest_checkpoint}")
                
            else:
                latest_checkpoint = pretrained_model
        else:
            print(f"Using pretrained model: {pretrained_model}")
            latest_checkpoint = pretrained_model
        
        prev_stage_idx = "stage" + str((self.config['stage_idx']-1)).zfill(4)
        # replace $MODEL_CHECKPOINT with latest_checkpoint in the json file
        with open(self.prev_model_json, 'r') as f:
            json_str = f.read()
            json_str = json_str.replace("$MODEL_CHECKPOINT", latest_checkpoint)

        # save the updated json content back to the file
        with open(self.prev_model_json, 'w') as f:
            f.write(json_str)

        try:
            # load yaml file to change the parameters
            with open(yaml_path, 'r') as f:
                config_vars = yaml.load(f, Loader=yaml.FullLoader)
                # sed -e "s/\$SIM_LENGTH/${SIM_LENGTH}/" -e "s/\$OUTPUT_PATH/${dest_path//\//\\/}/" -e "s/\$EXPERIMENT_PATH/${EXPERIMENT_PATH//\//\\/}/" -e "s/\$DDMD_PATH/${DDMD_PATH//\//\\/}/" -e "s/\$GPU_IDX/${gpu_idx}/" -e "s/\$STAGE_IDX/${STAGE_IDX}/" $yaml_path  > $dest_path/$(basename $yaml_path)
                config_vars['experiment_directory'] = self.config['experiment_path']
                config_vars['stage_idx'] = self.config['stage_idx']
                config_vars['task_idx'] = 0 # fix to 0
                config_vars['output_path'] = dest_path
                
                new_yaml_file = dest_path + "/" + stage_name + "_stage_test.yaml"
                yaml.dump(config_vars, open(new_yaml_file, 'w'), default_flow_style=False)
                
                logfile = dest_path + "/" + task_idx + "_INFERENCE.log"
                
                cmd = [
                    f'cd {dest_path};',
                    'conda','run', '-n', self.config['conda_pytorch'],
                    'mpirun',
                    '--host', node_name,
                    '-np', str(1),
                    '-env',
                    'OMP_NUM_THREADS=4',
                    '-env',
                    f'PYTHONPATH={self.config["ddmd_path"]}:{self.config["molecules_path"]}',
                    'python',
                    f'{self.config["ddmd_path"]}/deepdrivemd/agents/lof/lof.py',
                    '-c', new_yaml_file,
                ]
                
                conda_cmd = ' '.join(cmd)
                print(F"Running Inference on {node_name}: {dest_path}")
                print(f"{conda_cmd} > {logfile}")
                curr_task = Exec(conda_cmd, LocalExecInfo(env=self.mod_env,
                                            pipe_stdout=logfile))
                return curr_task
        except Exception as e:
            print("ERROR: " + str(e))
            print("ERROR: Inference failed")
            return None
    
    def _check_openmm(self):
        """
        Check if all the OpenMM files exist
        """
        for task in range(self.config['md_start'], self.config['md_runs']):
        
            task_idx = "task" + str(task).zfill(4)
            stage_idx = "stage" + str(self.config['stage_idx']).zfill(4)
            stage_name="molecular_dynamics"
            dest_path= self.config['experiment_path'] + "/" + stage_name + "_runs/" + stage_idx + "/" + task_idx
            
            # Check if "*.h5" and "*.pdb" files exist and not size 0
            h5_path_pattern = os.path.join(dest_path, '*.h5')
            matching_h5_files = glob.glob(h5_path_pattern)
            pdb_path_pattern = os.path.join(dest_path, '*.pdb')
            matching_pdb_files = glob.glob(pdb_path_pattern)
            if matching_h5_files and matching_pdb_files:
                continue
            else:
                return False
        return True

    def _unset_vfd_vars(self,env_vars_toset):
        
        conda_envs = [self.config['conda_openmm'], self.config['conda_pytorch']]
        
        for cenv in conda_envs:
        
            cmd = ['conda', 'env', 'config', 'vars', 'unset',]
            
            for env_var in env_vars_toset:
                cmd.append(f'{env_var}')
            cmd.append('-n')
            cmd.append(cenv)
            
            cmd = ' '.join(cmd)
            Exec(cmd, LocalExecInfo(env=self.mod_env,))
            self.log(f"DDMD _unset_vfd_vars for {cenv}: {cmd}")

    def _set_env_vars(self, env_vars_toset):
        
        conda_envs = [self.config['conda_openmm'], self.config['conda_pytorch']]
        
        for cenv in conda_envs:
            
            # Unset all env_vars_toset first
            self._unset_vfd_vars(env_vars_toset)

            cmd = [ 'conda', 'env', 'config', 'vars', 'set']
            for env_var in env_vars_toset:
                env_var_val = self.mod_env[env_var]
                cmd.append(f'{env_var}={env_var_val}')
            
            cmd.append('-n')
            cmd.append(cenv)
            cmd = ' '.join(cmd)
            self.log(f"DDMD _set_env_vars for {cenv}: {cmd}")
            Exec(cmd, LocalExecInfo(env=self.mod_env,))
        

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        
        print("INFO: removing all previous runs")
        self.clean()

        if self.config['with_hermes'] == True:
            self._set_env_vars(self.hermes_env_vars)
        else:
            self._unset_vfd_vars(self.hermes_env_vars)

        # Check if all the OpenMM files exist
        if self._check_openmm() == False and self.config['skip_sim'] == True:
            print("ERROR: OpenMM files not found, cannot skip simulation")
            self.config['skip_sim'] = False
        
        iter_cnt = self.config['iter_count']
        
        total_start = time.time()
        
        for i in range(iter_cnt):
                            
            if self.config['skip_sim'] == False:
                start = time.time()
                self.openmm_list = self._run_openmm()
                # wait for all self.openmm_list to finish
                for task in self.openmm_list:
                    if task is not None:
                        task.wait()
                
                end = time.time()
            
                print(f"OpenMM[{(self.config['stage_idx'])}] : " + str(end - start) + " seconds")
            else:
                print("Skipping OpenMM stage")
            
            if self.config['short_pipe'] == False:
                start = time.time()
                self._run_aggregate()
                end = time.time()
                print(f"Aggregate[{(self.config['stage_idx'])}] : " + str(end - start) + " seconds")
                
            
            self.config['stage_idx']+=1
            
            train_start = time.time()
            self.train = self._run_train()
            if self.config['short_pipe'] == False:
                self.train.wait()
                end = time.time()
                print(f"Train[{(self.config['stage_idx'])}] : " + str(end - train_start) + " seconds")
            else:
                print("Shortened Pipeline: Train stage not waited")
            
            self.config['stage_idx']+=1
            
            start = time.time()
            self.inference = self._run_inference()
            end = time.time()
            
            if self.config['short_pipe'] == False:
                print(f"Inference stage[{(self.config['stage_idx'])}] : " + str(end - start) + " seconds")
            else:
                self.train.wait()
                end = time.time()
                print(f"Train[{(self.config['stage_idx']-1)}] and Inference[{(self.config['stage_idx'])}] : " + str(end - train_start) + " seconds")

        total_end = time.time()
        print(f"Total time: {total_end - total_start} seconds")
    
    
    def kill(self):
        """
        Kill a running application. E.g., OrangeFS will kill the servers,
        clients, and metadata services.

        :return: None
        """
        # FIXME: this will kill all python processes
        print("INFO: killing all python processes")
        Kill('python',
             PsshExecInfo(hostfile=self.jarvis.hostfile,
                          env=self.env))
        
    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        remove_paths = [
            "agent_runs", "inference_runs", "model_selection_runs",
            "aggregate_runs", "machine_learning_runs", "molecular_dynamics_runs"
        ]
        
        if self.config['skip_sim'] == True:
            print("INFO: do not clean OpenMM")
            # remove all paths excepts molecular_dynamics_runs
            for rp in remove_paths:
                if rp != "molecular_dynamics_runs":
                    remove_path = self.config['experiment_path'] + "/" + rp
                    print("INFO: removing " + remove_path)
                    Rm(remove_path)
        else:
            for rp in remove_paths:
                remove_path = self.config['experiment_path'] + "/" + rp
                print("INFO: removing " + remove_path)
                Rm(remove_path)
```

### `builtin/builtin/dlio_benchmark/pkg.py`

```python
"""
This module provides classes and methods to launch the DlioBenchmark application.
DlioBenchmark is ....
"""
from jarvis_cd.basic.pkg import Application, Color
from jarvis_util import *


class DlioBenchmark(Application):
    """
    This class provides methods to launch the DlioBenchmark application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            # workload related configurations
            {
                'name': 'workload',  # The name of the parameter
                'msg': 'specify the workload name',  # Describe this parameter
                'type': str,  # What is the parameter type?
                'default': 'unet3d_a100',  # What is the default value if not required?
                'choices': [],
                'args': [],
            },
            {
                'name': 'generate_data',
                'msg': 'Does require to generate data before training?',
                'type': bool,
                'default': False,
                'choices': [],
                'args': [],
            },
            {
                'name': 'checkpoint_supported',
                'msg': 'Does the workload support checkpointing?',
                'type': bool,
                'default': True,
                'choices': [],
                'args': [],
            }, 
            {
                'name': 'checkpoint',
                'msg': 'Enable/disable checkpoint',
                'type': bool,
                'default': True,
                'choices': [],
                'args': [],
            }, 
            # dataset related configurations
            {
                'name': 'data_path',
                'msg': 'The path of the dataset',
                'type': str,
                'default': None,
                'choices': [],
                'args': [],
            },
            {
                'name': 'num_files_train',
                'msg': 'Number of files used for training',
                'type': int,
                'default': None,
                'choices': [],
                'args': [],
            },
            # reader related configurations
            {
                'name': 'batch_size',
                'msg': 'Number of samples read per iteration',
                'type': int,
                'default': None,
                'choices': [],
                'args': [],
            },
            {
                'name': 'read_threads',
                'msg': 'Number of read threads in dataloader',
                'type': int,
                'default': None,
                'choices': [],
                'args': [],
            }, 
            # train related configurations
            {
                'name': 'epochs',
                'msg': 'Number of epochs to run',
                'type': int,
                'default': None,
                'choices': [],
                'args': [],
            },
            # checkpoint related configurations
            {
                'name': 'checkpoint_path',
                'msg': 'Path of the checkpoint files',
                'type': str,
                'default': None,
                'choices': [],
                'args': [],
            }, 
            {
                'name': 'checkpoint_after_epoch',
                'msg': 'Checkpoint after the specified epoch id',
                'type': int,
                'default': None,
                'choices': [],
                'args': [],
            }, 
            {
                'name': 'epochs_between_checkpoints',
                'msg': 'Checkpoint interval (unit: epochs)',
                'type': int,
                'default': None,
                'choices': [],
                'args': [],
            }, 
            # process related configuration
            {
                'name': 'nprocs',
                'msg': 'Number of processes',
                'type': int,
                'default': 8,
            },
            {
                'name': 'ppn',
                'msg': 'The number of processes per node',
                'type': int,
                'default': 8,
            },
            # Run with tracing or not
            {
                'name': 'tracing',
                'msg': 'Enable/disable tracing (running with/without DFTracer)',
                'type': bool,
                'default': False,
            }, 
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        # reconfigure data_path
        if self.config['data_path'] is None:
            self.config['data_path'] = f"data/{self.config['workload']}"
        elif f"data/{self.config['workload']}" not in self.config['data_path']:
            self.config['data_path'] = f"{self.config['data_path']}/data/{self.config['workload']}"  

        # reconfigure checkpoint path
        if self.config['checkpoint_supported']:
            if self.config['checkpoint_path'] is None:
                self.config['checkpoint_path'] = f"checkpoints/{self.config['workload']}"
            elif f"checkpoints/{self.config['workload']}" not in self.config['checkpoint_path']:
                self.config['checkpoint_path'] = f"{self.config['checkpoint_path']}/checkpoints/{self.config['workload']}" 

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        
        # step1: generate data if it is required before training
        if self.config['generate_data']:
            # construct the command
            gen_cmd = [
                'dlio_benchmark',
                f'workload={self.config['workload']}',
                f'++workload.workflow.generate_data=True',
                f'++workload.workflow.train=False',
                f'++workload.dataset.data_folder={self.config['data_path']}' 
            ]

            if self.config['num_files_train'] is not None:
                gen_cmd.append(f'++workload.dataset.num_files_train={self.config['num_files_train']}')

            # run the command to generate data
            Exec(' '.join(gen_cmd),
                MpiExecInfo(env=self.mod_env,
                            hostfile=self.jarvis.hostfile,
                            nprocs=self.config['nprocs'],
                            ppn=self.config['ppn']))

        # step2: clear the system cache
        Exec('sudo drop_caches',
             PsshExecInfo(env=self.env,
                        hostfile=self.jarvis.hostfile))
        
        # step3: run the benchmark with the workload
        if self.config['tracing']:
            self.mod_env['DFTRACER_ENABLE'] = '1'
            self.mod_env['DFTRACER_INC_METADATA'] = '1'   

        run_cmd = [
            'dlio_benchmark',
            f'workload={self.config['workload']}',
            f'++workload.workflow.generate_data=False',
            f'++workload.workflow.train=Train',
            f'++workload.dataset.data_folder={self.config['data_path']}'  
        ]

        if self.config['num_files_train'] is not None:
            run_cmd.append(f'++workload.dataset.num_files_train={self.config['num_files_train']}')
        
        if self.config['batch_size'] is not None:
            run_cmd.append(f'++workload.reader.batch_size={self.config['batch_size']}')
        
        if self.config['read_threads'] is not None:
            run_cmd.append(f'++workload.reader.read_threads={self.config['read_threads']}')

        if self.config['epochs'] is not None:
            run_cmd.append(f'++workload.train.epochs={self.config['epochs']}')
        
        if self.config['checkpoint_supported']:
            run_cmd.append(f'++workload.workflow.checkpoint={self.config['checkpoint']}')
            run_cmd.append(f'++workload.checkpoint.checkpoint_folder={self.config['checkpoint_path']}')
            if self.config['checkpoint_after_epoch'] is not None:
                run_cmd.append(f'++workload.checkpoint.checkpoint_after_epoch={self.config['checkpoint_after_epoch']}')
            if self.config['epochs_between_checkpoints'] is not None:
                run_cmd.append(f'++workload.checkpoint.epochs_between_checkpoints={self.config['epochs_between_checkpoints']}') 
        #print(f"self.env = {self.env}", flush=True)
        # run the benchmark command
        Exec(' '.join(run_cmd),
             MpiExecInfo(env=self.mod_env,
                         hostfile=self.jarvis.hostfile,
                         nprocs=self.config['nprocs'],
                         ppn=self.config['ppn']))
        

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        # clear data path
        Rm(self.config['data_path'] + '*',
           PsshExecInfo(env=self.env,
                        hostfile=self.jarvis.hostfile))

        self.log(f'Removing dataset {self.config['data_path']}', Color.YELLOW)

        # clear checkpoint
        Rm(self.config['checkpoint_path'] + '*',
           PsshExecInfo(env=self.env,
                        hostfile=self.jarvis.hostfile))
        
        self.log(f'Removing checkpoints {self.config['checkpoint_path']}', Color.YELLOW)
```

### `builtin/builtin/echo/pkg.py`

```python
"""
This module provides classes and methods to launch the Echo application.
Echo is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class Echo(Application):
    """
    This class provides methods to launch the Echo application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return []

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        print('Echo!')

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/filebench/pkg.py`

```python
"""
This module provides classes and methods to launch Redis.
Redis cluster is used if the hostfile has many hosts
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class Filebench(Application):
    """
    This class provides methods to launch the Ior application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'workload',
                'msg': 'The filebench workload to use',
                'type': str,
                'default': 'fileserver',
                'choices': [],
                'args': [],
            },
            {
                'name': 'dir',
                'msg': 'Directory to use',
                'type': str,
                'default': '/tmp/${USER}/',
                'choices': [],
                'args': [],
            },
            {
                'name': 'run',
                'msg': 'Total runtime (seconds)',
                'type': int,
                'default': 15,
                'choices': [],
                'args': [],
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        # Create the redis hostfile
        workload = self.config['workload']
        dir = os.path.expandvars(self.config['dir'])
        nfiles = SizeConv.to_int(self.config['nfiles'])
        self.copy_template_file(f'{self.pkg_dir}/config/{workload}.f',
                                f'{self.shared_dir}/{workload}.f',
                                {
                                    'DIR': dir,
                                    'RUN': self.config['run'],
                                })

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        cmd = [
            'setarch `arch` --addr-no-randomize',
            'filebench',
            f'-f {self.shared_dir}/{self.config["workload"]}.f',
        ]
        cmd = ' '.join(cmd)
        self.log(cmd, color=Color.YELLOW)
        Exec(cmd,
             PsshExecInfo(env=self.mod_env,
                          hostfile=self.jarvis.hostfile,
                          do_dbg=self.config['do_dbg'],
                          dbg_port=self.config['dbg_port']))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        Kill('filebench',
             PsshExecInfo(env=self.env,
                          hostfile=self.jarvis.hostfile))

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        Rm(self.config['dir'] + '*',
           PsshExecInfo(env=self.env,
                        hostfile=self.jarvis.hostfile))
```

### `builtin/builtin/fio/pkg.py`

```python
"""
This module provides classes and methods to launch the Ior application.
Ior is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class Fio(Application):
    """
    This class provides methods to launch the Ior application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'write',
                'msg': 'Perform a write workload',
                'type': bool,
                'default': True,
                'choices': [],
                'args': [],
            },
            {
                'name': 'read',
                'msg': 'Perform a read workload',
                'type': bool,
                'default': False,
            },
            {
                'name': 'xfer',
                'msg': 'The size of data transfer',
                'type': str,
                'default': '1m',
            },
            {
                'name': 'total_size',
                'msg': 'Total amount of data to generate',
                'type': str,
                'default': '32m',
            },
            {
                'name': 'iodepth',
                'msg': 'Total I/O to generate at a time',
                'type': int,
                'default': 1,
            },
            {
                'name': 'reps',
                'msg': 'Number of times to repeat',
                'type': int,
                'default': 1,
            },
            {
                'name': 'nprocs',
                'msg': 'Number of threads/processes',
                'type': int,
                'default': 1,
            },
            {
                'name': 'out',
                'msg': 'Path to the output file',
                'type': str,
                'default': '/tmp/ior.bin',
            },
            {
                'name': 'direct',
                'msg': 'Use direct I/O',
                'type': bool,
                'default': False,
            },
            {
                'name': 'random',
                'msg': 'Use random I/O',
                'type': bool,
                'default': False,
            },
            {
                'name': 'engine',
                'msg': 'backend engine',
                'type': bool,
                'default': 'psync',
            },
            {
                'name': 'log',
                'msg': 'Path to IOR output log',
                'type': str,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        # Read/write
        if self.config['read'] and self.config['write']:
            mode = 'readwrite'
        elif self.config['read']:
            mode = 'read'
        elif self.config['write']:
            mode = 'write'
        # Direct I/O
        if self.config['direct']:
            direct = 1
        else:
            direct = 0
        # Random I/O
        if self.config['random']:
            random = 1
        else:
            random = 0
        cmd = [
            'fio',
            f'--rw={mode}',
            f'--size={self.config["total_size"]}',
            f'--bs={self.config["xfer"]}',
            f'--iodepth={self.config["iodepth"]}',
            f'--numjobs={self.config["nprocs"]}',
            f'--direct={direct}',
            f'--randrepeat={random}',
            f'--filename={self.config["out"]}',
            f'--ioengine={self.config["engine"]}',
            f'--name=job',
        ]
        # The path
        if '.' in os.path.basename(self.config['out']):
            os.makedirs(str(pathlib.Path(self.config['out']).parent),
                        exist_ok=True)
        else:
            os.makedirs(self.config['out'], exist_ok=True)
        # pipe_stdout=self.config['log'] 
        Exec(' '.join(cmd),
             LocalExecInfo(env=self.mod_env,
                         hostfile=self.jarvis.hostfile,
                         do_dbg=self.config['do_dbg'],
                         dbg_port=self.config['dbg_port']))
        
    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        Rm(self.config['out'] + '*',
           LocalExecInfo())

    def _get_stat(self, stat_dict):
        """
        Get statistics from the application.

        :param stat_dict: A dictionary of statistics.
        :return: None
        """
        stat_dict[f'{self.pkg_id}.runtime'] = self.start_time
```

### `builtin/builtin/gadget2/config/gassphere.yaml`

```yaml
PEANOHILBERT: true
WALLCLOCK: true
SYNCHRONIZATION: true
```

### `builtin/builtin/gadget2/config/lcdm_gas-ngen.yaml`

```yaml
PERIODIC: true
PEANOHILBERT: true
WALLCLOCK: true
SYNCHRONIZATION: true
PMGRID: 128
```

### `builtin/builtin/gadget2/config/lcdm_gas.yaml`

```yaml
PERIODIC: true
PEANOHILBERT: true
WALLCLOCK: true
SYNCHRONIZATION: true
PMGRID: 128
```

### `builtin/builtin/gadget2/pkg.py`

```python
"""
This module provides classes and methods to launch the Gadget2 application.
Gadget2 is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class Gadget2(Application):
    """
    This class provides methods to launch the Gadget2 application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'nprocs',
                'msg': 'Number of processes to spawn',
                'type': int,
                'default': 1,
            },
            {
                'name': 'ppn',
                'msg': 'Processes per node',
                'type': int,
                'default': None,
            },
            {
                'name': 'j',
                'msg': 'Number of threads to use for building gadget',
                'type': int,
                'default': 8,
            },
            {
                'name': 'test_case',
                'msg': 'The test case to use',
                'type': str,
                'default': 'gassphere',
            },
            {
                'name': 'out',
                'msg': 'The directory to output data to',
                'type': str,
                'default': '${HOME}/gadget_data',
            },
            {
                'name': 'buffer_size',
                'msg': 'The size in MB of buffers used for communication. '
                       '100MB is typically an upper bound.',
                'type': float,
                'default': 15,
            },
            {
                'name': 'part_alloc_factor',
                'msg': 'Allocate space for particles per processor. '
                       'Typically should be in the range of 1 to 3.',
                'type': float,
                'default': 1.1,
            },
            {
                'name': 'tree_alloc_factor',
                'msg': 'Allocate space for the BH-tree, which is typically '
                       'smaller than the number of particles.',
                'type': float,
                'default': .9,
            },
            {
                'name': 'max_size_timestep',
                'msg': 'The maximum time step of a particle',
                'type': float,
                'default': .01,
            },
            {
                'name': 'time_max',
                'msg': 'The maximum time the simulation estimates (seconds)',
                'type': float,
                'default': 3,
            },
            {
                'name': 'time_bet_snapshot',
                'msg': 'The number of estimated seconds before snapshot occurs',
                'type': float,
                'default': .2,
            },
            {
                'name': 'ic',
                'msg': 'The initial conditions file to use.',
                'type': str,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        test_case = self.config['test_case']
        paramfile = f'{self.config_dir}/{test_case}.param'
        buildconf = f'{self.pkg_dir}/config/{test_case}.yaml'
        outdir = expand_env(self.config['out'])
        self.copy_template_file(f'{self.pkg_dir}/paramfiles/{test_case}.param',
                                paramfile,
                                replacements={
                                    'OUTPUT_DIR': outdir,
                                    'REPO_DIR': self.env['GADGET2_PATH'],
                                    'BUFFER_SIZE': self.config['buffer_size'],
                                    'PART_ALLOC_FACTOR': self.config['part_alloc_factor'],
                                    'TREE_ALLOC_FACTOR': self.config['tree_alloc_factor'],
                                    'TIME_MAX': self.config['time_max'],
                                    'TIME_BET_SNAPSHOT': self.config['time_bet_snapshot'],
                                    'MAX_SIZE_TIMESTEP': self.config['max_size_timestep'],
                                    'INITCOND': self.config['ic'],
                                })
        build_dir = f'{self.shared_dir}/build'
        cmake_opts = YamlFile(buildconf).load()
        if 'FFTW_PATH' in self.env:
            cmake_opts['FFTW_PATH'] = self.env['FFTW_PATH']
        Cmake(self.env['GADGET2_PATH'],
              build_dir,
              opts=cmake_opts,
              exec_info=LocalExecInfo(env=self.env))
        Make(build_dir, nthreads=self.config['j'],
             exec_info=LocalExecInfo(env=self.env))

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        test_case = self.config['test_case']
        build_dir = f'{self.shared_dir}/build'
        exec_path = f'{build_dir}/bin/Gadget2'
        paramfile = f'{self.config_dir}/{test_case}.param'
        Mkdir(self.config['out'])
        Exec(f'{exec_path} {paramfile}',
             MpiExecInfo(nprocs=self.config['nprocs'],
                         ppn=self.config['ppn'],
                         hostfile=self.jarvis.hostfile,
                         env=self.mod_env,
                         cwd=self.env['GADGET2_PATH'],
                         do_dbg=self.config['do_dbg'],
                         dbg_port=self.config['dbg_port']))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        build_dir = f'{self.shared_dir}/build'
        Rm([self.config['out']])
```

### `builtin/builtin/gadget2_df/pkg.py`

```python
"""
This module provides classes and methods to launch the Gadget2Df application.
Gadget2Df is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class Gadget2Df(Application):
    """
    This class provides methods to launch the Gadget2Df application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'nprocs',
                'msg': 'Number of processes to spawn',
                'type': int,
                'default': 1,
            },
            {
                'name': 'ppn',
                'msg': 'Processes per node',
                'type': int,
                'default': None,
            },
            {
                'name': 'j',
                'msg': 'Number of threads to use for building gadget',
                'type': int,
                'default': 8,
            },
            {
                'name': 'nparticles',
                'msg': 'The maximum number of particles to generate. Should'
                       'be a multiple of 4096.',
                'type': int,
                'default': 4096,
            },
            {
                'name': 'ic',
                'msg': 'The name of the initial condition output file.',
                'type': str,
                'default': 'ics',
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        paramfile = f'{self.config_dir}/ics.param'
        nparticles = self.config['nparticles']
        tile_fac = int((nparticles / 4096) ** (1.0 / 3.0))
        nparticles = 4096 * tile_fac ** 3
        print(f'NUMBER OF PARTICLES: {nparticles}')
        if tile_fac < 1:
            tile_fac = 1
        nsample = int(tile_fac * 16)
        self.copy_template_file(f'{self.pkg_dir}/paramfiles/ics.param',
                                paramfile,
                                replacements={
                                    'REPO_DIR': self.env['GADGET2_PATH'],
                                    'TILE_FAC': tile_fac,
                                    'NSAMPLE': nsample,
                                    'FILE_BASE': self.config['ic'],
                                })
        build_dir = f'{self.shared_dir}/build'
        cmake_opts = {}
        Mkdir(f'{self.env["GADGET2_PATH"]}/ICs-NGen')
        if 'FFTW_PATH' in self.env:
            cmake_opts['FFTW_PATH'] = self.env['FFTW_PATH']
        Cmake(self.env['GADGET2_PATH'],
              build_dir,
              opts=cmake_opts,
              exec_info=LocalExecInfo(env=self.env))
        Make(build_dir, nthreads=self.config['j'],
             exec_info=LocalExecInfo(env=self.env))

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        build_dir = f'{self.shared_dir}/build'
        paramfile = f'{self.config_dir}/ics.param'
        exec_path = f'{build_dir}/bin/NGenIC'
        ngenic_root = f'{self.env["GADGET2_PATH"]}/N-GenIC'
        Exec(f'{exec_path} {paramfile}',
             MpiExecInfo(nprocs=self.config['nprocs'],
                         ppn=self.config['ppn'],
                         hostfile=self.jarvis.hostfile,
                         env=self.mod_env,
                         cwd=ngenic_root))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        ics_path = f'{self.env["GADGET2_PATH"]}/ICs-NGen/{self.config["ic"]}.*'
        print(ics_path)
        Rm(ics_path)
```

### `builtin/builtin/gray_scott/config/adios2.xml`

```xml
<?xml version="1.0"?>
<adios-config>

    <!--============================================
           Configuration for Gray-Scott and GS Plot
        ============================================-->

    <io name="SimulationOutput">
        <engine type="FileStream">
            <!-- SST engine parameters -->
            <parameter key="RendezvousReaderCount" value="0"/>
            <parameter key="QueueLimit" value="1"/>
            <parameter key="QueueFullPolicy" value="Discard"/>
            <!-- BP4/SST engine parameters -->
            <parameter key="OpenTimeoutSecs" value="10.0"/>
        </engine>
    </io>

    <!--===========================================
           Configuration for PDF calc and PDF Plot
        ===========================================-->

    <io name="PDFAnalysisOutput">
        <engine type="FileStream">
            <!-- SST engine parameters -->
            <parameter key="RendezvousReaderCount" value="1"/>
            <parameter key="QueueLimit" value="5"/>
            <parameter key="QueueFullPolicy" value="Block"/>
            <!-- BP4/SST engine parameters -->
            <parameter key="OpenTimeoutSecs" value="10.0"/>
        </engine>

        <!-- Compress variables -->
        <!--
        <variable name="U">
            <operation type="sz">
                <parameter key="accuracy" value="0.001"/>
            </operation>
        </variable>
        <variable name="V">
            <operation type="sz">
                <parameter key="accuracy" value="0.001"/>
            </operation>
        </variable>
        -->
    </io>

    <!-- example engines

        <engine type="FileStream"/>
        <engine type="SST"/>
        <engine type="BP4"/>
        <engine type="BP5"/>
        <engine type="HDF5"/>
        <engine type="File"/>

        === SST ===
        SST can be set up to force blocking the producer on a consumer
        or to discard unused data. Separately, it can be also set up
        so that the producer is waiting for a first connection or
        just starts running alone.

        Producer start alone, and it does not keep data.
        Consumer will get recent data when connects.
        If consumer(s) goes away, producer runs alone and
           discards data.
        <engine type="SST">
            <parameter key="RendezvousReaderCount" value="0"/>
            <parameter key="QueueLimit" value="1"/>
            <parameter key="QueueFullPolicy" value="Discard"/>
        </engine>

        Producer will wait for 1 consumer to connect before proceeding.
        Producer will buffer 5 output steps so a consumer may lag behind a bit.
        If consumer(s) goes away, producer will block indefinitely after
          the buffer is full.
        <engine type="SST">
            <parameter key="RendezvousReaderCount" value="1"/>
            <parameter key="QueueLimit" value="5"/>
            <parameter key="QueueFullPolicy" value="Block"/>
        </engine>

        === BP4 ===
        BP4 is the default ADIOS2 file format.
        'NumAggregators ' parameter controls how many files
            are created under the output folder. By default, each process
            writes its own file (N-to-N pattern), which is fast but is
            not scalable to tens of thousands of processes. The number of
            substreams should be chosen for the capability of the underlying
            filesystem (e.g. twice the number of OST servers on a Lustre file system).
        'OpenTimeoutSecs' parameter specifies how long to wait on a reading Open
            for the file to appear. Useful for streaming when the reader starts up
            faster than the writer produce any output.
        <engine type="BP4">
            <parameter key="NumAggregators " value="4"/>
            <parameter key="OpenTimeoutSecs" value="10.0"/>
        </engine>

        === FileStream ===
        FileStream is a token name for a file format that supports reading while writing
        It refers to BP4 currently. Timeout for opening is set to 1 hour by default for readers.
        'NumAggregators ' parameter is the same as for BP4.
        <engine type="FileStream">
            <parameter key="NumAggregators " value="4"/>
        </engine>

        === File ===
        FileStream is a token name for a file format, useful on reader side to open
        any version of BP or an HDF5 file.
     -->
</adios-config>
```

### `builtin/builtin/gray_scott/pkg.py`

```python
"""
This module provides classes and methods to launch the Gray Scott application.
Gray Scott is a 3D 7-point stencil code for modeling the diffusion of two
substances.
"""
from jarvis_cd.basic.pkg import Application, Color
from jarvis_util import *
import time
import pathlib


class GrayScott(Application):
    """
    This class provides methods to launch the GrayScott application.
    """
    def _init(self):
        """
        Initialize paths
        """
        self.adios2_xml_path = f'{self.shared_dir}/adios2.xml'
        self.settings_json_path = f'{self.shared_dir}/settings-files.json'

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'nprocs',
                'msg': 'Number of processes to spawn',
                'type': int,
                'default': 4,
            },
            {
                'name': 'ppn',
                'msg': 'Processes per node',
                'type': int,
                'default': None,
            },
            {
                'name': 'L',
                'msg': 'Grid size of cube',
                'type': int,
                'default': 32,
            },
            {
                'name': 'Du',
                'msg': 'Diffusion rate of substance U',
                'type': float,
                'default': .2,
            },
            {
                'name': 'Dv',
                'msg': 'Diffusion rate of substance V',
                'type': float,
                'default': .1,
            },
            {
                'name': 'F',
                'msg': 'Feed rate of U',
                'type': float,
                'default': .01,
            },
            {
                'name': 'k',
                'msg': 'Kill rate of V',
                'type': float,
                'default': .05,
            },
            {
                'name': 'dt',
                'msg': 'Timestep',
                'type': float,
                'default': 2.0,
            },
            {
                'name': 'steps',
                'msg': 'Total number of steps to simulate',
                'type': int,
                'default': 100,
            },
            {
                'name': 'plotgap',
                'msg': 'Number of steps between output',
                'type': float,
                'default': 10,
            },
            {
                'name': 'noise',
                'msg': 'Amount of noise',
                'type': float,
                'default': .01,
            },
            {
                'name': 'output',
                'msg': 'Absolute path to output data',
                'type': str,
                'default': None,
            },
            {
                'name': 'engine',
                'msg': 'Engien to be used',
                'choices': ['bp5', 'hermes'],
                'type': str,
                'default': 'bp5',
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        if self.config['output'] is None:
            adios_dir = os.path.join(self.shared_dir, 'gray-scott-output')
            self.config['output'] = os.path.join(adios_dir,
                                                 'data')
            Mkdir(adios_dir, PsshExecInfo(hostfile=self.jarvis.hostfile,
                                          env=self.env))
        settings_json = {
            'L': self.config['L'],
            'Du': self.config['Du'],
            'Dv': self.config['Dv'],
            'F': self.config['F'],
            'k': self.config['k'],
            'dt': self.config['dt'],
            'plotgap': self.config['plotgap'],
            'steps': self.config['steps'],
            'noise': self.config['noise'],
            'output': f'{self.config["output"]}',
            'adios_config': self.adios2_xml_path
        }
        Mkdir(self.config['output'],
              PsshExecInfo(hostfile=self.jarvis.hostfile,
                           env=self.env))
        JsonFile(self.settings_json_path).save(settings_json)

        if self.config['engine'].lower() == 'bp5':
            self.copy_template_file(f'{self.pkg_dir}/config/adios2.xml',
                                self.adios2_xml_path)
        elif self.config['engine'].lower() == 'hermes':
            self.copy_template_file(f'{self.pkg_dir}/config/hermes.xml',
                                    self.adios2_xml_path)
        else:
            raise Exception('Engine not defined')

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        # print(self.env['HERMES_CLIENT_CONF'])
        start = time.time()
        Exec(f'gray-scott {self.settings_json_path}',
             MpiExecInfo(nprocs=self.config['nprocs'],
                         ppn=self.config['ppn'],
                         hostfile=self.jarvis.hostfile,
                         env=self.mod_env))
        end = time.time()
        diff = end - start
        self.log(f'TIME: {diff} seconds', color=Color.GREEN)

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        output_dir = self.config['output'] + "*"
        print(f'Removing {output_dir}')
        Rm(output_dir)
```

### `builtin/builtin/hermes_api/pkg.py`

```python
"""
This module provides classes and methods to inject the HermesMpiio interceptor.
HermesMpiio intercepts the MPI I/O calls used by a native MPI program and
routes it to Hermes.
"""
from jarvis_cd.basic.pkg import Interceptor
from jarvis_util import *


class HermesApi(Interceptor):
    """
    This class provides methods to inject the HermesMpiio interceptor.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'mpi',
                'msg': 'Intercept MPI-IO',
                'type': bool,
                'default': False
            },
            {
                'name': 'posix',
                'msg': 'Intercept POSIX',
                'type': bool,
                'default': False
            },
            {
                'name': 'stdio',
                'msg': 'Intercept STDIO',
                'type': bool,
                'default': False
            },
            {
                'name': 'vfd',
                'msg': 'Intercept HDF5 I/O',
                'type': bool,
                'default': False
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        has_one = False
        if self.config['mpi']:
            self.env['HERMES_MPIIO'] = self.find_library('hermes_mpiio')
            if self.env['HERMES_MPIIO'] is None:
                raise Exception('Could not find hermes_mpi')
            self.env['HERMES_ROOT'] = str(pathlib.Path(self.env['HERMES_MPIIO']).parent.parent)
            print(f'Found libhermes_mpiio.so at {self.env["HERMES_MPIIO"]}')
            has_one = True
        if self.config['posix']:
            self.env['HERMES_POSIX'] = self.find_library('hermes_posix')
            if self.env['HERMES_POSIX'] is None:
                raise Exception('Could not find hermes_posix')
            self.env['HERMES_ROOT'] = str(pathlib.Path(self.env['HERMES_POSIX']).parent.parent)
            print(f'Found libhermes_posix.so at {self.env["HERMES_POSIX"]}')
            has_one = True
        if self.config['stdio']:
            self.env['HERMES_STDIO'] = self.find_library('hermes_stdio')
            if self.env['HERMES_STDIO'] is None:
                raise Exception('Could not find hermes_posix')
            self.env['HERMES_ROOT'] = str(pathlib.Path(self.env['HERMES_STDIO']).parent.parent)
            print(f'Found libhermes_stdio.so at {self.env["HERMES_STDIO"]}')
            has_one = True
        if self.config['vfd']:
            self.env['HERMES_VFD'] = self.find_library('hdf5_hermes_vfd')
            if self.env['HERMES_VFD'] is None:
                raise Exception('Could not find hdf5_hermes_vfd')
            self.env['HERMES_ROOT'] = str(pathlib.Path(self.env['HERMES_VFD']).parent.parent)
            print(f'Found libhdf5_hermes_vfd.so at {self.env["HERMES_VFD"]}')
            has_one = True
        if not has_one:
            raise Exception('Hermes API not selected')

    def modify_env(self):
        """
        Modify the jarvis environment.

        :return: None
        """
        if self.config['mpi']:
            self.append_env('LD_PRELOAD', self.env['HERMES_MPIIO'])
        if self.config['posix']:
            self.append_env('LD_PRELOAD', self.env['HERMES_POSIX'])
        if self.config['stdio']:
            self.append_env('LD_PRELOAD', self.env['HERMES_STDIO'])
        if self.config['vfd']:
            plugin_path_parent = (
                str(pathlib.Path(self.env['HERMES_VFD']).parent))
            self.setenv('HDF5_PLUGIN_PATH', plugin_path_parent)
            self.setenv('HDF5_DRIVER', 'hdf5_hermes_vfd')
```

### `builtin/builtin/hermes_api_bench/pkg.py`

```python
"""
This module provides classes and methods to launch the HermesApiBench application.
HermesApiBench is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class HermesApiBench(Application):
    """
    This class provides methods to launch the HermesApiBench application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'mode',
                'msg': 'The benchmark to run',
                'type': str,
                'default': None,
                'choices': ['putget', 'pputget', 'create_bkt',
                            'get_bkt', 'del_bkt'],
            },
            {
                'name': 'blobs_per_rank',
                'msg': 'The number of blobs to create per-rank',
                'type': str,
                'default': '1',
            },
            {
                'name': 'bkts_per_rank',
                'msg': 'The number of buckets to create per-rank',
                'type': str,
                'default': '1',
            },
            {
                'name': 'blob_size',
                'msg': 'The size of a single blob',
                'type': str,
                'default': '1m',
            },
            {
                'name': 'part_size',
                'msg': 'The size of a partial op on a blob',
                'type': str,
                'default': '4k',
            },
            {
                'name': 'blobs_per_bkt',
                'msg': 'The number of blobs to create in a single bucket',
                'type': str,
                'default': '1',
            },
            {
                'name': 'nprocs',
                'msg': 'The number of processes to spawn',
                'type': int,
                'default': 1,
            },
            {
                'name': 'ppn',
                'msg': 'The number of processes per node',
                'type': int,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        mode = self.config['mode']
        cmd = [f'hermes_api_bench {mode}']
        if mode == 'putget':
            cmd += [
                self.config['blob_size'],
                self.config['blobs_per_rank']
            ]
        elif mode == 'pputget':
            cmd += [
                self.config['blob_size'],
                self.config['part_size'],
                self.config['blobs_per_rank']
            ]
        elif mode == 'create_bkt':
            cmd += [
                self.config['bkts_per_rank']
            ]
        elif mode == 'get_bkt':
            cmd += [
                self.config['bkts_per_rank']
            ]
        elif mode == 'del_bkt':
            cmd += [
                self.config['bkts_per_rank'],
                self.config['blobs_per_bkt'],
            ]
        cmd = ' '.join(cmd)
        Exec(cmd, MpiExecInfo(nprocs=self.config['nprocs'],
                              env=self.env,
                              hosts=self.jarvis.hostfile,
                              ppn=self.config['ppn'],
                              do_dbg=self.config['do_dbg'],
                              dbg_port=self.config['dbg_port']))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/hermes_mpiio_tests/pkg.py`

```python
"""
This module provides classes and methods to launch the HermesMpiioTests application.
HermesMpiioTests is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class HermesMpiioTests(Application):
    """
    This class provides methods to launch the HermesMpiioTests application.
    """
    def _init(self):
        """
        Initialize paths
        """
        return

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'test_file',
                'choices': ['mpiio_basic'],
                'msg': '',
                'type': str,
                'default': None,
            },
            {
                'name': 'test_case',
                'msg': 'Specify exact test case to run',
                'type': str,
                'default': None,
            },
            {
                'name': 'hermes',
                'msg': 'Whether or not to use Hermes',
                'type': bool,
                'default': False,
            },
            {
                'name': 'sync',
                'msg': 'The size of the test to run',
                'choices': [None, 'sync', 'async'],
                'type': str,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        Mkdir("/tmp/test_hermes")
        test_fun = getattr(self, f'test_{self.config["test_file"]}')
        test_fun()

    def test_mpiio_basic(self):
        cmd = 'mpiio_adapter_test'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        if self.config['test_case']:
            cmd = f'{cmd} {self.config["test_case"]}'
        else:
            mpiio_cmd = [cmd]
            if self.config['sync'] == 'sync':
                mpiio_cmd.append('[synchronicity=sync]')
            elif self.config['sync'] == 'async':
                mpiio_cmd.append('[synchronicity=async]')
            mpiio_cmd.append('--reporter compact -d yes')
            cmd = ' '.join(mpiio_cmd)
        node = Exec(cmd,
                    MpiExecInfo(nprocs=1,
                                env=self.mod_env,
                                do_dbg=self.config['do_dbg'],
                                dbg_port=self.config['dbg_port'],
                                pipe_stdout=self.config['stdout'],
                                pipe_stderr=self.config['stderr']))
        return node.exit_code

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/hermes_posix_tests/pkg.py`

```python
"""
This module provides classes and methods to launch the HermesPosixTests application.
HermesPosixTests is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class HermesPosixTests(Application):
    """
    This class provides methods to launch the HermesPosixTests application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'test_file',
                'choices': ['posix_basic',
                            'posix_basic_mpi',
                            'posix_simple_io_omp'],
                'msg': '',
                'type': str,
                'default': None,
            },
            {
                'name': 'test_case',
                'msg': 'Specify exact test case to run',
                'type': str,
                'default': None,
            },
            {
                'name': 'hermes',
                'msg': 'Whether or not to use Hermes',
                'type': bool,
                'default': False,
            },
            {
                'name': 'size',
                'msg': 'The size of the test to run',
                'choices': [None, 'small', 'large'],
                'type': str,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        Mkdir("/tmp/test_hermes")
        test_fun = getattr(self, f'test_{self.config["test_file"]}')
        test_fun()

    def test_posix_basic(self):
        cmd = 'posix_adapter_test'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        if self.config['test_case']:
            cmd = (f'{cmd} {self.config["test_case"]}')
            # cmd = (f'{cmd} BatchedWriteTemporalFixed,BatchedReadSequentialTemporalFixed')
        else:
            posix_cmd = [cmd]
            if self.config['size'] == 'small':
                posix_cmd.append('~[request_size=range-small]')
            elif self.config['size'] == 'large':
                posix_cmd.append('~[request_size=range-large]')
            posix_cmd.append('--reporter compact -d yes')
            cmd = ' '.join(posix_cmd)
        node = Exec(cmd,
                    LocalExecInfo(env=self.mod_env,
                                  do_dbg=self.config['do_dbg'],
                                  dbg_port=self.config['dbg_port'],
                                  pipe_stdout=self.config['stdout'],
                                  pipe_stderr=self.config['stderr']))
        return node.exit_code

    def test_posix_basic_mpi(self):
        cmd = 'posix_adapter_mpi_test'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        if self.config['test_case']:
            cmd = f'{cmd} {self.config["test_case"]}'
        else:
            posix_cmd = [cmd]
            if self.config['size'] == 'small':
                posix_cmd.append('~[request_size=range-small]')
            elif self.config['size'] == 'large':
                posix_cmd.append('~[request_size=range-large]')
            posix_cmd.append('--reporter compact -d yes')
            cmd = ' '.join(posix_cmd)
        node = Exec(cmd,
                    MpiExecInfo(nprocs=2,
                                env=self.mod_env,
                                do_dbg=self.config['do_dbg'],
                                dbg_port=self.config['dbg_port'],
                                pipe_stdout=self.config['stdout'],
                                pipe_stderr=self.config['stderr']))
        return node.exit_code

    def test_posix_simple_io_omp(self):
        cmd = 'posix_simple_io_omp'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        cmd = f'{cmd} /tmp/test_hermes/hi.txt 0 1024 8 0'
        node = Exec(cmd,
                    LocalExecInfo(env=self.mod_env,
                                  do_dbg=self.config['do_dbg'],
                                  dbg_port=self.config['dbg_port']))
        return node.exit_code

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/hermes_run/pkg.py`

```python
"""
This module provides classes and methods to launch the HermesRun service.
hrun is ....
"""

from jarvis_cd.basic.pkg import Service, Color
from jarvis_util import *


class HermesRun(Service):
    """
    This class provides methods to launch the HermesRun service.
    """
    def _init(self):
        """
        Initialize paths
        """
        self.daemon_pkg = None
        self.hostfile_path = f'{self.shared_dir}/hostfile'
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'num_nodes',
                'msg': 'Number of nodes to run hermes on. 0 means all',
                'type': int,
                'default': 0,
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'data_shm',
                'msg': 'Data buffering space',
                'type': str,
                'default': '8g',
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'rdata_shm',
                'msg': 'Runtime data buffering space',
                'type': str,
                'default': '8g',
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'task_shm',
                'msg': 'Task buffering space',
                'type': str,
                'default': '0g',
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'shm_name',
                'msg': 'The base shared-memory name',
                'type': str,
                'default': 'hrun_shm_${USER}',
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'port',
                'msg': 'The port to listen for data on',
                'type': int,
                'default': 8080,
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'provider',
                'msg': 'The libfabric provider type to use (e.g., sockets)',
                'type': str,
                'default': None,
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'domain',
                'msg': 'The libfabric domain to use (e.g., lo)',
                'type': str,
                'default': None,
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'fabric',
                'msg': 'The libfabric fabric to use (e.g., 192.168.0.0/16)',
                'type': str,
                'default': None,
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'threads',
                'msg': 'the number of rpc threads to create',
                'type': int,
                'default': 32,
                'class': 'communication',
                'rank': 1,
            },
            {
                'name': 'recency_max',
                'msg': 'time before blob is considered stale (sec)',
                'type': float,
                'default': 1,
                'class': 'buffer organizer',
                'rank': 1,
            },
            {
                'name': 'borg_min_cap',
                'msg': 'Capacity percentage before reorganizing can begin',
                'type': float,
                'default': 0,
                'class': 'buffer organizer',
                'rank': 1,
            },
            {
                'name': 'flush_period',
                'msg': 'Period of time to check for flushing (milliseconds)',
                'type': int,
                'default': 5000,
                'class': 'buffer organizer',
                'rank': 1,
            },
            {
                'name': 'qdepth',
                'msg': 'The depth of queues',
                'type': int,
                'default': 100000,
                'class': 'queuing',
                'rank': 1,
            },
            {
                'name': 'pqdepth',
                'msg': 'The depth of the process queue',
                'type': int,
                'default': 48,
                'class': 'queuing',
                'rank': 1,
            },
            {
                'name': 'qlanes',
                'msg': 'The number of lanes per queue',
                'type': int,
                'default': 4,
                'class': 'queuing',
                'rank': 1,
            },
            {
                'name': 'dworkers',
                'msg': 'The number of core-dedicated workers',
                'type': int,
                'default': 2,
                'class': 'queuing',
                'rank': 1,
            },
            {
                'name': 'oworkers',
                'msg': 'The number of overlapping workers',
                'type': int,
                'default': 4,
                'class': 'queuing',
                'rank': 1,
            },
            {
                'name': 'oworkers_per_core',
                'msg': 'Overlapping workers per core',
                'type': int,
                'default': 32,
                'class': 'queuing',
                'rank': 1,
            },
            {
                'name': 'include',
                'msg': 'Specify paths to include',
                'type': list,
                'default': [],
                'class': 'adapter',
                'rank': 1,
                'args': [
                    {
                        'name': 'path',
                        'msg': 'The path to be included',
                        'type': str
                    },
                ],
                'aliases': ['i']
            },
            {
                'name': 'exclude',
                'msg': 'Specify paths to exclude',
                'type': list,
                'default': [],
                'class': 'adapter',
                'rank': 1,
                'args': [
                    {
                        'name': 'path',
                        'msg': 'The path to be excluded',
                        'type': str
                    },
                ],
                'aliases': ['e']
            },
            {
                'name': 'adapter_mode',
                'msg': 'The adapter mode to use for Hermes',
                'type': str,
                'default': 'default',
                'choices': ['default', 'scratch', 'bypass'],
                'class': 'adapter',
                'rank': 1,
            },
            {
                'name': 'flush_mode',
                'msg': 'The flushing mode to use for adapters',
                'type': str,
                'default': 'async',
                'choices': ['sync', 'async'],
                'class': 'adapter',
                'rank': 1,
            },
            {
                'name': 'log_verbosity',
                'msg': 'Verbosity of the output, 0 for fatal, 1 for info',
                'type': int,
                'default': 1,
            },
            {
                'name': 'page_size',
                'msg': 'The page size to use for adapters',
                'type': str,
                'default': '1m',
                'class': 'adapter',
                'rank': 1,
            },
            {
                'name': 'ram',
                'msg': 'Amount of RAM to use for buffering',
                'type': str,
                'default': '0',
                'class': 'dpe',
                'rank': 1,
            },
            {
                'name': 'dpe',
                'msg': 'The DPE to use by default',
                'type': str,
                'default': 'MinimizeIoTime',
                'class': 'dpe',
                'rank': 1,
            },
            {
                'name': 'devices',
                'msg': 'Search for a number of devices to include',
                'type': list,
                'default': [],
                'args': [
                    {
                        'name': 'type',
                        'msg': 'The type of the device being queried',
                        'type': str
                    },
                    {
                        'name': 'count',
                        'msg': 'The number of devices being',
                        'type': int
                    }
                ],
                'class': 'dpe',
                'rank': 1,
            }
        ]

    def get_hostfile(self):
        self.hostfile = Hostfile(hostfile=self.hostfile_path)

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param config: The human-readable jarvis YAML configuration for the
        application.
        :return: None
        """
        rg = self.jarvis.resource_graph

        # Get node subset
        self.hostfile = self.jarvis.hostfile
        if self.config['num_nodes'] > 0:
            self.hostfile = self.jarvis.hostfile.subset(self.config['num_nodes'])
            self.hostfile.save(self.hostfile_path)
        
        self.env['HERMES_LOG_VERBOSITY'] = str(self.config['log_verbosity'])
        # Begin making hermes_run config
        hermes_server = {
            'work_orchestrator': {
                'max_dworkers': self.config['dworkers'],
                'max_oworkers': self.config['oworkers'],
                'oworkers_per_core': self.config['oworkers_per_core'],
            },
            'queue_manager': {
                'queue_depth': self.config['qdepth'],
                'proc_queue_depth': self.config['pqdepth'],
                'max_lanes': self.config['qlanes'],
                'max_queues': 1024,
                'shm_allocator': 'kScalablePageAllocator',
                'shm_name': self.config['shm_name'],
                'shm_size': self.config['task_shm'],
                'data_shm_size': self.config['data_shm'],
                'rdata_shm_size': self.config['rdata_shm'],
            },
            'devices': {},
            'rpc': {}
        }

        # Begin making Hermes client config
        hermes_client = {
            'path_inclusions': ['/tmp/test_hermes'],
            'path_exclusions': ['/'],
            'file_page_size': self.config['page_size']
        }
        if self.config['flush_mode'] == 'async':
            hermes_client['flushing_mode'] = 'kAsync'
        elif self.config['flush_mode'] == 'sync':
            hermes_client['flushing_mode'] = 'kSync'
        if self.config['include'] is not None:
            hermes_client['path_inclusions'] += self.config['include']
        if self.config['exclude'] is not None:
            hermes_client['path_exclusions'] += self.config['exclude']

        # Get storage info
        if len(self.config['devices']) == 0:
            # Get all the fastest storage device mount points on machine
            dev_df = rg.find_storage(needs_root=False)
        else:
            # Get the storage devices for the user
            dev_list = [rg.find_storage(dev_types=dev_type,
                                        count_per_pkg=count,
                                        needs_root=False)
                        for dev_type, count in self.config['devices']]
            dev_df = sdf.concat(dev_list)
        if len(dev_df) == 0:
            raise Exception('Hermes needs at least one storage device')
        
        devs = dev_df.rows
        self.config['borg_paths'] = []
        for i, dev in enumerate(devs):
            dev_type = dev['dev_type']
            custom_name = f'{dev_type}_{i}'
            mount = os.path.expandvars(dev['mount'])
            if len(mount) == 0:
                continue
            if dev_type == 'nvme':
                bandwidth = '1g'
                latency = '60us'
            elif dev_type == 'ssd':
                bandwidth = '500MBps'
                latency = '400us'
            elif dev_type == 'hdd':
                bandwidth = '120MBps'
                latency = '5ms'
            else:
                bandwidth = '120MBps'
                latency = '5ms'
            mount = f'{mount}/hermes_data'
            hermes_server['devices'][custom_name] = {
                'mount_point': mount,
                'capacity': int(.9 * float(dev['avail'])),
                'block_size': '4kb',
                'bandwidth': bandwidth,
                'latency': latency,
                'is_shared_device': dev['shared'],
                'borg_capacity_thresh': [0.0, 1.0],
                'slab_sizes': ['4KB', '16KB', '64KB', '1MB']
            }
            self.config['borg_paths'].append(mount)
            Mkdir(mount, PsshExecInfo(hostfile=self.hostfile,
                                      env=self.env))
        if 'ram' in self.config and self.config['ram'] != '0':
            hermes_server['devices']['ram'] = {
                'mount_point': '',
                'capacity': self.config['ram'],
                'block_size': '4kb',
                'bandwidth': '40GBps',
                'latency': '100ns',
                'is_shared_device': False,
                'borg_capacity_thresh': [self.config['borg_min_cap'], 1.0],
                'slab_sizes': ['256', '512', '1KB',
                               '4KB', '16KB', '64KB', '1MB']
            }

        # Get all network info 
        net_info = rg.find_net_info(local=len(self.hostfile) == 1, env=self.env)
        provider = self.config['provider']
        domain = self.config['domain']
        fabric = self.config['fabric']
        if provider is not None:
            net_info = net_info[lambda x: x['provider'] == provider]
        if domain is not None:
            net_info = net_info[lambda x: x['domain'] == domain]
        if fabric is not None:
            net_info = net_info[lambda x: x['fabric'] == fabric]

        # Get fastest providers
        if provider is None:
            providers = net_info['provider'].unique().list() 
            bases = ['verbs', 'tcp', 'sockets']
            suffixes = ['', ';ofi_rxm']
            for base in bases:
                for suffix in suffixes:
                    test_provider = f'{base}{suffix}'
                    if test_provider in providers:
                        provider = test_provider
                        break

        # Get first matching net info
        self.log(f'Provider: {provider}')
        net_info_save = net_info
        if provider is not None:
            net_info = net_info[lambda r: str(r['provider']) == provider]
        if len(net_info) == 0:
            self.log(net_info_save)
            self.log('Failed to find provider for the runtime', Color.RED)
            exit(1)
        net_info = net_info.rows[0]

        # Compile hostfile
        compile = CompileHostfile(self.hostfile, 
                        net_info['provider'],
                        net_info['domain'],
                        net_info['fabric'],
                        self.hostfile_path,
                        env=self.env)
        self.hostfile = compile.hostfile

        # Create network info config
        protocol = net_info['provider']
        domain = net_info['domain']
        hostfile_path = self.hostfile.path
        if self.hostfile.path is None:
            hostfile_path = ''
            domain = ''
        if self.config['domain'] is not None:
            domain = self.config['domain']
        hermes_server['rpc'] = {
            'host_file': hostfile_path,
            'protocol': protocol,
            'domain': domain,
            'port': self.config['port'],
            'num_threads': self.config['threads']
        }
        hermes_server['buffer_organizer'] = {
            'recency_max': self.config['recency_max'],
            'flush_period': self.config['flush_period']
        }
        if self.hostfile.path is None:
            hermes_server['rpc']['host_names'] = self.hostfile.hosts
        hermes_server['default_placement_policy'] = self.config['dpe']
        if self.config['adapter_mode'] == 'default':
            adapter_mode = 'kDefault'
        elif self.config['adapter_mode'] == 'scratch':
            adapter_mode = 'kScratch'
        elif self.config['adapter_mode'] == 'bypass':
            adapter_mode = 'kBypass'
        self.env['HERMES_ADAPTER_MODE'] = adapter_mode
        hermes_server['default_placement_policy'] = self.config['dpe']

        # Save hermes configurations
        hermes_server_yaml = f'{self.shared_dir}/hermes_server.yaml'
        YamlFile(hermes_server_yaml).save(hermes_server)
        self.env['HERMES_CONF'] = hermes_server_yaml

        # Save Hermes client configurations
        hermes_client_yaml = f'{self.shared_dir}/hermes_client.yaml'
        YamlFile(hermes_client_yaml).save(hermes_client)
        self.env['HERMES_CLIENT_CONF'] = hermes_client_yaml

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        self.log(self.env['HERMES_CONF'])
        self.log(self.env['HERMES_CLIENT_CONF'])
        self.get_hostfile()
        self.daemon_pkg = Exec('hrun_start_runtime',
                                PsshExecInfo(hostfile=self.hostfile,
                                             env=self.mod_env,
                                             exec_async=True,
                                             do_dbg=self.config['do_dbg'],
                                             dbg_port=self.config['dbg_port'],
                                             hide_output=self.config['hide_output'],
                                             pipe_stdout=self.config['stdout'],
                                             pipe_stderr=self.config['stderr']))
        time.sleep(self.config['sleep'])
        self.log('Done sleeping')

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        self.log('Stopping hermes_run')
        self.get_hostfile()
        Exec('hrun_stop_runtime',
             LocalExecInfo(hostfile=self.hostfile,
                           env=self.env,
                           exec_async=False,
                           # do_dbg=self.config['do_dbg'],
                           # dbg_port=self.config['dbg_port'] + 2,
                           hide_output=self.config['hide_output']))
        self.log('Client Exited?')
        if self.daemon_pkg is not None:
            self.daemon_pkg.wait()
        self.log('Daemon Exited?')

    def kill(self):
        self.get_hostfile()
        Kill('hrun',
             PsshExecInfo(hostfile=self.hostfile,
                          env=self.env))
        if self.config['do_dbg']:
            Kill('gdbserver',
                 PsshExecInfo(hostfile=self.hostfile,
                              env=self.env))
        self.log('Client Exited?')
        if self.daemon_pkg is not None:
            self.daemon_pkg.wait()
        self.log('Daemon Exited?')

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        self.get_hostfile()
        for path in self.config['borg_paths']:
            self.log(f'Removing {path}', Color.YELLOW)
            Rm(path, PsshExecInfo(hostfile=self.hostfile))

    def status(self):
        """
        Check whether or not an application is running. E.g., are OrangeFS
        servers running?

        :return: True or false
        """
        return True
```

### `builtin/builtin/hermes_stdio_tests/pkg.py`

```python
"""
This module provides classes and methods to launch the HermesStdioTests application.
HermesStdioTests is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class HermesStdioTests(Application):
    """
    This class provides methods to launch the HermesStdioTests application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'test_file',
                'choices': ['stdio_basic',
                            'stdio_basic_mpi',
                            'stdio_low_buf',
                            'stdio_adapter_mode',
                            'stdio_mapper'],
                'msg': '',
                'type': str,
                'default': None,
            },
            {
                'name': 'test_case',
                'msg': 'Specify exact test case to run',
                'type': str,
                'default': None,
            },
            {
                'name': 'hermes',
                'msg': 'Whether or not to use Hermes',
                'type': bool,
                'default': False,
            },
            {
                'name': 'size',
                'msg': 'The size of the test to run',
                'choices': [None, 'small', 'large'],
                'type': str,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        Mkdir("/tmp/test_hermes")
        test_fun = getattr(self, f'test_{self.config["test_file"]}')
        test_fun()

    def test_stdio_basic(self):
        cmd = 'stdio_adapter_test'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        if self.config['test_case']:
            cmd = (f'{cmd} {self.config["test_case"]}')
            # cmd = (f'{cmd} BatchedWriteTemporalFixed,BatchedReadSequentialTemporalFixed')
        else:
            posix_cmd = [cmd]
            if self.config['size'] == 'small':
                posix_cmd.append('~[request_size=range-small]')
            elif self.config['size'] == 'large':
                posix_cmd.append('~[request_size=range-large]')
            posix_cmd.append('--reporter compact -d yes')
            cmd = ' '.join(posix_cmd)
        node = Exec(cmd,
                    LocalExecInfo(env=self.mod_env,
                                  do_dbg=self.config['do_dbg'],
                                  dbg_port=self.config['dbg_port'],
                                  pipe_stdout=self.config['stdout'],
                                  pipe_stderr=self.config['stderr']))
        return node.exit_code

    def test_stdio_basic_mpi(self):
        cmd = 'stdio_adapter_mpi_test'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        if self.config['test_case']:
            cmd = f'{cmd} {self.config["test_case"]}'
        else:
            posix_cmd = [cmd]
            if self.config['size'] == 'small':
                posix_cmd.append('~[request_size=range-small]')
            elif self.config['size'] == 'large':
                posix_cmd.append('~[request_size=range-large]')
            posix_cmd.append('--reporter compact -d yes')
            cmd = ' '.join(posix_cmd)
        node = Exec(cmd,
                    MpiExecInfo(nprocs=2,
                                env=self.mod_env,
                                do_dbg=self.config['do_dbg'],
                                dbg_port=self.config['dbg_port'],
                                pipe_stdout=self.config['stdout'],
                                pipe_stderr=self.config['stderr']))
        return node.exit_code

    def test_stdio_low_buf(self):
        cmd = 'stdio_low_buf_adapter_test'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        if self.config['test_case']:
            cmd = f'{cmd} {self.config["test_case"]}'
        node = Exec(cmd,
                    MpiExecInfo(nprocs=1,
                                env=self.mod_env,
                                do_dbg=self.config['do_dbg'],
                                dbg_port=self.config['dbg_port'],
                                pipe_stdout=self.config['stdout'],
                                pipe_stderr=self.config['stderr']))
        return node.exit_code

    def test_stdio_adapter_mode(self):
        cmd = 'stdio_adapter_mode_test'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        if self.config['test_case']:
            cmd = f'{cmd} {self.config["test_case"]}'
        node = Exec(cmd,
                    MpiExecInfo(nprocs=1,
                                env=self.mod_env,
                                do_dbg=self.config['do_dbg'],
                                dbg_port=self.config['dbg_port'],
                                pipe_stdout=self.config['stdout'],
                                pipe_stderr=self.config['stderr']))
        return node.exit_code

    def test_stdio_mapper(self):
        cmd = 'stdio_adapter_mapper_test'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        if self.config['test_case']:
            cmd = f'{cmd} {self.config["test_case"]}'
        node = Exec(cmd,
                    MpiExecInfo(nprocs=1,
                                env=self.mod_env,
                                do_dbg=self.config['do_dbg'],
                                dbg_port=self.config['dbg_port'],
                                pipe_stdout=self.config['stdout'],
                                pipe_stderr=self.config['stderr']))
        return node.exit_code

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/hermes_unit_tests/pkg.py`

```python
"""
This module provides classes and methods to launch the LabstorIpcTest application.
LabstorIpcTest is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class HermesUnitTests(Application):
    """
    This class provides methods to launch the LabstorIpcTest application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'TEST_CASE',
                'msg': 'Destroy previous configuration and rebuild',
                'type': str,
                'default': 'TestIpc'
            },
            {
                'name': 'nprocs',
                'msg': 'The number of processes to spawn',
                'type': int,
                'default': None,
            },
            {
                'name': 'ppn',
                'msg': 'The number of processes per node',
                'type': int,
                'default': 1,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        nprocs = self.config['nprocs']
        if self.config['nprocs'] is None:
            nprocs = len(self.jarvis.hostfile)
        test_ipc_execs = ['TestIpc', 'TestAsyncIpc', 'TestIO', 'TestIpcMultithread4', 'TestIpcMultithread8']
        test_config_execs = [
            'TestHermesPaths'
        ]
        test_hermes_execs = [
            'TestHermesPut1n', 'TestHermesPut', 'TestHermesSerializedPutGet',
            'TestHermesAsyncPut', 'TestHermesAsyncPutLocalFlush', 'TestHermesPutGet',
            'TestHermesPartialPutGet', 'TestHermesBlobDestroy',
            'TestHermesBucketDestroy', 'TestHermesReorganizeBlob',
            'TestHermesBucketAppend', 'TestHermesBucketAppend1n',
            'TestHermesConnect', 'TestHermesGetContainedBlobIds',
            'TestHermesMultiGetBucket', 'TestHermesDataStager',
            'TestHermesDataOp', 'TestHermesCollectMetadata', 'TestHermesDataPlacement',
            'TestHermesDataPlacementFancy', 'TestHermesCompress', 'hermes'
        ]
        test_latency_execs = ['TestRoundTripLatency',
                              'TestHshmQueueAllocateEmplacePop',
                              'TestWorkerLatency']
        test_ping_pong = ['TestPingPong']
        print(self.config['TEST_CASE'])
        if self.config['TEST_CASE'] in test_config_execs:
            Exec(f'test_config_exec {self.config["TEST_CASE"]}',
                 LocalExecInfo(hostfile=self.jarvis.hostfile,
                             nprocs=nprocs,
                             ppn=self.config['ppn'],
                             env=self.env,
                             do_dbg=self.config['do_dbg'],
                             dbg_port=self.config['dbg_port']))
        elif self.config['TEST_CASE'] in test_ipc_execs:
            Exec(f'test_ipc_exec {self.config["TEST_CASE"]}',
                 MpiExecInfo(hostfile=self.jarvis.hostfile,
                             nprocs=nprocs,
                             ppn=self.config['ppn'],
                             env=self.env,
                             do_dbg=self.config['do_dbg'],
                             dbg_port=self.config['dbg_port']))
        elif self.config['TEST_CASE'] in test_hermes_execs:
            case = self.config['TEST_CASE']
            if self.config['TEST_CASE'] == 'hermes':
                case = ''
            Exec(f'test_hermes_exec {case}',
                 MpiExecInfo(hostfile=self.jarvis.hostfile,
                             nprocs=nprocs,
                             ppn=self.config['ppn'],
                             env=self.env,
                             do_dbg=self.config['do_dbg'],
                             dbg_port=self.config['dbg_port']))
        elif self.config['TEST_CASE'] in test_latency_execs:
            Exec(f'test_performance_exec {self.config["TEST_CASE"]}',
                 LocalExecInfo(env=self.env,
                             do_dbg=self.config['do_dbg'],
                             dbg_port=self.config['dbg_port']))
        elif self.config['TEST_CASE'] in test_ping_pong:
            Exec(f'test_ping_pong_exec',
                MpiExecInfo(nprocs=2,
                            ppn=2,
                            env=self.env,
                             do_dbg=self.config['do_dbg'],
                             dbg_port=self.config['dbg_port']))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/hermes_vfd_tests/pkg.py`

```python
"""
This module provides classes and methods to launch the HermesVfdTests application.
HermesVfdTests is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class HermesVfdTests(Application):
    """
    This class provides methods to launch the HermesVfdTests application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'test_file',
                'choices': ['vfd_basic', 'vfd_py_test'],
                'msg': '',
                'type': str,
                'default': None,
            },
            {
                'name': 'test_case',
                'msg': 'Specify exact test case to run',
                'type': str,
                'default': None,
            },
            {
                'name': 'hermes',
                'msg': 'Whether or not to use Hermes',
                'type': bool,
                'default': False,
            },
            {
                'name': 'mode',
                'msg': 'The mode of the test to run',
                'choices': [None, 'default', 'scratch'],
                'type': str,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        Mkdir("/tmp/test_hermes")
        test_fun = getattr(self, f'test_{self.config["test_file"]}')
        test_fun()

    def test_vfd_basic(self):
        cmd = 'vfd_adapter_test'
        if self.config['hermes']:
            cmd = f'hermes_{cmd}'
        if self.config['test_case']:
            cmd = (f'{cmd} {self.config["test_case"]}')
        else:
            vfd_cmd = [cmd]
            if self.config['mode'] == 'scratch':
                vfd_cmd.append('~[mode=scratch]')
            vfd_cmd.append('--reporter compact -d yes')
            cmd = ' '.join(vfd_cmd)
        node = Exec(cmd,
                    LocalExecInfo(env=self.mod_env,
                                  do_dbg=self.config['do_dbg'],
                                  dbg_port=self.config['dbg_port'],
                                  pipe_stdout=self.config['stdout'],
                                  pipe_stderr=self.config['stderr']))
        return node.exit_code

    def test_vfd_py_test(self):
        cmd = f'python3 {self.env["HERMES_ROOT"]}/bin/hermes_vfd_py_test.py'
        node = Exec(cmd,
                    LocalExecInfo(env=self.mod_env,
                                  do_dbg=self.config['do_dbg'],
                                  dbg_port=self.config['dbg_port'],
                                  pipe_stdout=self.config['stdout'],
                                  pipe_stderr=self.config['stderr']))
        return node.exit_code

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/hermes_viz/pkg.py`

```python
"""
This module provides classes and methods to launch the Ior application.
Ior is ....
"""
from jarvis_cd.basic.pkg import Service
from jarvis_util import *


class HermesViz(Service):
    """
    This class provides methods to launch the Ior application.
    """
    def _init(self):
        """
        Initialize paths
        """
        self.daemon_pkg = None

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'port',
                'msg': 'Por the server will listen at',
                'type': int,
                'default': 5000,
            },
            {
                'name': 'pooling',
                'msg': 'Time in seconds (accepts floats) that server will sleep between pooling hermes',
                'type': float,
                'default': 0.5,
            },
            {
                'name': 'real',
                'msg': 'Generate data or capture from hermes',
                'type': bool,
                'default': True,
            },
            {
                'name': 'hostfile',
                'msg': 'hostfile with nodes under which we are running',
                'type': str,
                'default': "~/jarvis_node_normal",
            },
            {
                'name': 'db_path',
                'msg': 'path to the database to gather the metadata',
                'type': str
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        print("Starting the Hermes visualizer flask server?")
        if self.config["db_path"]:
            cmd = f'hermes_viz.py --port {self.config["port"]} --sleep_time {self.config["pooling"]} ' \
                  f'--real {self.config["real"]} --hostfile {self.config["hostfile"]} ' \
                  f'--db_path {self.config["db_path"]}'
        else:
            cmd = f'hermes_viz.py --port {self.config["port"]} --sleep_time {self.config["pooling"]} ' \
                  f'--real {self.config["real"]} --hostfile {self.config["hostfile"]} '
        self.daemon_pkg = Exec(cmd, LocalExecInfo(env=self.env, exec_async=True))
        time.sleep(self.config['sleep'])
        print('Finished sleeping for the visualizer')

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        print('Stopping hermes_viz')
        Kill('hermes_viz.py',
             LocalExecInfo(env=self.env),
             partial=True)
        if self.daemon_pkg is not None:
            self.daemon_pkg.wait()
        print('hermes_viz stoppped')

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass

    def status(self):
        """
        Check whether or not an application is running. E.g., are OrangeFS
        servers running?

        :return: True or false
        """
        return True
```

### `builtin/builtin/ior/pkg.py`

```python
"""
This module provides classes and methods to launch the Ior application.
Ior is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *
import os


class Ior(Application):
    """
    This class provides methods to launch the Ior application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'write',
                'msg': 'Perform a write workload',
                'type': bool,
                'default': True,
                'choices': [],
                'args': [],
            },
            {
                'name': 'read',
                'msg': 'Perform a read workload',
                'type': bool,
                'default': False,
            },
            {
                'name': 'xfer',
                'msg': 'The size of data transfer',
                'type': str,
                'default': '1m',
            },
            {
                'name': 'block',
                'msg': 'Amount of data to generate per-process',
                'type': str,
                'default': '32m',
            },
            {
                'name': 'api',
                'msg': 'The I/O api to use',
                'type': str,
                'choices': ['posix', 'mpiio', 'hdf5'],
                'default': 'posix',
            },
            {
                'name': 'fpp',
                'msg': 'Use file-per-process',
                'type': bool,
                'default': False,
            },
            {
                'name': 'reps',
                'msg': 'Number of times to repeat',
                'type': int,
                'default': 1,
            },
            {
                'name': 'nprocs',
                'msg': 'Number of processes',
                'type': int,
                'default': 1,
            },
            {
                'name': 'ppn',
                'msg': 'The number of processes per node',
                'type': int,
                'default': 16,
            },
            {
                'name': 'out',
                'msg': 'Path to the output file',
                'type': str,
                'default': '/tmp/ior.bin',
            },
            {
                'name': 'log',
                'msg': 'Path to IOR output log',
                'type': str,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        self.config['api'] = self.config['api'].upper()

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        cmd = [
            'ior',
            '-k',
            f'-b {self.config["block"]}',
            f'-t {self.config["xfer"]}',
            f'-a {self.config["api"]}',
            f'-o {self.config["out"]}',
        ]
        out = os.path.expandvars(self.config['out'])
        if self.config['write']:
            cmd.append('-w')
        if self.config['read']:
            cmd.append('-r')
        if self.config['fpp']:
            cmd.append('-F')
        if self.config['reps'] > 1:
            cmd.append(f'-i {self.config["reps"]}')
        if '.' in os.path.basename(out):
            os.makedirs(str(pathlib.Path(out).parent),
                        exist_ok=True)
        else:
            os.makedirs(out, exist_ok=True)
        # pipe_stdout=self.config['log']
        Exec('which mpiexec',
             LocalExecInfo(env=self.mod_env))
        Exec(' '.join(cmd),
             MpiExecInfo(env=self.mod_env,
                         hostfile=self.jarvis.hostfile,
                         nprocs=self.config['nprocs'],
                         ppn=self.config['ppn'],
                         do_dbg=self.config['do_dbg'],
                         dbg_port=self.config['dbg_port']))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        Rm(self.config['out'] + '*',
           PsshExecInfo(env=self.env,
                        hostfile=self.jarvis.hostfile))

    def _get_stat(self, stat_dict):
        """
        Get statistics from the application.

        :param stat_dict: A dictionary of statistics.
        :return: None
        """
        stat_dict[f'{self.pkg_id}.runtime'] = self.start_time
```

### `builtin/builtin/my_shell/pkg.py`

```python
"""
This module provides classes and methods to launch the MyShell application.
MyShell is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class MyShell(Application):
    """
    This class provides methods to launch the MyShell application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        
        return [
            {
                'name': 'script',  # The name of the parameter
                'msg': 'The path of shell script to execute.',  # Describe this parameter
                'type': str,  # What is the parameter type?
                'default': None,  # What is the default value if not required?
            },
        ]

    def configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        self.update_config(kwargs, rebuild=False)
        self.config['script'] = self.config['script']

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        cmd = [
            'bash',
        ]
        if self.config['script']:
            cmd.append(self.config['script'])
        # pipe_stdout=self.config['log']
        Exec(' '.join(cmd))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/my_shell/test_scirpt.sh`

```bash
echo hLLO
ps aux | grep python3
```

### `builtin/builtin/nyx_lya/pkg.py`

```python
"""
This module provides classes and methods to launch the NyxLya application.
NyxLya is ....
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class NyxLya(Application):
    """
    This class provides methods to launch the NyxLya application.
    """
    def _init(self):
        """
        Initialize paths
        """
        self.inputs_path = f'{self.pkg_dir}/config/inputs'
        self.nyx_lya_path = None

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'nprocs',
                'msg': 'Number of processes to spawn',
                'type': int,
                'default': 1,
            },
            {
                'name': 'ppn',
                'msg': 'Processes per pkg',
                'type': int,
                'default': 1,
            },
            {
                'name': 'nyx_install_path',
                'msg': 'Absolute path to Nyx installation',
                'type': str,
                'default': None,
            },
            {
                'name': 'initial_z',
                'msg': 'final value of z, z corresponds to a time stemp (e.g., 190.0)',
                'type': float,
                'default': 159.0,
            },
            {
                'name': 'final_z',
                'msg': 'final value of z, z corresponds to a time stemp (e.g., 180.0). final_z < initial_z',
                'type': float,
                'default': 2.0, 
            },
            {
                'name': 'plot_z_values',
                'msg': 'z values to save the plot files(e.g., "188.0 186.0 184.0 182.0")',
                'type': str,
                'default': "7.0 6.0 5.0 4.0 3.0 2.0",
            },
            {
                'name': 'particle_file',
                'msg': 'Absolute path to the binary particle fileoutput(e.g., 64sssss_20mpc.nyx)',
                'type': str,
                'default': '64sssss_20mpc.nyx',
            },
            {
                'name': 'output',
                'msg': 'Absolute path to the output directory',
                'type': str,
                'default': None,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        if self.config['nyx_install_path'] is None:
            print("Error: please provide the path to Nyx installation....")
            exit(1)
        else:
            self.nyx_lya_path = f"{self.config['nyx_install_path']}/LyA"

        if self.config['particle_file'] == "64sssss_20mpc.nyx":
            self.config['particle_file'] = f'{self.nyx_lya_path}/64sssss_20mpc.nyx'
        
        if self.config['output'] is None:
            self.config['output'] = f'{self.nyx_lya_path}/outputs'
            Mkdir(self.config['output'], PsshExecInfo(hostfile=self.jarvis.hostfile,
                                          env=self.env))

        # copy a template inputs file from NYX installation path to the pkg directory
        self.copy_template_file(f'{self.nyx_lya_path}/inputs', self.inputs_path)
        # modify the inputs file based on user's input
        self._configure_nyx()

    def _configure_nyx(self):

        prefix_mapping = {
            'nyx.write_hdf5': f"",
            'nyx.initial_z': f"nyx.initial_z = {self.config['initial_z']}\n",
            'nyx.final_z': f"nyx.final_z = {self.config['final_z']}\n",
            'amr.plot_file': f"amr.plot_file = {self.config['output']}/plt\n",
            'nyx.plot_z_values': f"nyx.plot_z_values = {self.config['plot_z_values']}\n",
            'nyx.binary_particle_file': f"nyx.binary_particle_file = {self.config['particle_file']}\n",
            'amr.check_file': f"amr.check_file = {self.config['output']}/chk\n",
            'amr.derive_plot_vars': lambda line: f"#{line}",
            'amr.data_log': f"amr.data_log = {self.config['output']}/runlog\n",
            'amr.grid_log': f"amr.grid_log = {self.config['output']}/grdlog\n",
        }

        lines = []
        lines.append("nyx.write_hdf5 = 1\n")
        with open(self.inputs_path, 'r') as file:
            for line in file:
                line_stripped = line.strip()
                action = prefix_mapping.get(line_stripped.split(' ')[0], None)
                
                if action == None:
                    lines.append(line)
                elif callable(action):
                    lines.append(action(line))
                else:
                    lines.append(action)
        
        # rewrite the file
        with open(self.inputs_path, 'w') as file:
            file.writelines(lines)

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        # since "self.nyx_lya_path" is always set to be none in _init(), we need to rest it here
        self.nyx_lya_path = f"{self.config['nyx_install_path']}/LyA"
        Exec(f'{self.nyx_lya_path}/nyx_LyA {self.inputs_path}',
             MpiExecInfo(nprocs=self.config['nprocs'],
                         ppn=self.config['ppn'],
                         hostfile=self.jarvis.hostfile,
                         env=self.env))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        output_dir = self.config['output'] + "*"
        print(f'Removing {output_dir}')
        Rm(output_dir)
```

### `builtin/builtin/orangefs/__init__.py`

```python

```

### `builtin/builtin/orangefs/ares.py`

```python
from jarvis_util import *
from .custom_kern import OrangefsCustomKern


class OrangefsAres:
    def ares_stop(self):
        cmd = [
            f'{self.ofs_path}/sbin/ares-orangefs-terminate',
            self.config['pfs_conf'],
            self.config['server_hosts_path'],
            self.config['client_hosts_path'],
            self.config['mount'],
        ]
        cmd = ' '.join(cmd)
        print(cmd)
        Exec(cmd, LocalExecInfo(env=self.env))
```

### `builtin/builtin/orangefs/custom_kern.py`

```python
from jarvis_util import *


class OrangefsCustomKern:
    def custom_start(self):
        # start pfs servers
        print("Starting the PFS servers")
        for host in self.server_hosts.list():
            host_ip = host.hosts[0]
            server_start_cmds = [
                # f'pvfs2-server -f -a {host_ip}  {self.config["pfs_conf"]}',
                f'pvfs2-server -a {host_ip} {self.config["pfs_conf"]}'
            ]
            print(server_start_cmds)
            print(f"PVFS2TAB: {self.env['PVFS2TAB_FILE']}")
            Exec(server_start_cmds,
                 SshExecInfo(hostfile=Hostfile(all_hosts=[host]),
                             env=self.env))
        self.status()

        # insert OFS kernel module
        print("Inserting OrangeFS kernel module")
        Exec('modprobe orangefs', PsshExecInfo(sudo=True,
                                               sudoenv=self.config['sudoenv'],
                                               hosts=self.client_hosts,
                                               env=self.env))

        # PFS client thing
        print("Starting the OrangeFS clients")
        start_client_cmd = f'{self.ofs_path}/sbin/pvfs2-client -p {self.ofs_path}/sbin/pvfs2-client-core -L {self.config["client_log"]}'
        Exec(start_client_cmd,
             PsshExecInfo(hostfile=self.client_hosts,
                          env=self.env,
                          sudo=True,
                          sudoenv=self.config['sudoenv']))

        # start pfs client
        print("Mounting the OrangeFS clients")
        mdm_ip = self.md_hosts.list()[0].hosts[0]
        mount_client = 'mount -t pvfs2 {protocol}://{ip}:{port}/{name} {mount_point}'.format(
            protocol=self.config['protocol'],
            port=self.config['port'],
            ip=mdm_ip,
            name=self.config['name'],
            mount_point=self.config['mount'])
        Exec(mount_client,
             PsshExecInfo(hostfile=self.client_hosts,
                          env=self.env,
                          sudo=True,
                          sudoenv=self.config['sudoenv']))

    def custom_stop(self):
        Exec(f'umount -t pvfs2 {self.config["mount"]}',
             PsshExecInfo(hosts=self.client_hosts,
                          env=self.env,
                          sudo=True,
                          sudoenv=self.config['sudoenv']))
        self.log(f"Unmounting {self.config['mount']} on each client", Color.YELLOW)
        Kill('.*pvfs2-client.*', PsshExecInfo(hosts=self.client_hosts,
                                env=self.env))
        Kill('pvfs2-server',
             PsshExecInfo(hosts=self.server_hosts,
                          env=self.env))
        Exec('pgrep -la pvfs2-server',
             PsshExecInfo(hosts=self.client_hosts,
                          env=self.env))
```

### `builtin/builtin/orangefs/fuse.py`

```python
from jarvis_cd.basic.pkg import Service
from jarvis_util import *
import os


class OrangefsFuse:
    def fuse_start(self):
        # start pfs servers 
        for host in self.server_hosts:
            server_start_cmds = [
                # f"pvfs2-server {self.config['pfs_conf']} -f -a {host}",
                f"pvfs2-server {self.config['pfs_conf']} -a {host}"
            ]
            Exec(server_start_cmds,
                 SshExecInfo(hostfile=Hostfile(all_hosts=[host]),
                             env=self.env))
        self.status()

        # start pfs client
        md_list = self.md_hosts.list()
        for i,client in self.client_hosts.enumerate():
            mdm_ip = md_list[i % len(self.md_hosts)].hosts_ip[0]
            start_client_cmds = [
                "pvfs2fuse -o fs_spec={protocol}://{ip}:{port}/{name} {mount_point}".format(
                    protocol=self.config['protocol'],
                    port=self.config['port'],
                    ip=mdm_ip,
                    name=self.config['name'],
                    mount_point=self.config['mount'])
            ]
            Exec(start_client_cmds,
                 SshExecInfo(hostfile=client,
                             env=self.env))

    def fuse_stop(self):
        cmds = [
            f"fusermount -u {self.config['mount']}"
        ]
        Exec(cmds, PsshExecInfo(hosts=self.client_hosts,
                                env=self.env))
        self.log(f"Unmounting {self.config['mount']} on each client", Color.YELLOW)

        Kill('.*pvfs2-client.*', PsshExecInfo(hosts=self.client_hosts,
                                        env=self.env))
        Kill('pvfs2-server',
             PsshExecInfo(hosts=self.server_hosts,
                          env=self.env))
        Exec("pgrep -la pvfs2-server", PsshExecInfo(hosts=self.client_hosts,
                                env=self.env))
```

### `builtin/builtin/orangefs/pkg.py`

```python
from jarvis_cd.basic.pkg import Service
from jarvis_util import *
from .custom_kern import OrangefsCustomKern
from .ares import OrangefsAres
from .fuse import OrangefsFuse
import os
import time


class Orangefs(Service, OrangefsCustomKern, OrangefsAres, OrangefsFuse):
    def _init(self):
        """
        Initialize paths
        """

    def _configure_menu(self):
        return [
            {
                'name': 'port',
                'msg': 'The port to listen for data on',
                'type': int,
                'default': 3334
            },
            {
                'name': 'ofs_data_dir',
                'msg': 'The mount point to place all OFS data. Must not be a shared system (e.g., another PFS).',
                'type': str,
                'default': None,
            },
            {
                'name': 'stripe_size',
                'msg': 'The stripe size',
                'type': int,
                'default': 65536,
            },
            {
                'name': 'stripe_dist',
                'msg': 'The striping distribution algorithm',
                'type': str,
                'default': 'simple_stripe',
            },
            {
                'name': 'protocol',
                'msg': 'The network protocol (tcp/ib)',
                'type': str,
                'default': 'tcp',
                'choices': ['tcp', 'ib']
            },
            {
                'name': 'mount',
                'msg': 'Where to mount orangefs clients',
                'type': str,
                'default': None,
            },
            {
                'name': 'name',
                'msg': 'The name of the orangefs installation',
                'type': str,
                'default': 'orangefs',
            },
            {
                'name': 'sudoenv',
                'msg': 'Whether environment forwarding is supported for sudo',
                'type': bool,
                'default': True,
            },
            {
                'name': 'ofs_mode',
                'msg': 'Whether we are using the orangefs on Ares',
                'type': bool,
                'choices': ['fuse', 'ares', 'kern'],
                'default': 'ares',
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        rg = self.jarvis.resource_graph
        if self.config['ofs_mode'] != 'kern':
            self.config['sudoenv'] = False

        # Configure and save hosts
        self.client_hosts = self.jarvis.hostfile
        self.server_hosts = self.jarvis.hostfile
        self.md_hosts = self.jarvis.hostfile
        self.config['client_host_set'] = self.client_hosts.hosts
        self.config['server_host_set'] = self.server_hosts.hosts
        self.config['md_host_set'] = self.md_hosts.hosts
        self.config['client_hosts_path'] = f'{self.private_dir}/client_hosts'
        self.config['server_hosts_path'] = f'{self.private_dir}/server_hosts'
        self.config['metadata_hosts_path'] = f'{self.private_dir}/metadata_hosts'
        self.client_hosts.save(self.config['client_hosts_path'])
        self.server_hosts.save(self.config['server_hosts_path'])
        self.md_hosts.save(self.config['metadata_hosts_path'])
        Pscp([self.config['client_hosts_path'],
              self.config['server_hosts_path'],
              self.config['metadata_hosts_path']],
             PsshExecInfo(hosts=self.jarvis.hostfile, env=self.env))
        self.log('Distributed client, server, and metadata hostfiles', Color.YELLOW)

        # Locate storage hardware
        storage_dir = self.config['ofs_data_dir']

        # Define paths
        self.config['pfs_conf'] = f'{self.private_dir}/orangefs.xml'
        self.config['pvfs2tab'] = f'{self.private_dir}/pvfs2tab'
        if self.config['mount'] is None:
            self.config['mount'] = f'{self.private_dir}/client'
        self.config['storage'] = f'{storage_dir}/orangefs_storage'
        self.config['metadata'] = f'{storage_dir}/orangefs_metadata'
        self.config['log'] = f'{self.private_dir}/orangefs_server.log'
        self.config['client_log'] = f'{self.private_dir}/orangefs_client.log'

        # generate PFS Gen config
        if self.config['protocol'] == 'tcp':
            proto_cmd = f'--tcpport {self.config["port"]}'
        elif self.config['protocol'] == 'ib':
            proto_cmd = f'--ibport {self.config["port"]}'
        else:
            raise Exception("Protocol must be either tcp or ib")
        pvfs_gen_cmd = [
            'pvfs2-genconfig',
            '--quiet',
            f'--protocol {self.config["protocol"]}',
            proto_cmd,
            f'--dist-name {self.config["stripe_dist"]}',
            f'--dist-params \"strip_size: {self.config["stripe_size"]}\"',
            f'--ioservers {self.server_hosts.host_str(sep=",")}',
            f'--metaservers {self.md_hosts.host_str(sep=",")}',
            f'--storage {self.config["storage"]}',
            f'--metadata {self.config["metadata"]}',
            f'--logfile {self.config["log"]}',
            f'--fsname {self.config["name"]}',
            self.config['pfs_conf']
        ]
        pvfs_gen_cmd = " ".join(pvfs_gen_cmd)
        Exec(pvfs_gen_cmd, LocalExecInfo(env=self.env))
        Pscp(self.config['pfs_conf'],
             PsshExecInfo(hosts=self.jarvis.hostfile, env=self.env))
        self.log(f"Generated pvfs2 config: {self.config['pfs_conf']}", Color.YELLOW)

        # Create storage directories
        Mkdir(self.config['mount'], PsshExecInfo(hosts=self.client_hosts,
                                                 env=self.env))
        Mkdir(self.config['storage'], PsshExecInfo(hosts=self.server_hosts,
                                                   env=self.env))
        Mkdir(self.config['metadata'], PsshExecInfo(hosts=self.md_hosts,
                                                    env=self.env))
        self.log(f"Create mount, metadata and storage directories", Color.YELLOW)
        self.log(f"Mount at: {self.config['mount']}", Color.YELLOW)

        # Set pvfstab on clients
        mdm_ip = self.md_hosts.list()[0].hosts[0]
        with open(self.config['pvfs2tab'], 'w', encoding='utf-8') as fp:
            fp.write(
                '{protocol}://{ip}:{port}/{name} {mount_point} pvfs2 defaults,auto 0 0\n'.format(
                    protocol=self.config['protocol'],
                    port=self.config['port'],
                    ip=mdm_ip,
                    name=self.config['name'],
                    mount_point=self.config['mount'],
                    client_pvfs2tab=self.config['pvfs2tab']))
        Pscp(self.config['pvfs2tab'],
             PsshExecInfo(hosts=self.jarvis.hostfile,
                          env=self.env))
        self.env['PVFS2TAB_FILE'] = self.config['pvfs2tab']
        self.log(f"Create PVFS2TAB_FILE: {self.config['pvfs2tab']}", Color.YELLOW)

        for host in self.server_hosts.list():
            host_ip = host.hosts[0]
            server_start_cmds = [
                f'pvfs2-server -f -a {host_ip}  {self.config["pfs_conf"]}'
            ]
            self.log(server_start_cmds, Color.YELLOW)
            Exec(server_start_cmds,
                 SshExecInfo(hostfile=host,
                             env=self.env))

    def _load_config(self):
        if 'sudoenv' not in self.config:
            self.config['sudoenv'] = True
        self.client_hosts = Hostfile(all_hosts=self.config['client_host_set'])
        self.server_hosts = Hostfile(all_hosts=self.config['server_host_set'])
        self.md_hosts = Hostfile(all_hosts=self.config['md_host_set'])
        self.ofs_path = self.env['ORANGEFS_PATH']

    def start(self):
        self._load_config() 
        if self.config['ofs_mode'] == 'fuse':
            self.fuse_start()
        else:
            self.custom_start()

    def stop(self):
        self._load_config()
        if self.config['ofs_mode'] == 'ares':
            self.ares_stop()
        elif self.config['ofs_mode'] == 'fuse':
            self.fuse_stop()
        else:
            self.custom_stop()

    def clean(self):
        self._load_config()
        Rm([self.config['mount'], self.config['client_log']],
           PsshExecInfo(hosts=self.client_hosts,
                        env=self.env))
        Rm([self.config['storage'], self.config['log']],
           PsshExecInfo(hosts=self.server_hosts,
                        env=self.env))
        Rm(self.config['metadata'],
           PsshExecInfo(hosts=self.md_hosts,
                        env=self.env))

    def status(self):
        self._load_config()
        Exec('mount | grep pvfs',
             PsshExecInfo(hosts=self.server_hosts,
                          env=self.env))
        verify_server_cmd = [
            f'pvfs2-ping -m {self.config["mount"]} | grep \"appears to be correctly configured\"'
        ]
        Exec(verify_server_cmd,
             PsshExecInfo(hosts=self.client_hosts,
                          env=self.env))
        return True
```

### `builtin/builtin/pyflextrkr/example_config/run_mcs_tb_summer_sam_template.yml`

```yaml
---
# DYAMOND MCS tracking configuration file
# Tracking uses collocated Tb + Precipitation

# Processing steps:
run_preprocess : False
run_idfeature : True
run_tracksingle : True
run_gettracks : True
run_trackstats : True
run_identifymcs : True
run_matchpf : True
run_robustmcs : True
run_mapfeature : True
run_speed : True

# Parallel processing set up
# run_parallel: 1 (local cluster), 2 (Dask MPI)
run_parallel: 1
nprocesses : 12  # Number of processors to use if run_parallel=1
# dask_tmp_dir: '/tmp'  # Dask temporary directory if run_parallel=1
dask_tmp_dir: '/tmp/pyflextrkr_test'  # Dask temporary directory if run_parallel=1
timeout: 360  # [seconds] Dask timeout limit

# Start/end date and time
startdate: '20160801.0000'
# enddate: '20160801.0500' # 6 files ~204MB , tested smallest for 9 stages
# enddate: '20160801.1100' # 12 files ~ 408MB
enddate: '20160801.2300' # 24 files ~816MB
# enddate: '20160802.1100' # 36 files ~ 884MB
# enddate: '20160802.2300' # 48 files ~ 1.6GB
# enddate: '20160803.2300' # 72 files ~ 2.4GB
# enddate: '20160804.2300' # 96 files ~ 3GB
# enddate: '20160806.2300' # 142 files ~ 4.7GB
# enddate: '20160809.2300' # 216 files ~ 7.2GB
# enddate: '20160810.2300' # 240 files ~ 8GB
# enddate: '20160910.0000' # 960 files ~ 32GB

# Specify tracking input data date/time string format
# This is the preprocessed file that contains Tb & rainrate
# E.g., databasename20181101.011503.nc --> yyyymodd.hhmmss
# E.g., databasename2018-11-01_01:15:00 --> yyyy-mo-dd_hh:mm:ss
time_format: 'yyyymoddhh'
databasename:  'pr_rlut_mean_sam_'

# Input files directory
clouddata_path: 'INPUT_DIR/'
# Working directory for the tracking data
root_path: 'TRACK_DIR/'
# Working sub-directory names
tracking_path_name: 'tracking'
stats_path_name: 'stats'
pixel_path_name: 'mcstracking'

# Land mask file
landmask_filename: 'INPUT_DIR/IMERG_landmask_180W-180E_60S-60N.nc'
# landmask_filename: 'INPUT_DIR/IMERG_landmask_0-360_60S-60N.nc'
landmask_varname: 'landseamask'
landmask_x_dimname: 'lon'
landmask_y_dimname: 'lat'
landmask_x_coordname: 'lon'
landmask_y_coordname: 'lat'
landfrac_thresh: [0, 90]  # Define the range of fraction for land (depends on what value is land the landmask file)

# Input dataset structure
pixel_radius:  10.0  # [km] Spatial resolution of the input data
datatimeresolution: 1.0  # [hour] Temporal resolution of the input data
# Variable names in the input data
olr2tb: True
olr_varname: 'LWNTA'
pcp_varname: 'Precac'
clouddatasource: 'model'
time_dimname: 'time'
x_dimname: 'lon'
y_dimname: 'lat'
time_coordname: 'time'
x_coordname: 'lon'
y_coordname: 'lat'

# Specify types of feature being tracked
# This adds additional feature-specific statistics to be computed
feature_type: 'tb_pf'

# Cloud identification parameters
mincoldcorepix:  4  # Minimum number of pixels for the cold core
smoothwindowdimensions:  10  # Dimension of the Box2DKernel filter on Tb.

# # set geolimits change to smaller region to reduce computation time
# medfiltsize: 5      # Window size to perform medfilt2d to fill missing Tb pixels, must be an odd number
# geolimits: [-60, -360, 60, 360] # [lat_min, lon_min, lat_max, lon_max] 4-element array to subset domain boundaries # RG1: global
# geolimits: [-15, 60, 30, 180] # RG2: medium size Pacific Ocean region
geloimits: [-15, 90, 15, 150] # RG3: smallest size Souch China Sea region


area_thresh:  800  # [km^2] Minimum area to define a cloud
miss_thresh:  0.4  # Missing data fraction threshold. If missing data exceeds this, the time frame will be omitted.
cloudtb_core:  225.0  # [K]
cloudtb_cold:  241.0  # [K]
cloudtb_warm:  261.0  # [K]
cloudtb_cloud:  261.0  # [K]
absolutetb_threshs: [160, 330]  # K [min, max] absolute Tb range allowed.
warmanvilexpansion:  0  # Not working yet, set this to 0 for now
cloudidmethod: 'label_grow'
# Specific parameters to link cloud objects using PF
linkpf:  1  # Set to 1 to turn on linkpf option; default: 0
pf_smooth_window:  5  # Smoothing window for identifying PF
pf_dbz_thresh:  3  # [dBZ] for reflectivity, or [mm/h] for rainrate
pf_link_area_thresh:  648.0  # [km^2]

# Tracking parameters
othresh: 0.5  # overlap fraction threshold. Clouds that overlap more than this between times are tracked.
timegap: 3.1  # [hour] If missing data duration longer than this, tracking restarts
nmaxlinks: 50  # Maximum number of clouds that any single cloud can be linked to
maxnclouds:  3000  # Maximum number of clouds in one snapshot
duration_range: [2, 400] # A vector [minlength,maxlength] to specify the duration range for the tracks
# Flag to remove short-lived tracks [< min(duration_range)] that are not mergers/splits with other tracks
# 0:keep all tracks; 1:remove short tracks
remove_shorttracks: 1
# Set this flag to 1 to write a dense (2D) trackstats netCDF file
# Note that for datasets with lots of tracks, the memory consumption could be large
trackstats_dense_netcdf: 1
# Minimum time difference threshold to match track stats with cloudid files
match_pixel_dt_thresh: 60.0  # seconds

# MCS Tb parameters
mcs_tb_area_thresh: 40000  # [km^2] Tb area threshold
mcs_tb_duration_thresh:  4  # [hour] Tb minimum length of a mcs
mcs_tb_split_duration:  12  # [hour] Tb tracks smaller or equal to this length will be included with the MCS splits from
mcs_tb_merge_duration:  12  # [hour] Tb tracks smaller or equal to this length will be included with the MCS merges into
mcs_tb_gap: 1  # [unitless] Allowable temporal gap in Tb data for MCS area threshold
# MCS PF parameters
mcs_pf_majoraxis_thresh:  100  # [km] MCS PF major axis length lower limit
max_pf_majoraxis_thresh:  1800  # [km] MCS PF major axis length upper limit
mcs_pf_durationthresh:  4  # [hour] PF minimum length of mcs
mcs_pf_majoraxis_for_lifetime:  20  # [km] Minimum PF size to count PF lifetime
mcs_pf_gap:  1  # [unitless] Allowable temporal gap in PF data for MCS characteristics

# Specify rain rate parameters
pf_rr_thres:  2.0  # [mm/hr] Rain rate threshold
nmaxpf: 3  # Maximum number of precipitation features that can be within a cloud feature
nmaxcore: 20  # Maximum number of convective cores that can be within a cloud feature
pcp_thresh:  1.0  # Pixels with hourly precipitation larger than this will be labeled with track number
heavy_rainrate_thresh:  10.0  # [mm/hr] Heavy rain rate threshold
mcs_min_rainvol_thresh: 20000   #  [km^2 mm/h] Min rain volumne threshold #TODO
mcs_volrain_duration_thresh: 1.0   # [hour] Min volume rain threshold #TODO


# Define tracked feature variable names
feature_varname: 'feature_number'
nfeature_varname: 'nfeatures'
featuresize_varname: 'npix_feature'

# Track statistics output file dimension names
tracks_dimname: 'tracks'
times_dimname: 'times'
pf_dimname: 'nmaxpf'
fillval: -9999
# MCS track stats file base names
mcstbstats_filebase: 'mcs_tracks_'
mcspfstats_filebase: 'mcs_tracks_pf_'
mcsrobust_filebase: 'mcs_tracks_robust_'
pixeltracking_filebase: 'mcstrack_'
mcsfinal_filebase: 'mcs_tracks_final_'

# Feature movement speed parameters
lag_for_speed: 1  # lag intervals between tracked features to calculate movement
track_number_for_speed: "pcptracknumber"
track_field_for_speed: 'precipitation'
min_size_thresh_for_speed: 20 # [km] Min PF major axis length to calculate movement #TODO
max_speed_thresh: 50  # [m/s] #TODO
```

### `builtin/builtin/pyflextrkr/example_config/run_mcs_tbpf_saag_summer_sam_template.yml`

```yaml
---
# DYAMOND MCS tracking configuration file
# Tracking uses collocated Tb + Precipitation

# Processing steps:
run_preprocess : False
run_idfeature : True
run_tracksingle : True
run_gettracks : True
run_trackstats : True
run_identifymcs : True
run_matchpf : True
run_robustmcs : True
run_mapfeature : True
run_speed : True

# Parallel processing set up
# run_parallel: 1 (local cluster), 2 (Dask MPI)
run_parallel: 1
nprocesses : 12  # Number of processors to use if run_parallel=1
# dask_tmp_dir: '/tmp'  # Dask temporary directory if run_parallel=1
dask_tmp_dir: '/tmp/pyflextrkr_test'  # Dask temporary directory if run_parallel=1
timeout: 360  # [seconds] Dask timeout limit

# Start/end date and time
startdate: '20160801.0000'
# enddate: '20160801.0500' # 6 files ~204MB , tested smallest for 9 stages
# enddate: '20160801.1100' # 12 files ~ 408MB
enddate: '20160801.2300' # 24 files ~816MB
# enddate: '20160802.1100' # 36 files ~ 884MB
# enddate: '20160802.2300' # 48 files ~ 1.6GB
# enddate: '20160803.2300' # 72 files ~ 2.4GB
# enddate: '20160804.2300' # 96 files ~ 3GB
# enddate: '20160806.2300' # 142 files ~ 4.7GB
# enddate: '20160809.2300' # 216 files ~ 7.2GB
# enddate: '20160810.2300' # 240 files ~ 8GB
# enddate: '20160910.0000' # 960 files ~ 32GB

# Specify tracking input data date/time string format
# This is the preprocessed file that contains Tb & rainrate
# E.g., databasename20181101.011503.nc --> yyyymodd.hhmmss
# E.g., databasename2018-11-01_01:15:00 --> yyyy-mo-dd_hh:mm:ss
time_format: 'yyyymoddhh'
databasename:  'pr_rlut_mean_sam_'

# Input files directory
clouddata_path: 'INPUT_DIR/'
# Working directory for the tracking data
root_path: 'OUTPUT_DIR/'
# Working sub-directory names
tracking_path_name: 'tracking'
stats_path_name: 'stats'
pixel_path_name: 'mcstracking'

# Land mask file
landmask_filename: 'INPUT_DIR/IMERG_landmask_180W-180E_60S-60N.nc'
# landmask_filename: 'INPUT_DIR/IMERG_landmask_0-360_60S-60N.nc'
landmask_varname: 'landseamask'
landmask_x_dimname: 'lon'
landmask_y_dimname: 'lat'
landmask_x_coordname: 'lon'
landmask_y_coordname: 'lat'
landfrac_thresh: [0, 90]  # Define the range of fraction for land (depends on what value is land the landmask file)

# Input dataset structure
pixel_radius:  10.0  # [km] Spatial resolution of the input data
datatimeresolution: 1.0  # [hour] Temporal resolution of the input data
# Variable names in the input data
olr2tb: True
olr_varname: 'LWNTA'
pcp_varname: 'Precac'
clouddatasource: 'model'
time_dimname: 'time'
x_dimname: 'lon'
y_dimname: 'lat'
time_coordname: 'time'
x_coordname: 'lon'
y_coordname: 'lat'

# Specify types of feature being tracked
# This adds additional feature-specific statistics to be computed
feature_type: 'tb_pf'

# Cloud identification parameters
mincoldcorepix:  4  # Minimum number of pixels for the cold core
smoothwindowdimensions:  10  # Dimension of the Box2DKernel filter on Tb.

# # set geolimits change to smaller region to reduce computation time
# medfiltsize: 5      # Window size to perform medfilt2d to fill missing Tb pixels, must be an odd number
# geolimits: [-60, -360, 60, 360] # [lat_min, lon_min, lat_max, lon_max] 4-element array to subset domain boundaries # RG1: global
# geolimits: [-15, 60, 30, 180] # RG2: medium size Pacific Ocean region
geloimits: [-15, 90, 15, 150] # RG3: smallest size Souch China Sea region


area_thresh:  800  # [km^2] Minimum area to define a cloud
miss_thresh:  0.4  # Missing data fraction threshold. If missing data exceeds this, the time frame will be omitted.
cloudtb_core:  225.0  # [K]
cloudtb_cold:  241.0  # [K]
cloudtb_warm:  261.0  # [K]
cloudtb_cloud:  261.0  # [K]
absolutetb_threshs: [160, 330]  # K [min, max] absolute Tb range allowed.
warmanvilexpansion:  0  # Not working yet, set this to 0 for now
cloudidmethod: 'label_grow'
# Specific parameters to link cloud objects using PF
linkpf:  1  # Set to 1 to turn on linkpf option; default: 0
pf_smooth_window:  5  # Smoothing window for identifying PF
pf_dbz_thresh:  3  # [dBZ] for reflectivity, or [mm/h] for rainrate
pf_link_area_thresh:  648.0  # [km^2]

# Tracking parameters
othresh: 0.5  # overlap fraction threshold. Clouds that overlap more than this between times are tracked.
timegap: 3.1  # [hour] If missing data duration longer than this, tracking restarts
nmaxlinks: 50  # Maximum number of clouds that any single cloud can be linked to
maxnclouds:  3000  # Maximum number of clouds in one snapshot
duration_range: [2, 400] # A vector [minlength,maxlength] to specify the duration range for the tracks
# Flag to remove short-lived tracks [< min(duration_range)] that are not mergers/splits with other tracks
# 0:keep all tracks; 1:remove short tracks
remove_shorttracks: 1
# Set this flag to 1 to write a dense (2D) trackstats netCDF file
# Note that for datasets with lots of tracks, the memory consumption could be large
trackstats_dense_netcdf: 1
# Minimum time difference threshold to match track stats with cloudid files
match_pixel_dt_thresh: 60.0  # seconds

# MCS Tb parameters
mcs_tb_area_thresh: 40000  # [km^2] Tb area threshold
mcs_tb_duration_thresh:  4  # [hour] Tb minimum length of a mcs
mcs_tb_split_duration:  12  # [hour] Tb tracks smaller or equal to this length will be included with the MCS splits from
mcs_tb_merge_duration:  12  # [hour] Tb tracks smaller or equal to this length will be included with the MCS merges into
mcs_tb_gap: 1  # [unitless] Allowable temporal gap in Tb data for MCS area threshold
# MCS PF parameters
mcs_pf_majoraxis_thresh:  100  # [km] MCS PF major axis length lower limit
max_pf_majoraxis_thresh:  1800  # [km] MCS PF major axis length upper limit
mcs_pf_durationthresh:  4  # [hour] PF minimum length of mcs
mcs_pf_majoraxis_for_lifetime:  20  # [km] Minimum PF size to count PF lifetime
mcs_pf_gap:  1  # [unitless] Allowable temporal gap in PF data for MCS characteristics

# Specify rain rate parameters
pf_rr_thres:  2.0  # [mm/hr] Rain rate threshold
nmaxpf: 3  # Maximum number of precipitation features that can be within a cloud feature
nmaxcore: 20  # Maximum number of convective cores that can be within a cloud feature
pcp_thresh:  1.0  # Pixels with hourly precipitation larger than this will be labeled with track number
heavy_rainrate_thresh:  10.0  # [mm/hr] Heavy rain rate threshold
mcs_min_rainvol_thresh: 20000   #  [km^2 mm/h] Min rain volumne threshold #TODO
mcs_volrain_duration_thresh: 1.0   # [hour] Min volume rain threshold #TODO


# # Candice Added
# mcs_lifecycle_thresh: 8  # MCS Tb duration [hour]

# # MCS PF parameter coefficients [intercept, slope]
# # These parameters are derived with pf_rr_thres:  2 mm/h
# # Lower percentile means lower thresholds
# coefs_pf_area:  [1962, 0]           # 1% [changed slope to 0: independent of lifetime]
# # coefs_pf_area:  [2119.02, 61.143]      # 3%
# # coefs_pf_area:  [2874.05, 89.825]  # 5% [recommended]
# # coefs_pf_area:  [4160.82, 93.077]      # 7%
# # coefs_pf_area:  [4988.15, 138.172]      # 10%

# coefs_pf_rr:  [2.72873, 0.0]            # 1%
# # coefs_pf_rr:  [2.81982, 0.0135463]      # 3%
# # coefs_pf_rr:  [3.01657, 0.0144461]  # 5% [recommended]
# # coefs_pf_rr:  [3.14895, 0.0150174]      # 7%
# # coefs_pf_rr:  [3.34859, 0.0172043]      # 10%

# coefs_pf_skew:  [0.036384, 0]            # 1%
# # coefs_pf_skew:  [0.072809, 0.0104444]     # 3%
# # coefs_pf_skew:  [0.194462, 0.0100072]  # 5% [recommended]
# # coefs_pf_skew:  [0.256639, 0.0106527]      # 7%
# # coefs_pf_skew:  [0.376142, 0.0095545]      # 10%

# coefs_pf_heavyratio:  [0.750260, 0.4133300]  # 5%
# # coefs_pf_heavyratio:  [3.419024, 0.4387090]  # 10% [recommended]
# # coefs_pf_heavyratio:  [4.753215, 0.4886454]  # 15%
# # coefs_pf_heavyratio:  [4.592209, 0.6107371]  # 20%
# # coefs_pf_heavyratio:  [8.389616, 0.5079337]  # 25%


# Define tracked feature variable names
feature_varname: 'feature_number'
nfeature_varname: 'nfeatures'
featuresize_varname: 'npix_feature'

# Track statistics output file dimension names
tracks_dimname: 'tracks'
times_dimname: 'times'
pf_dimname: 'nmaxpf'
fillval: -9999
# MCS track stats file base names
mcstbstats_filebase: 'mcs_tracks_'
mcspfstats_filebase: 'mcs_tracks_pf_'
mcsrobust_filebase: 'mcs_tracks_robust_'
pixeltracking_filebase: 'mcstrack_'
mcsfinal_filebase: 'mcs_tracks_final_'

# Feature movement speed parameters
lag_for_speed: 1  # lag intervals between tracked features to calculate movement
track_number_for_speed: "pcptracknumber"
track_field_for_speed: 'precipitation'
min_size_thresh_for_speed: 20 # [km] Min PF major axis length to calculate movement #TODO
max_speed_thresh: 50  # [m/s] #TODO
```

### `builtin/builtin/pyflextrkr/example_config/run_mcs_tbpfradar3d_wrf_template.yml`

```yaml
---
# MCS tracking configuration file
# Tracking uses collocated Tb + Radar3D

# Processing steps:
run_preprocess: False
run_idfeature : True
run_tracksingle : True
run_gettracks : True # not needed
run_trackstats : True
run_identifymcs : True # needed
run_matchpf : True # needed
run_robustmcs : True # needed
run_mapfeature : True # needed
run_speed : True # needed

# Parallel processing set up
# run_parallel: 1 (local cluster), 2 (Dask MPI)
run_parallel: 1
nprocesses : 8  # Number of processors to use if run_parallel=1
dask_tmp_dir: '/tmp/pyflextrkr_test'  # Dask temporary directory if run_parallel=1
timeout: 360  # [seconds] Dask timeout limit

# Start/end date and time
startdate: '20150506.0000'
enddate: '20150506.1600' # 17 files, each ~15-17 MB
# enddate: '20150506.0800' # 9 files, smallest possible to run all processing steps
# enddate: '20150510.0000' # 97 files, total 1.4GB

# Specify tracking input data date/time string format
# This is the preprocessed file that contains Tb & rainrate
# E.g., databasename20181101.011503.nc --> yyyymodd.hhmmss
# E.g., databasename2018-11-01_01:15:00 --> yyyy-mo-dd_hh:mm:ss
time_format: 'yyyy-mo-dd_hh:mm:ss'
regrid_basename: 'wrfout_rainrate_tb_zh_mh_'  # Note: include all strings before the time (including "_", ".")
databasename: 'wrfout_rainrate_tb_zh_mh_'
# Specify vertical height levels to interpolate reflectivity (unit: km ASL)
interp_levels: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 
  11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25]

# WRF raw data
wrfout_path: ''
wrfout_basename: 'wrfout_d01_'
# Tracking input files directory
clouddata_path: 'INPUT_DIR/'
# Working directory for the tracking data
root_path: 'TRACK_DIR/'
# Working sub-directory names
tracking_path_name: 'tracking'
stats_path_name: 'stats'
pixel_path_name: 'mcstracking'

# Land mask file
landmask_filename: 'INPUT_DIR/wrf_landmask.nc'
landmask_varname: 'LANDMASK'
landmask_x_dimname: 'west_east'
landmask_y_dimname: 'south_north'
landmask_x_coordname: 'XLONG'
landmask_y_coordname: 'XLAT'

# Input dataset structure
pixel_radius:  3.0  # [km] Spatial resolution of the input data
datatimeresolution: 1.0  # [hour] Temporal resolution of the input data
# Variable names in the input data
tb_varname:  'tb'
pcp_varname: 'rainrate'
reflectivity_varname: 'reflectivity'
meltlevel_varname: 'meltinglevelheight'
clouddatasource: 'model'
radardatasource: 'wrf'
pfdatasource:  'wrf'  # flag for landmask convention to calculate PF land fraction
time_dimname: 'time'
x_dimname: 'lon'
y_dimname: 'lat'
z_dimname: 'level'
x_coordname: 'lon2d'
y_coordname: 'lat2d'
z_coordname: 'level'

# Specify types of feature being tracked
# This adds additional feature-specific statistics to be computed
feature_type: 'tb_pf_radar3d'

# SL3D classification parameters
# Background box size to calculate peakedness [km]
background_Box:  12.
# Reflectivity threshold to fill low-level coverage gap [dBZ]
# Missing echo at 3 km ASL with valid echo at 4 km ASL and
# reflectivity > threshold at 4 km will be filled with radar reflectivity at 4 km
ReflThresh_lowlevel_gap:  20.
# Stratiform rain reflectivity threshold at 3 km ASL [dBZ]
strat_EchoThresh_3km:  20.
# Stratiform rain reflectivity threshold below 3 km ASL [dBZ]
strat_EchoThresh_lt3km:  10.0
# Column-mean reflectivitiy peakedness fraction threshold to be convective
col_peakedness_frac:  0.3
# Above melting level reflectivity threshold [dBZ] to be convective
abs_ConvThres_aml:  45.
# 25 dBZ echo-top height threshold [km] to be convective
etop25dBZ_Thresh:  10.0
# Composite reflectivity threshold [dBZ] for neighbor points to be convective
neighbor_CompReflThresh:  25.
# Reflectivity vertical gradient (low - up) threshold [dB] to be updraft
updraft_ReflGradiant_Thresh:  8.0
# Max height [km] to include reflectivity vertical gradient to be updraft
updraft_ReflGradiant_MaxHeight:  7.0
# Composite reflectivity threshold [dBZ] to be updraft
updraft_CompRefl_Thresh:  40.0
# Number of vertical level gaps allowed in calculating echo-top height
echotop_gap: 1
# Height level (ASL) to save 2D reflectivity [km]
dbz_lowlevel_asl: 2.0

# Cloud identification parameters
mincoldcorepix:  4  # Minimum number of pixels for the cold core
smoothwindowdimensions:  30  # Dimension of the Box2DKernel filter on Tb.
medfiltsize: 5      # Window size to perform medfilt2d to fill missing Tb pixels, must be an odd number
geolimits: [-90, -360, 90, 360] # 4-element array to subset domain boundaries [lat_min, lon_min, lat_max, lon_max]
area_thresh:  36  # [km^2] Minimum area to define a cloud
miss_thresh:  0.35  # Missing data fraction threshold. If missing data exceeds this, the time frame will be omitted.
cloudtb_core:  225.0  # [K]
cloudtb_cold:  241.0  # [K]
cloudtb_warm:  261.0  # [K]
cloudtb_cloud:  261.0  # [K]
absolutetb_threshs: [160, 330]  # K [min, max] absolute Tb range allowed.
warmanvilexpansion:  0  # Not working yet, set this to 0 for now
cloudidmethod: 'label_grow'
# Specific parameters to link cloud objects using PF
linkpf:  1  # Set to 1 to turn on linkpf option; default: 0
linkpf_varname: 'reflectivity_comp'   # PF variable name to perform linkpf operation
pf_smooth_window:  10  # Smoothing window for identifying PF
pf_dbz_thresh:  25  # [dBZ] for reflectivity, or [mm/h] for rainrate
pf_link_area_thresh:  300.0  # [km^2]

# Tracking parameters
othresh: 0.5  # overlap fraction threshold. Clouds that overlap more than this between times are tracked.
timegap: 3.1  # [hour] If missing data duration longer than this, tracking restarts
nmaxlinks: 200  # Maximum number of clouds that any single cloud can be linked to
maxnclouds: 2000  # Maximum number of clouds in one snapshot
duration_range: [2, 300] # A vector [minlength,maxlength] to specify the duration range for the tracks
# Flag to remove short-lived tracks [< min(duration_range)] that are not mergers/splits with other tracks
# 0:keep all tracks; 1:remove short tracks
remove_shorttracks: 1
# Set this flag to 1 to write a dense (2D) trackstats netCDF file
# Note that for datasets with lots of tracks, the memory consumption could be large
trackstats_dense_netcdf: 1
# Minimum time difference threshold to match track stats with cloudid files
match_pixel_dt_thresh: 60.0  # seconds

# MCS Tb parameters
mcs_tb_area_thresh: 60000  # [km^2] Tb area threshold
mcs_tb_duration_thresh:  6  # [hour] Tb minimum length of a mcs
mcs_tb_split_duration:  12  # [hour] Tb tracks smaller or equal to this length will be included with the MCS splits from
mcs_tb_merge_duration:  12  # [hour] Tb tracks smaller or equal to this length will be included with the MCS merges into
mcs_tb_gap: 1  # [unitless] Allowable temporal gap in Tb data for MCS area threshold
# MCS PF parameters
mcs_pf_majoraxis_thresh:  100  # [km] MCS PF major axis length lower limit
max_pf_majoraxis_thresh:  1800  # [km] MCS PF major axis length upper limit
mcs_pf_durationthresh:  5  # [hour] PF minimum length of mcs
mcs_pf_majoraxis_for_lifetime:  20  # [km] Minimum PF size to count PF lifetime
mcs_pf_gap:  1  # [unitless] Allowable temporal gap in PF data for MCS characteristics
landfrac_thresh: 90  # [%] Define threshold for PF land fraction
# Specify rain rate parameters
pf_rr_thres:  2.0  # [mm/hr] Rain rate threshold to define a precipitation feature
pcp_thresh:  1.0  # [mm/hr] Rain rate threshold to label pixels with track number
heavy_rainrate_thresh:  10.0  # Heavy rain rate threshold [mm/hr]
nmaxpf: 5  # Maximum number of precipitation features to save their statistics within a cloud feature
#nmaxcore: 5  # Maximum number of convective cores to save their statistics within a cloud feature
mcs_core_min_area: 180  # [km^2] Min area to calculate convective core statistics
dbz_thresh: 10  # [dBZ] Reflectivity threshold to label pixels with track number
mcs_lifecycle_thresh: 8  # MCS Tb duration [hour]

# Define tracked feature variable names
feature_varname: 'feature_number'
nfeature_varname: 'nfeatures'
featuresize_varname: 'npix_feature'

# Track statistics output file dimension names
tracks_dimname: 'tracks'
times_dimname: 'times'
pf_dimname: 'nmaxpf'
fillval: -9999
# MCS track stats file base names
mcstbstats_filebase: 'mcs_tracks_'
mcspfstats_filebase: 'mcs_tracks_pf_'
mcsrobust_filebase: 'mcs_tracks_robust_'
pixeltracking_filebase: 'mcstrack_'
mcsfinal_filebase: 'mcs_tracks_final_'

# Feature movement speed parameters
lag_for_speed: 1  # [unitless] lag intervals between tracked features to calculate movement
track_number_for_speed: "dbztracknumber"
track_field_for_speed: 'reflectivity_comp'
min_size_thresh_for_speed: 20 # [km] Min PF major axis length to calculate movement
max_speed_thresh: 50  # [m/s] Speeds larger than this will be replaced by temporal filter
```

### `builtin/builtin/pyflextrkr/pkg.py`

```python
"""
This module provides classes and methods to launch the Gray Scott application.
Pyflextrkr is ....
"""
from jarvis_cd.basic.pkg import Application, Color
from jarvis_util import *
import time
import pathlib

import yaml
from scspkg.pkg import Package

class Pyflextrkr(Application):
    """
    This class provides methods to launch the Pyflextrkr application.
    """
    def _init(self):
        """
        Initialize paths
        """
        self.pkg_type = 'pyflextrkr'
        self.hermes_env_vars = ['HERMES_ADAPTER_MODE', 'HERMES_CLIENT_CONF', 
                                'HERMES_CONF', 'LD_PRELOAD']

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        
        return [
            {
                'name': 'conda_env',
                'msg': 'Name of the conda environment for running Pyflextrkr',
                'type': str,
                'default': "flextrkr",
            },
            {
                'name': 'config',
                'msg': 'The config file for running analysis',
                'type': str,
                'default': None,
            },
            {
                'name': 'runscript',
                'msg': 'The name of the Pyflextrkr script to run (run_mcs_tbpfradar3d_wrf)',
                'type': str,
                'default': 'run_mcs_tbpfradar3d_wrf',
                'choices': ['run_mcs_tbpfradar3d_wrf', 'run_mcs_tbpf_saag_summer_sam', 'run_mcs_tb_summer_sam']
            },
            {
                'name': 'flush_mem',
                'msg': 'Flushing the memory after each stage',
                'type': bool,
                'default': False,
            },
            {
                'name': 'flush_mem_cmd',
                'msg': 'Command to flush the node memory',
                'type': str,
                'default': "ml user-scripts; sudo drop_caches", # for Ares
            },
            {
                'name': 'pyflextrkr_path',
                'msg': 'Absolute path to the Pyflextrkr source code',
                'type': str,
                'default': f"{Package(self.pkg_type).pkg_root}/src/PyFLEXTRKR",
            },
            {
                'name': 'experiment_input_path',
                'msg': 'Absolute path to the experiment run input and output files',
                'type': str,
                'default': None,
            },
            {
                'name': 'run_parallel',
                'msg': 'Parallel mode for Pyflextrkr: 0 (serial), 1 (local cluster), 2 (Dask MPI)',
                'type': int,
                'default': 1,
                'choices': [0,1,2],
            },
            {
                'name': 'nprocesses',
                'msg': 'Number of processes to run in parallel',
                'type': int,
                'default': 8,
            },
            {
                'name': 'run_cmd', # This is a internal variable
                'msg': 'Command to run Pyflextrkr',
                'type': str,
                'default': None,
            },
            {
                'name': 'local_exp_dir',
                'msg': 'Local experiment directory',
                'type': str,
                'default': None,
            },
            {
                'name': 'with_hermes',
                'msg': 'Whether it is used with Hermes (e.g. needs to update environment variables)',
                'type': bool,
                'default': False,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        
        experiment_input_path = os.getenv('EXPERIMENT_INPUT_PATH')
        if experiment_input_path is None:
            raise Exception("Must set the experiment_input_path")
        else:
            self.config['experiment_input_path'] = experiment_input_path
        
        # update config file everytime
        self.config['config'] = f"{self.pkg_dir}/example_config/{self.config['runscript']}_template.yml"
        
        # Check if pyflextrkr_path not exists
        if pathlib.Path(self.config['pyflextrkr_path']).exists() == False:
            raise Exception(f"`pyflextrkr_path` {self.config['pyflextrkr_path']} does not exist.")
        
        if self.config['conda_env'] is None:
            raise Exception("Must set the conda environment for running Pyflextrkr")
        
        if self.config['runscript'] is None:
            raise Exception("Must set the Pyflextrkr script to run")
        else:
            
            # check if run script matches config file
            if self.config['runscript'] not in self.config['config']:
                raise Exception(f"Run script {self.config['runscript']} does not match config file {self.config['config']}")
            
            # get base file name without extension
            pass_in_path = self.config['runscript']
            script_name = pass_in_path.split("/")[-1]
            # remove ".py" from file name
            if ".py" in script_name:
                script_name = script_name[:-3]
            self.config['runscript'] = script_name

        # Check if config file exists
        if pathlib.Path(self.config['config']).exists():
            pass
        else:
            raise Exception(f"File {self.config['config']} does not exist.")

        if self.config['flush_mem'] == False:
            self.env['FLUSH_MEM'] = "FALSE"
        else:
            self.env['FLUSH_MEM'] = "TRUE"
            if self.config['flush_mem_cmd'] is None:
                raise Exception("Must add the command to flush memory using flush_mem_cmd")
        
        if self.config['pyflextrkr_path'] is None:
            raise Exception("Must set the `pyflextrkr_path` to the Pyflextrkr source code")
        else:
            # check that path exists
            pathlib.Path(self.config['pyflextrkr_path']).exists()
            # self.config['stdout'] = f'{self.config["pyflextrkr_path"]}/pyflextrkr_run.log'
        

    def _configure_yaml(self):
        self.env['HDF5_USE_FILE_LOCKING'] = "FALSE" # set HDF5 locking: FALSE, TRUE, BESTEFFORT

        yaml_file = self.config['config']
        
        if "_template.yml" not in str(yaml_file):
            yaml_file = yaml_file.replace(".yml", "_template.yml")
        
        self.log(f"Pyflextrkr config from: {yaml_file}")
        
        with open(yaml_file, "r") as stream:
            
            experiment_input_path = self.config['experiment_input_path']
            if self.config['local_exp_dir'] is not None:
                experiment_input_path = self.config['local_exp_dir']
            
            input_path = f"{experiment_input_path}/{self.config['runscript']}/"
            output_path = f"{experiment_input_path}/output_data/{self.config['runscript']}/"
            
            # Check if input_path exists and has files
            if pathlib.Path(input_path).exists() == False:
                raise Exception(f"Input path {input_path} does not exist.")
            if len(os.listdir(input_path)) == 0:
                raise Exception(f"Input path {input_path} is empty.")
            
            # pathlib.Path(input_path).mkdir(parents=True, exist_ok=True) # this should be done in data stage_in or setup
            pathlib.Path(output_path).mkdir(parents=True, exist_ok=True)
            
            try:
                config_vars = yaml.safe_load(stream)
                
                config_vars['dask_tmp_dir'] = f"/tmp/pyflextrkr_test"
                pathlib.Path(config_vars['dask_tmp_dir']).mkdir(parents=True, exist_ok=True)
                
                config_vars['clouddata_path'] = str(input_path)
                config_vars['root_path'] = str(output_path)
                
                # Set run mode
                config_vars['run_parallel'] = self.config['run_parallel']
                
                # check processes
                if self.config['run_parallel'] == 0 and self.config['nprocesses'] > 1:
                    self.log(f"WARNING: run_parallel is 0 (serial) nprocesses is set to 1")
                    self.config['nprocesses'] = 1
                config_vars['nprocesses'] = self.config['nprocesses']
                
                if self.config['nprocesses'] < config_vars['nprocesses']:
                    self.log(f"WARNING: nprocesses is less than config file, set to {config_vars['nprocesses']}")
                    self.config['nprocesses'] = config_vars['nprocesses']
                
                # check if landmask_filename is a key in config_vars
                if 'landmask_filename' in config_vars:
                    org_path = config_vars['landmask_filename']
                    landmask_path = org_path.replace('INPUT_DIR/', input_path)
                    landmask_path = landmask_path.replace("'", "") # remove single quotes format
                    
                    if pathlib.Path(landmask_path).exists():
                        config_vars['landmask_filename'] = str(landmask_path)
                    else:
                        raise Exception(f"File {landmask_path} does not exist.")
                
                # save config_vars back to yaml file
                new_yaml_file = yaml_file.replace("_template.yml", ".yml")
                yaml.dump(config_vars, open(new_yaml_file, 'w'), default_flow_style=False)
            except yaml.YAMLError as exc:
                self.log(exc)
        self.config['config'] = new_yaml_file 
            
    def _unset_vfd_vars(self,env_vars_toset):
        cmd = ['conda', 'env', 'config', 'vars', 'unset',]
        
        for env_var in env_vars_toset:
            cmd.append(f'{env_var}')
        cmd.append('-n')
        cmd.append(self.config['conda_env'])
        
        cmd = ' '.join(cmd)
        Exec(cmd, LocalExecInfo(env=self.mod_env,))
        self.log(f"Pyflextrkr _unset_vfd_vars: {cmd}")

    def _set_env_vars(self, env_vars_toset):
        
        self.log(f"Pyflextrkr _set_env_vars")
        
        # Unset all env_vars_toset first
        self._unset_vfd_vars(env_vars_toset)

        cmd = [ 'conda', 'env', 'config', 'vars', 'set']
        for env_var in env_vars_toset:
            env_var_val = self.mod_env[env_var]
            cmd.append(f'{env_var}={env_var_val}')
        
        cmd.append('-n')
        cmd.append(self.config['conda_env'])
        cmd = ' '.join(cmd)
        self.log(f"Pyflextrkr _set_env_vars: {cmd}")
        Exec(cmd, LocalExecInfo(env=self.mod_env,))
        
    
    def _construct_cmd(self):
        """
        Construct the command to launch the application. E.g., Pyflextrkr will
        launch with expected environment and number of srun processes.

        :return: None
        """
        self.clean()
        
        cmd = []
        if self.config['run_parallel'] == 1:
            cmd = [
            'conda','run', '-v','-n', self.config['conda_env'],
            ]
        elif self.config['run_parallel'] == 2:
            host_list_str = None
            
            # Check if self.jarvis.hostfile is set
            if self.jarvis.hostfile is None:
                raise Exception("Running with Dask-MPI mode but self.jarvis.hostfile is None")
            
            # open self.jarvis.hostfile to get all lines of hosts into a string deliminated by ,
            # self.log(f"Pyflextrkr hostfile: {self.jarvis.hostfile}")
            if 'localhost' in self.jarvis.hostfile:
                host_list_str = "127.0.0.1"
            else:
                for hostname in self.jarvis.hostfile:
                    if host_list_str is None:
                        host_list_str = hostname.rstrip()
                    else:
                        host_list_str = host_list_str + "," + hostname.rstrip()
            
            if host_list_str is None:
                raise Exception("host_list_str is None")
            self.log(f"Pyflextrkr host_list_str: {host_list_str}")
            
            # mpirun --host $hostlist --npernode 2
            ppn = self.config['nprocesses']/len(self.jarvis.hostfile)
            cmd = [
                'conda','run', '-v','-n', self.config['conda_env'],
                'mpirun',
                '--host', host_list_str,
                '-n', str(self.config['nprocesses']),
                '-ppn', str(int(ppn)),
                # '-env', f'HDF5_USE_FILE_LOCKING={self.config["HDF5_USE_FILE_LOCKING"]}',
            ]
        
        # Exec("which python")
        cmd.append('python')
        # Convert runscript to full .py file path
        if self.config['pyflextrkr_path'] and self.config['runscript']:
            cmd.append(f'{self.config["pyflextrkr_path"]}/runscripts/{self.config["runscript"]}.py')
        
        
        cmd.append(self.config['config'])

        self.config['run_cmd'] = ' '.join(cmd)

    def start(self):
        """
        Launch an application. E.g., Pyflextrkr will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        
        if self.config['with_hermes'] == True:
            self._set_env_vars(self.hermes_env_vars)
        else:
            self._unset_vfd_vars(self.hermes_env_vars)
        
        ## Configure yaml file before start
        self._configure_yaml()
        self._construct_cmd()
        
        self.log(f"Pyflextrkr run_cmd: {self.config['run_cmd']}")
        
        start = time.time()
        
        Exec(self.config['run_cmd'],
             LocalExecInfo(env=self.mod_env,
                           do_dbg=self.config['do_dbg'],
                           dbg_port=self.config['dbg_port'],
                           pipe_stdout=self.config['stdout'],
                           pipe_stderr=self.config['stderr'],
                           ))
        
        end = time.time()
        diff = end - start
        self.log(f'Pyflextrkr TIME: {diff} seconds') # color=Color.GREEN
        

    def stop(self):
        """
        Stop a running application. E.g., Pyflextrkr will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass
        
    def kill(self):
        """
        Stop a running application. E.g., Pyflextrkr will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        cmd = ['killall', '-9', 'python']
        Exec(' '.join(cmd), LocalExecInfo(hostfile=self.jarvis.hostfile))

    def clean(self):
        """
        Destroy all data for an application. E.g., Pyflextrkr will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        # self.log(f"Manual Exec Required: Please clean up files in {self.config['experiment_input_path']}")
        
        output_dir = self.config['experiment_input_path'] + f"/output_data/{self.config['runscript']}"
        if self.config['local_exp_dir'] is not None:
            output_dir = self.config['local_exp_dir'] + f"/output_data/{self.config['runscript']}"
        
        # recursive remove all files in output_data directory
        self.log(f'Removing {output_dir}')
        Rm(output_dir)
        
        ## Do not clear cache in script, clear cache manually
        # # Clear cache
        # self.log(f'Clearing cache')
        # Exec(self.config['flush_mem_cmd'], LocalExecInfo(env=self.mod_env,))
        
        # output_dir = self.config['output'] + "*"
        # self.log(f'Removing {output_dir}')
        # Rm(output_dir)
```

### `builtin/builtin/pymonitor/pkg.py`

```python
"""
This module provides classes and methods to launch the Ior application.
Ior is ....
"""
from jarvis_cd.basic.pkg import Service
from jarvis_util import *
from jarvis_util.introspect.monitor import Monitor

class Pymonitor(Service):
    """
    This class provides methods to launch the Ior application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'frequency',
                'msg': 'Monitor frequency in seconds',
                'type': int,
                'default': 1
            },
            {
                'name': 'dir',
                'msg': 'Directory to store monitor logs',
                'type': str,
                'default': None,
            },
            {
                'name': 'num_nodes',
                'msg': 'Number of nodes to run monitor on. 0 means all',
                'type': int,
                'default': 0,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        if self.config['dir'] is None:
            self.config['dir'] = f'{self.shared_dir}/logs'
        self.config['dir'] = os.path.expandvars(self.config['dir'])
        Mkdir(self.config['dir'])
        self.env['MONITOR_DIR'] = self.config['dir']
        self.log(f'The config dir is {self.config["dir"]}')

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        self.log(f'Pymonitor started on {self.config["dir"]}')
        self.env['PYTHONBUFFERED'] = '0'
        hostfile = self.jarvis.hostfile
        if self.config['num_nodes'] > 0:
            hostfile = hostfile.subset(self.config['num_nodes'])
        Monitor(self.config['frequency'],
                self.config['dir'],
                PsshExecInfo(env=self.env,
                            hostfile=hostfile,
                            exec_async=True))
        time.sleep(self.config['sleep'])

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        Kill('.*pymonitor.*', PsshExecInfo(env=self.env))

    def status(self):
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        Rm(self.config['dir'])
```

### `builtin/builtin/redis-benchmark/pkg.py`

```python
"""
This module provides classes and methods to launch the Redis benchmark tool.
Redis cluster is used if the hostfile has many hosts
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class RedisBenchmark(Application):
    """
    This class provides methods to launch the Ior application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'port',
                'msg': 'The port to use for the cluster',
                'type': int,
                'default': 7000,
                'choices': [],
                'args': [],
            },
            {
                'name': 'count',
                'msg': 'Number of requests to generate',
                'type': int,
                'default': 1000,
                'choices': [],
                'args': [],
            },
            {
                'name': 'write',
                'msg': 'Perform writes',
                'type': bool,
                'default': True,
                'choices': [],
                'args': [],
            },
            {
                'name': 'read',
                'msg': 'Perform reads',
                'type': bool,
                'default': True,
                'choices': [],
                'args': [],
            },
            {
                'name': 'nthreads',
                'msg': 'Number of threads',
                'type': int,
                'default': 1,
                'choices': [],
                'args': [],
            },
            {
                'name': 'pipeline',
                'msg': 'Number of requests to pipeline',
                'type': int,
                'default': 1,
                'choices': [],
                'args': [],
            },
            {
                'name': 'req_size',
                'msg': 'Size of requests (bytes)',
                'type': int,
                'default': 3,
                'choices': [],
                'args': [],
            },
            {
                'name': 'node',
                'msg': 'The node id to use for the cluster',
                'type': int,
                'default': 0,
                'choices': [],
                'args': [],
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """

        hostfile = self.jarvis.hostfile
        bench_type = [
            'set' if self.config['write'] else '',
            'get' if self.config['read'] else '',
        ]
        bench_type = ','.join([b for b in bench_type if b])
        cmd = [
            'redis-benchmark',
            f'-n {self.config["count"]}',
            f'-t {bench_type}',
            f'-P {self.config["pipeline"]}',
            f'--threads {self.config["nthreads"]}',
            f'-d {self.config["req_size"]}',
            f'-p {self.config["port"]}',
        ]
        if len(hostfile) > 1:
            cmd += [
                f'-h {hostfile.hosts[self.config["node"]]}',
                f'--cluster'
            ]
        self.log('Starting the cluster', color=Color.YELLOW)
        Exec(' '.join(cmd),
             LocalExecInfo(env=self.mod_env,
                           hostfile=hostfile,
                           do_dbg=self.config['do_dbg'],
                           dbg_port=self.config['dbg_port']))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        hostfile = self.jarvis.hostfile
        for host in range(hostfile.hosts):
            Exec(f'redis-cli -p {self.config["port"]} -h {host} flushall',
                 LocalExecInfo(env=self.mod_env,
                               hostfile=hostfile,
                               do_dbg=self.config['do_dbg'],
                               dbg_port=self.config['dbg_port']))
            Exec(f'redis-cli -p {self.config["port"]} -h {host} cluster reset',
                 LocalExecInfo(env=self.mod_env,
                               hostfile=hostfile,
                               do_dbg=self.config['do_dbg'],
                               dbg_port=self.config['dbg_port']))
```

### `builtin/builtin/redis/config/redis.conf`

```conf
# Redis configuration file example.
#
# Note that in order to read the configuration file, Redis must be
# started with the file path as first argument:
#
# ./redis-server /path/to/redis.conf

# Note on units: when memory size is needed, it is possible to specify
# it in the usual form of 1k 5GB 4M and so forth:
#
# 1k => 1000 bytes
# 1kb => 1024 bytes
# 1m => 1000000 bytes
# 1mb => 1024*1024 bytes
# 1g => 1000000000 bytes
# 1gb => 1024*1024*1024 bytes
#
# units are case insensitive so 1GB 1Gb 1gB are all the same.

################################## INCLUDES ###################################

# Include one or more other config files here.  This is useful if you
# have a standard template that goes to all Redis servers but also need
# to customize a few per-server settings.  Include files can include
# other files, so use this wisely.
#
# Note that option "include" won't be rewritten by command "CONFIG REWRITE"
# from admin or Redis Sentinel. Since Redis always uses the last processed
# line as value of a configuration directive, you'd better put includes
# at the beginning of this file to avoid overwriting config change at runtime.
#
# If instead you are interested in using includes to override configuration
# options, it is better to use include as the last line.
#
# Included paths may contain wildcards. All files matching the wildcards will
# be included in alphabetical order.
# Note that if an include path contains a wildcards but no files match it when
# the server is started, the include statement will be ignored and no error will
# be emitted.  It is safe, therefore, to include wildcard files from empty
# directories.
#
# include /path/to/local.conf
# include /path/to/other.conf
# include /path/to/fragments/*.conf
#

################################## MODULES #####################################

# Load modules at startup. If the server is not able to load modules
# it will abort. It is possible to use multiple loadmodule directives.
#
# loadmodule /path/to/my_module.so
# loadmodule /path/to/other_module.so

################################## NETWORK #####################################

# By default, if no "bind" configuration directive is specified, Redis listens
# for connections from all available network interfaces on the host machine.
# It is possible to listen to just one or multiple selected interfaces using
# the "bind" configuration directive, followed by one or more IP addresses.
# Each address can be prefixed by "-", which means that redis will not fail to
# start if the address is not available. Being not available only refers to
# addresses that does not correspond to any network interface. Addresses that
# are already in use will always fail, and unsupported protocols will always BE
# silently skipped.
#
# Examples:
#
# bind 192.168.1.100 10.0.0.1     # listens on two specific IPv4 addresses
# bind 127.0.0.1 ::1              # listens on loopback IPv4 and IPv6
# bind * -::*                     # like the default, all available interfaces
#
# ~~~ WARNING ~~~ If the computer running Redis is directly exposed to the
# internet, binding to all the interfaces is dangerous and will expose the
# instance to everybody on the internet. So by default we uncomment the
# following bind directive, that will force Redis to listen only on the
# IPv4 and IPv6 (if available) loopback interface addresses (this means Redis
# will only be able to accept client connections from the same host that it is
# running on).
#
# IF YOU ARE SURE YOU WANT YOUR INSTANCE TO LISTEN TO ALL THE INTERFACES
# COMMENT OUT THE FOLLOWING LINE.
#
# You will also need to set a password unless you explicitly disable protected
# mode.
# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
bind 0.0.0.0

# By default, outgoing connections (from replica to master, from Sentinel to
# instances, cluster bus, etc.) are not bound to a specific local address. In
# most cases, this means the operating system will handle that based on routing
# and the interface through which the connection goes out.
#
# Using bind-source-addr it is possible to configure a specific address to bind
# to, which may also affect how the connection gets routed.
#
# Example:
#
# bind-source-addr 10.0.0.1

# Protected mode is a layer of security protection, in order to avoid that
# Redis instances left open on the internet are accessed and exploited.
#
# When protected mode is on and the default user has no password, the server
# only accepts local connections from the IPv4 address (127.0.0.1), IPv6 address
# (::1) or Unix domain sockets.
#
# By default protected mode is enabled. You should disable it only if
# you are sure you want clients from other hosts to connect to Redis
# even if no authentication is configured.
protected-mode no

# Redis uses default hardened security configuration directives to reduce the
# attack surface on innocent users. Therefore, several sensitive configuration
# directives are immutable, and some potentially-dangerous commands are blocked.
#
# Configuration directives that control files that Redis writes to (e.g., 'dir'
# and 'dbfilename') and that aren't usually modified during runtime
# are protected by making them immutable.
#
# Commands that can increase the attack surface of Redis and that aren't usually
# called by users are blocked by default.
#
# These can be exposed to either all connections or just local ones by setting
# each of the configs listed below to either of these values:
#
# no    - Block for any connection (remain immutable)
# yes   - Allow for any connection (no protection)
# local - Allow only for local connections. Ones originating from the
#         IPv4 address (127.0.0.1), IPv6 address (::1) or Unix domain sockets.
#
# enable-protected-configs no
# enable-debug-command no
# enable-module-command no

# Accept connections on the specified port, default is 6379 (IANA #815344).
# If port 0 is specified Redis will not listen on a TCP socket.
port ##PORT##

# TCP listen() backlog.
#
# In high requests-per-second environments you need a high backlog in order
# to avoid slow clients connection issues. Note that the Linux kernel
# will silently truncate it to the value of /proc/sys/net/core/somaxconn so
# make sure to raise both the value of somaxconn and tcp_max_syn_backlog
# in order to get the desired effect.
tcp-backlog 511

# Unix socket.
#
# Specify the path for the Unix socket that will be used to listen for
# incoming connections. There is no default, so Redis will not listen
# on a unix socket when not specified.
#
# unixsocket /run/redis.sock
# unixsocketperm 700

# Close the connection after a client is idle for N seconds (0 to disable)
timeout 0

# TCP keepalive.
#
# If non-zero, use SO_KEEPALIVE to send TCP ACKs to clients in absence
# of communication. This is useful for two reasons:
#
# 1) Detect dead peers.
# 2) Force network equipment in the middle to consider the connection to be
#    alive.
#
# On Linux, the specified value (in seconds) is the period used to send ACKs.
# Note that to close the connection the double of the time is needed.
# On other kernels the period depends on the kernel configuration.
#
# A reasonable value for this option is 300 seconds, which is the new
# Redis default starting with Redis 3.2.1.
tcp-keepalive 300

# Apply OS-specific mechanism to mark the listening socket with the specified
# ID, to support advanced routing and filtering capabilities.
#
# On Linux, the ID represents a connection mark.
# On FreeBSD, the ID represents a socket cookie ID.
# On OpenBSD, the ID represents a route table ID.
#
# The default value is 0, which implies no marking is required.
# socket-mark-id 0

################################# TLS/SSL #####################################

# By default, TLS/SSL is disabled. To enable it, the "tls-port" configuration
# directive can be used to define TLS-listening ports. To enable TLS on the
# default port, use:
#
# port 0
# tls-port 6379

# Configure a X.509 certificate and private key to use for authenticating the
# server to connected clients, masters or cluster peers.  These files should be
# PEM formatted.
#
# tls-cert-file redis.crt
# tls-key-file redis.key
#
# If the key file is encrypted using a passphrase, it can be included here
# as well.
#
# tls-key-file-pass secret

# Normally Redis uses the same certificate for both server functions (accepting
# connections) and client functions (replicating from a master, establishing
# cluster bus connections, etc.).
#
# Sometimes certificates are issued with attributes that designate them as
# client-only or server-only certificates. In that case it may be desired to use
# different certificates for incoming (server) and outgoing (client)
# connections. To do that, use the following directives:
#
# tls-client-cert-file client.crt
# tls-client-key-file client.key
#
# If the key file is encrypted using a passphrase, it can be included here
# as well.
#
# tls-client-key-file-pass secret

# Configure a DH parameters file to enable Diffie-Hellman (DH) key exchange,
# required by older versions of OpenSSL (<3.0). Newer versions do not require
# this configuration and recommend against it.
#
# tls-dh-params-file redis.dh

# Configure a CA certificate(s) bundle or directory to authenticate TLS/SSL
# clients and peers.  Redis requires an explicit configuration of at least one
# of these, and will not implicitly use the system wide configuration.
#
# tls-ca-cert-file ca.crt
# tls-ca-cert-dir /etc/ssl/certs

# By default, clients (including replica servers) on a TLS port are required
# to authenticate using valid client side certificates.
#
# If "no" is specified, client certificates are not required and not accepted.
# If "optional" is specified, client certificates are accepted and must be
# valid if provided, but are not required.
#
# tls-auth-clients no
# tls-auth-clients optional

# By default, a Redis replica does not attempt to establish a TLS connection
# with its master.
#
# Use the following directive to enable TLS on replication links.
#
# tls-replication yes

# By default, the Redis Cluster bus uses a plain TCP connection. To enable
# TLS for the bus protocol, use the following directive:
#
# tls-cluster yes

# By default, only TLSv1.2 and TLSv1.3 are enabled and it is highly recommended
# that older formally deprecated versions are kept disabled to reduce the attack surface.
# You can explicitly specify TLS versions to support.
# Allowed values are case insensitive and include "TLSv1", "TLSv1.1", "TLSv1.2",
# "TLSv1.3" (OpenSSL >= 1.1.1) or any combination.
# To enable only TLSv1.2 and TLSv1.3, use:
#
# tls-protocols "TLSv1.2 TLSv1.3"

# Configure allowed ciphers.  See the ciphers(1ssl) manpage for more information
# about the syntax of this string.
#
# Note: this configuration applies only to <= TLSv1.2.
#
# tls-ciphers DEFAULT:!MEDIUM

# Configure allowed TLSv1.3 ciphersuites.  See the ciphers(1ssl) manpage for more
# information about the syntax of this string, and specifically for TLSv1.3
# ciphersuites.
#
# tls-ciphersuites TLS_CHACHA20_POLY1305_SHA256

# When choosing a cipher, use the server's preference instead of the client
# preference. By default, the server follows the client's preference.
#
# tls-prefer-server-ciphers yes

# By default, TLS session caching is enabled to allow faster and less expensive
# reconnections by clients that support it. Use the following directive to disable
# caching.
#
# tls-session-caching no

# Change the default number of TLS sessions cached. A zero value sets the cache
# to unlimited size. The default size is 20480.
#
# tls-session-cache-size 5000

# Change the default timeout of cached TLS sessions. The default timeout is 300
# seconds.
#
# tls-session-cache-timeout 60

################################# GENERAL #####################################

# By default Redis does not run as a daemon. Use 'yes' if you need it.
# Note that Redis will write a pid file in /var/run/redis.pid when daemonized.
# When Redis is supervised by upstart or systemd, this parameter has no impact.
daemonize no

# If you run Redis from upstart or systemd, Redis can interact with your
# supervision tree. Options:
#   supervised no      - no supervision interaction
#   supervised upstart - signal upstart by putting Redis into SIGSTOP mode
#                        requires "expect stop" in your upstart job config
#   supervised systemd - signal systemd by writing READY=1 to $NOTIFY_SOCKET
#                        on startup, and updating Redis status on a regular
#                        basis.
#   supervised auto    - detect upstart or systemd method based on
#                        UPSTART_JOB or NOTIFY_SOCKET environment variables
# Note: these supervision methods only signal "process is ready."
#       They do not enable continuous pings back to your supervisor.
#
# The default is "no". To run under upstart/systemd, you can simply uncomment
# the line below:
#
# supervised auto

# If a pid file is specified, Redis writes it where specified at startup
# and removes it at exit.
#
# When the server runs non daemonized, no pid file is created if none is
# specified in the configuration. When the server is daemonized, the pid file
# is used even if not specified, defaulting to "/var/run/redis.pid".
#
# Creating a pid file is best effort: if Redis is not able to create it
# nothing bad happens, the server will start and run normally.
#
# Note that on modern Linux systems "/run/redis.pid" is more conforming
# and should be used instead.
pidfile /var/run/redis_6379.pid

# Specify the server verbosity level.
# This can be one of:
# debug (a lot of information, useful for development/testing)
# verbose (many rarely useful info, but not a mess like the debug level)
# notice (moderately verbose, what you want in production probably)
# warning (only very important / critical messages are logged)
loglevel notice

# Specify the log file name. Also the empty string can be used to force
# Redis to log on the standard output. Note that if you use standard
# output for logging but daemonize, logs will be sent to /dev/null
logfile ""

# To enable logging to the system logger, just set 'syslog-enabled' to yes,
# and optionally update the other syslog parameters to suit your needs.
# syslog-enabled no

# Specify the syslog identity.
# syslog-ident redis

# Specify the syslog facility. Must be USER or between LOCAL0-LOCAL7.
# syslog-facility local0

# To disable the built in crash log, which will possibly produce cleaner core
# dumps when they are needed, uncomment the following:
#
# crash-log-enabled no

# To disable the fast memory check that's run as part of the crash log, which
# will possibly let redis terminate sooner, uncomment the following:
#
# crash-memcheck-enabled no

# Set the number of databases. The default database is DB 0, you can select
# a different one on a per-connection basis using SELECT <dbid> where
# dbid is a number between 0 and 'databases'-1
databases 16

# By default Redis shows an ASCII art logo only when started to log to the
# standard output and if the standard output is a TTY and syslog logging is
# disabled. Basically this means that normally a logo is displayed only in
# interactive sessions.
#
# However it is possible to force the pre-4.0 behavior and always show a
# ASCII art logo in startup logs by setting the following option to yes.
always-show-logo no

# By default, Redis modifies the process title (as seen in 'top' and 'ps') to
# provide some runtime information. It is possible to disable this and leave
# the process name as executed by setting the following to no.
set-proc-title yes

# When changing the process title, Redis uses the following template to construct
# the modified title.
#
# Template variables are specified in curly brackets. The following variables are
# supported:
#
# {title}           Name of process as executed if parent, or type of child process.
# {listen-addr}     Bind address or '*' followed by TCP or TLS port listening on, or
#                   Unix socket if only that's available.
# {server-mode}     Special mode, i.e. "[sentinel]" or "[cluster]".
# {port}            TCP port listening on, or 0.
# {tls-port}        TLS port listening on, or 0.
# {unixsocket}      Unix domain socket listening on, or "".
# {config-file}     Name of configuration file used.
#
proc-title-template "{title} {listen-addr} {server-mode}"

################################ SNAPSHOTTING  ################################

# Save the DB to disk.
#
# save <seconds> <changes> [<seconds> <changes> ...]
#
# Redis will save the DB if the given number of seconds elapsed and it
# surpassed the given number of write operations against the DB.
#
# Snapshotting can be completely disabled with a single empty string argument
# as in following example:
#
# save ""
#
# Unless specified otherwise, by default Redis will save the DB:
#   * After 3600 seconds (an hour) if at least 1 change was performed
#   * After 300 seconds (5 minutes) if at least 100 changes were performed
#   * After 60 seconds if at least 10000 changes were performed
#
# You can set these explicitly by uncommenting the following line.
#
# save 3600 1 300 100 60 10000

# By default Redis will stop accepting writes if RDB snapshots are enabled
# (at least one save point) and the latest background save failed.
# This will make the user aware (in a hard way) that data is not persisting
# on disk properly, otherwise chances are that no one will notice and some
# disaster will happen.
#
# If the background saving process will start working again Redis will
# automatically allow writes again.
#
# However if you have setup your proper monitoring of the Redis server
# and persistence, you may want to disable this feature so that Redis will
# continue to work as usual even if there are problems with disk,
# permissions, and so forth.
stop-writes-on-bgsave-error yes

# Compress string objects using LZF when dump .rdb databases?
# By default compression is enabled as it's almost always a win.
# If you want to save some CPU in the saving child set it to 'no' but
# the dataset will likely be bigger if you have compressible values or keys.
rdbcompression yes

# Since version 5 of RDB a CRC64 checksum is placed at the end of the file.
# This makes the format more resistant to corruption but there is a performance
# hit to pay (around 10%) when saving and loading RDB files, so you can disable it
# for maximum performances.
#
# RDB files created with checksum disabled have a checksum of zero that will
# tell the loading code to skip the check.
rdbchecksum yes

# Enables or disables full sanitization checks for ziplist and listpack etc when
# loading an RDB or RESTORE payload. This reduces the chances of a assertion or
# crash later on while processing commands.
# Options:
#   no         - Never perform full sanitization
#   yes        - Always perform full sanitization
#   clients    - Perform full sanitization only for user connections.
#                Excludes: RDB files, RESTORE commands received from the master
#                connection, and client connections which have the
#                skip-sanitize-payload ACL flag.
# The default should be 'clients' but since it currently affects cluster
# resharding via MIGRATE, it is temporarily set to 'no' by default.
#
# sanitize-dump-payload no

# The filename where to dump the DB
dbfilename dump.rdb

# Remove RDB files used by replication in instances without persistence
# enabled. By default this option is disabled, however there are environments
# where for regulations or other security concerns, RDB files persisted on
# disk by masters in order to feed replicas, or stored on disk by replicas
# in order to load them for the initial synchronization, should be deleted
# ASAP. Note that this option ONLY WORKS in instances that have both AOF
# and RDB persistence disabled, otherwise is completely ignored.
#
# An alternative (and sometimes better) way to obtain the same effect is
# to use diskless replication on both master and replicas instances. However
# in the case of replicas, diskless is not always an option.
rdb-del-sync-files no

# The working directory.
#
# The DB will be written inside this directory, with the filename specified
# above using the 'dbfilename' configuration directive.
#
# The Append Only File will also be created inside this directory.
#
# Note that you must specify a directory here, not a file name.
dir ./

################################# REPLICATION #################################

# Master-Replica replication. Use replicaof to make a Redis instance a copy of
# another Redis server. A few things to understand ASAP about Redis replication.
#
#   +------------------+      +---------------+
#   |      Master      | ---> |    Replica    |
#   | (receive writes) |      |  (exact copy) |
#   +------------------+      +---------------+
#
# 1) Redis replication is asynchronous, but you can configure a master to
#    stop accepting writes if it appears to be not connected with at least
#    a given number of replicas.
# 2) Redis replicas are able to perform a partial resynchronization with the
#    master if the replication link is lost for a relatively small amount of
#    time. You may want to configure the replication backlog size (see the next
#    sections of this file) with a sensible value depending on your needs.
# 3) Replication is automatic and does not need user intervention. After a
#    network partition replicas automatically try to reconnect to masters
#    and resynchronize with them.
#
# replicaof <masterip> <masterport>

# If the master is password protected (using the "requirepass" configuration
# directive below) it is possible to tell the replica to authenticate before
# starting the replication synchronization process, otherwise the master will
# refuse the replica request.
#
# masterauth <master-password>
#
# However this is not enough if you are using Redis ACLs (for Redis version
# 6 or greater), and the default user is not capable of running the PSYNC
# command and/or other commands needed for replication. In this case it's
# better to configure a special user to use with replication, and specify the
# masteruser configuration as such:
#
# masteruser <username>
#
# When masteruser is specified, the replica will authenticate against its
# master using the new AUTH form: AUTH <username> <password>.

# When a replica loses its connection with the master, or when the replication
# is still in progress, the replica can act in two different ways:
#
# 1) if replica-serve-stale-data is set to 'yes' (the default) the replica will
#    still reply to client requests, possibly with out of date data, or the
#    data set may just be empty if this is the first synchronization.
#
# 2) If replica-serve-stale-data is set to 'no' the replica will reply with error
#    "MASTERDOWN Link with MASTER is down and replica-serve-stale-data is set to 'no'"
#    to all data access commands, excluding commands such as:
#    INFO, REPLICAOF, AUTH, SHUTDOWN, REPLCONF, ROLE, CONFIG, SUBSCRIBE,
#    UNSUBSCRIBE, PSUBSCRIBE, PUNSUBSCRIBE, PUBLISH, PUBSUB, COMMAND, POST,
#    HOST and LATENCY.
#
replica-serve-stale-data yes

# You can configure a replica instance to accept writes or not. Writing against
# a replica instance may be useful to store some ephemeral data (because data
# written on a replica will be easily deleted after resync with the master) but
# may also cause problems if clients are writing to it because of a
# misconfiguration.
#
# Since Redis 2.6 by default replicas are read-only.
#
# Note: read only replicas are not designed to be exposed to untrusted clients
# on the internet. It's just a protection layer against misuse of the instance.
# Still a read only replica exports by default all the administrative commands
# such as CONFIG, DEBUG, and so forth. To a limited extent you can improve
# security of read only replicas using 'rename-command' to shadow all the
# administrative / dangerous commands.
replica-read-only yes

# Replication SYNC strategy: disk or socket.
#
# New replicas and reconnecting replicas that are not able to continue the
# replication process just receiving differences, need to do what is called a
# "full synchronization". An RDB file is transmitted from the master to the
# replicas.
#
# The transmission can happen in two different ways:
#
# 1) Disk-backed: The Redis master creates a new process that writes the RDB
#                 file on disk. Later the file is transferred by the parent
#                 process to the replicas incrementally.
# 2) Diskless: The Redis master creates a new process that directly writes the
#              RDB file to replica sockets, without touching the disk at all.
#
# With disk-backed replication, while the RDB file is generated, more replicas
# can be queued and served with the RDB file as soon as the current child
# producing the RDB file finishes its work. With diskless replication instead
# once the transfer starts, new replicas arriving will be queued and a new
# transfer will start when the current one terminates.
#
# When diskless replication is used, the master waits a configurable amount of
# time (in seconds) before starting the transfer in the hope that multiple
# replicas will arrive and the transfer can be parallelized.
#
# With slow disks and fast (large bandwidth) networks, diskless replication
# works better.
repl-diskless-sync yes

# When diskless replication is enabled, it is possible to configure the delay
# the server waits in order to spawn the child that transfers the RDB via socket
# to the replicas.
#
# This is important since once the transfer starts, it is not possible to serve
# new replicas arriving, that will be queued for the next RDB transfer, so the
# server waits a delay in order to let more replicas arrive.
#
# The delay is specified in seconds, and by default is 5 seconds. To disable
# it entirely just set it to 0 seconds and the transfer will start ASAP.
repl-diskless-sync-delay 5

# When diskless replication is enabled with a delay, it is possible to let
# the replication start before the maximum delay is reached if the maximum
# number of replicas expected have connected. Default of 0 means that the
# maximum is not defined and Redis will wait the full delay.
repl-diskless-sync-max-replicas 0

# -----------------------------------------------------------------------------
# WARNING: RDB diskless load is experimental. Since in this setup the replica
# does not immediately store an RDB on disk, it may cause data loss during
# failovers. RDB diskless load + Redis modules not handling I/O reads may also
# cause Redis to abort in case of I/O errors during the initial synchronization
# stage with the master. Use only if you know what you are doing.
# -----------------------------------------------------------------------------
#
# Replica can load the RDB it reads from the replication link directly from the
# socket, or store the RDB to a file and read that file after it was completely
# received from the master.
#
# In many cases the disk is slower than the network, and storing and loading
# the RDB file may increase replication time (and even increase the master's
# Copy on Write memory and replica buffers).
# However, parsing the RDB file directly from the socket may mean that we have
# to flush the contents of the current database before the full rdb was
# received. For this reason we have the following options:
#
# "disabled"    - Don't use diskless load (store the rdb file to the disk first)
# "on-empty-db" - Use diskless load only when it is completely safe.
# "swapdb"      - Keep current db contents in RAM while parsing the data directly
#                 from the socket. Replicas in this mode can keep serving current
#                 data set while replication is in progress, except for cases where
#                 they can't recognize master as having a data set from same
#                 replication history.
#                 Note that this requires sufficient memory, if you don't have it,
#                 you risk an OOM kill.
repl-diskless-load disabled

# Master send PINGs to its replicas in a predefined interval. It's possible to
# change this interval with the repl_ping_replica_period option. The default
# value is 10 seconds.
#
# repl-ping-replica-period 10

# The following option sets the replication timeout for:
#
# 1) Bulk transfer I/O during SYNC, from the point of view of replica.
# 2) Master timeout from the point of view of replicas (data, pings).
# 3) Replica timeout from the point of view of masters (REPLCONF ACK pings).
#
# It is important to make sure that this value is greater than the value
# specified for repl-ping-replica-period otherwise a timeout will be detected
# every time there is low traffic between the master and the replica. The default
# value is 60 seconds.
#
# repl-timeout 60

# Disable TCP_NODELAY on the replica socket after SYNC?
#
# If you select "yes" Redis will use a smaller number of TCP packets and
# less bandwidth to send data to replicas. But this can add a delay for
# the data to appear on the replica side, up to 40 milliseconds with
# Linux kernels using a default configuration.
#
# If you select "no" the delay for data to appear on the replica side will
# be reduced but more bandwidth will be used for replication.
#
# By default we optimize for low latency, but in very high traffic conditions
# or when the master and replicas are many hops away, turning this to "yes" may
# be a good idea.
repl-disable-tcp-nodelay no

# Set the replication backlog size. The backlog is a buffer that accumulates
# replica data when replicas are disconnected for some time, so that when a
# replica wants to reconnect again, often a full resync is not needed, but a
# partial resync is enough, just passing the portion of data the replica
# missed while disconnected.
#
# The bigger the replication backlog, the longer the replica can endure the
# disconnect and later be able to perform a partial resynchronization.
#
# The backlog is only allocated if there is at least one replica connected.
#
# repl-backlog-size 1mb

# After a master has no connected replicas for some time, the backlog will be
# freed. The following option configures the amount of seconds that need to
# elapse, starting from the time the last replica disconnected, for the backlog
# buffer to be freed.
#
# Note that replicas never free the backlog for timeout, since they may be
# promoted to masters later, and should be able to correctly "partially
# resynchronize" with other replicas: hence they should always accumulate backlog.
#
# A value of 0 means to never release the backlog.
#
# repl-backlog-ttl 3600

# The replica priority is an integer number published by Redis in the INFO
# output. It is used by Redis Sentinel in order to select a replica to promote
# into a master if the master is no longer working correctly.
#
# A replica with a low priority number is considered better for promotion, so
# for instance if there are three replicas with priority 10, 100, 25 Sentinel
# will pick the one with priority 10, that is the lowest.
#
# However a special priority of 0 marks the replica as not able to perform the
# role of master, so a replica with priority of 0 will never be selected by
# Redis Sentinel for promotion.
#
# By default the priority is 100.
replica-priority 100

# The propagation error behavior controls how Redis will behave when it is
# unable to handle a command being processed in the replication stream from a master
# or processed while reading from an AOF file. Errors that occur during propagation
# are unexpected, and can cause data inconsistency. However, there are edge cases
# in earlier versions of Redis where it was possible for the server to replicate or persist
# commands that would fail on future versions. For this reason the default behavior
# is to ignore such errors and continue processing commands.
#
# If an application wants to ensure there is no data divergence, this configuration
# should be set to 'panic' instead. The value can also be set to 'panic-on-replicas'
# to only panic when a replica encounters an error on the replication stream. One of
# these two panic values will become the default value in the future once there are
# sufficient safety mechanisms in place to prevent false positive crashes.
#
# propagation-error-behavior ignore

# Replica ignore disk write errors controls the behavior of a replica when it is
# unable to persist a write command received from its master to disk. By default,
# this configuration is set to 'no' and will crash the replica in this condition.
# It is not recommended to change this default, however in order to be compatible
# with older versions of Redis this config can be toggled to 'yes' which will just
# log a warning and execute the write command it got from the master.
#
# replica-ignore-disk-write-errors no

# -----------------------------------------------------------------------------
# By default, Redis Sentinel includes all replicas in its reports. A replica
# can be excluded from Redis Sentinel's announcements. An unannounced replica
# will be ignored by the 'sentinel replicas <master>' command and won't be
# exposed to Redis Sentinel's clients.
#
# This option does not change the behavior of replica-priority. Even with
# replica-announced set to 'no', the replica can be promoted to master. To
# prevent this behavior, set replica-priority to 0.
#
# replica-announced yes

# It is possible for a master to stop accepting writes if there are less than
# N replicas connected, having a lag less or equal than M seconds.
#
# The N replicas need to be in "online" state.
#
# The lag in seconds, that must be <= the specified value, is calculated from
# the last ping received from the replica, that is usually sent every second.
#
# This option does not GUARANTEE that N replicas will accept the write, but
# will limit the window of exposure for lost writes in case not enough replicas
# are available, to the specified number of seconds.
#
# For example to require at least 3 replicas with a lag <= 10 seconds use:
#
# min-replicas-to-write 3
# min-replicas-max-lag 10
#
# Setting one or the other to 0 disables the feature.
#
# By default min-replicas-to-write is set to 0 (feature disabled) and
# min-replicas-max-lag is set to 10.

# A Redis master is able to list the address and port of the attached
# replicas in different ways. For example the "INFO replication" section
# offers this information, which is used, among other tools, by
# Redis Sentinel in order to discover replica instances.
# Another place where this info is available is in the output of the
# "ROLE" command of a master.
#
# The listed IP address and port normally reported by a replica is
# obtained in the following way:
#
#   IP: The address is auto detected by checking the peer address
#   of the socket used by the replica to connect with the master.
#
#   Port: The port is communicated by the replica during the replication
#   handshake, and is normally the port that the replica is using to
#   listen for connections.
#
# However when port forwarding or Network Address Translation (NAT) is
# used, the replica may actually be reachable via different IP and port
# pairs. The following two options can be used by a replica in order to
# report to its master a specific set of IP and port, so that both INFO
# and ROLE will report those values.
#
# There is no need to use both the options if you need to override just
# the port or the IP address.
#
# replica-announce-ip 5.5.5.5
# replica-announce-port 1234

############################### KEYS TRACKING #################################

# Redis implements server assisted support for client side caching of values.
# This is implemented using an invalidation table that remembers, using
# a radix key indexed by key name, what clients have which keys. In turn
# this is used in order to send invalidation messages to clients. Please
# check this page to understand more about the feature:
#
#   https://redis.io/topics/client-side-caching
#
# When tracking is enabled for a client, all the read only queries are assumed
# to be cached: this will force Redis to store information in the invalidation
# table. When keys are modified, such information is flushed away, and
# invalidation messages are sent to the clients. However if the workload is
# heavily dominated by reads, Redis could use more and more memory in order
# to track the keys fetched by many clients.
#
# For this reason it is possible to configure a maximum fill value for the
# invalidation table. By default it is set to 1M of keys, and once this limit
# is reached, Redis will start to evict keys in the invalidation table
# even if they were not modified, just to reclaim memory: this will in turn
# force the clients to invalidate the cached values. Basically the table
# maximum size is a trade off between the memory you want to spend server
# side to track information about who cached what, and the ability of clients
# to retain cached objects in memory.
#
# If you set the value to 0, it means there are no limits, and Redis will
# retain as many keys as needed in the invalidation table.
# In the "stats" INFO section, you can find information about the number of
# keys in the invalidation table at every given moment.
#
# Note: when key tracking is used in broadcasting mode, no memory is used
# in the server side so this setting is useless.
#
# tracking-table-max-keys 1000000

################################## SECURITY ###################################

# Warning: since Redis is pretty fast, an outside user can try up to
# 1 million passwords per second against a modern box. This means that you
# should use very strong passwords, otherwise they will be very easy to break.
# Note that because the password is really a shared secret between the client
# and the server, and should not be memorized by any human, the password
# can be easily a long string from /dev/urandom or whatever, so by using a
# long and unguessable password no brute force attack will be possible.

# Redis ACL users are defined in the following format:
#
#   user <username> ... acl rules ...
#
# For example:
#
#   user worker +@list +@connection ~jobs:* on >ffa9203c493aa99
#
# The special username "default" is used for new connections. If this user
# has the "nopass" rule, then new connections will be immediately authenticated
# as the "default" user without the need of any password provided via the
# AUTH command. Otherwise if the "default" user is not flagged with "nopass"
# the connections will start in not authenticated state, and will require
# AUTH (or the HELLO command AUTH option) in order to be authenticated and
# start to work.
#
# The ACL rules that describe what a user can do are the following:
#
#  on           Enable the user: it is possible to authenticate as this user.
#  off          Disable the user: it's no longer possible to authenticate
#               with this user, however the already authenticated connections
#               will still work.
#  skip-sanitize-payload    RESTORE dump-payload sanitization is skipped.
#  sanitize-payload         RESTORE dump-payload is sanitized (default).
#  +<command>   Allow the execution of that command.
#               May be used with `|` for allowing subcommands (e.g "+config|get")
#  -<command>   Disallow the execution of that command.
#               May be used with `|` for blocking subcommands (e.g "-config|set")
#  +@<category> Allow the execution of all the commands in such category
#               with valid categories are like @admin, @set, @sortedset, ...
#               and so forth, see the full list in the server.c file where
#               the Redis command table is described and defined.
#               The special category @all means all the commands, but currently
#               present in the server, and that will be loaded in the future
#               via modules.
#  +<command>|first-arg  Allow a specific first argument of an otherwise
#                        disabled command. It is only supported on commands with
#                        no sub-commands, and is not allowed as negative form
#                        like -SELECT|1, only additive starting with "+". This
#                        feature is deprecated and may be removed in the future.
#  allcommands  Alias for +@all. Note that it implies the ability to execute
#               all the future commands loaded via the modules system.
#  nocommands   Alias for -@all.
#  ~<pattern>   Add a pattern of keys that can be mentioned as part of
#               commands. For instance ~* allows all the keys. The pattern
#               is a glob-style pattern like the one of KEYS.
#               It is possible to specify multiple patterns.
# %R~<pattern>  Add key read pattern that specifies which keys can be read 
#               from.
# %W~<pattern>  Add key write pattern that specifies which keys can be
#               written to. 
#  allkeys      Alias for ~*
#  resetkeys    Flush the list of allowed keys patterns.
#  &<pattern>   Add a glob-style pattern of Pub/Sub channels that can be
#               accessed by the user. It is possible to specify multiple channel
#               patterns.
#  allchannels  Alias for &*
#  resetchannels            Flush the list of allowed channel patterns.
#  ><password>  Add this password to the list of valid password for the user.
#               For example >mypass will add "mypass" to the list.
#               This directive clears the "nopass" flag (see later).
#  <<password>  Remove this password from the list of valid passwords.
#  nopass       All the set passwords of the user are removed, and the user
#               is flagged as requiring no password: it means that every
#               password will work against this user. If this directive is
#               used for the default user, every new connection will be
#               immediately authenticated with the default user without
#               any explicit AUTH command required. Note that the "resetpass"
#               directive will clear this condition.
#  resetpass    Flush the list of allowed passwords. Moreover removes the
#               "nopass" status. After "resetpass" the user has no associated
#               passwords and there is no way to authenticate without adding
#               some password (or setting it as "nopass" later).
#  reset        Performs the following actions: resetpass, resetkeys, off,
#               -@all. The user returns to the same state it has immediately
#               after its creation.
# (<options>)   Create a new selector with the options specified within the
#               parentheses and attach it to the user. Each option should be 
#               space separated. The first character must be ( and the last 
#               character must be ).
# clearselectors            Remove all of the currently attached selectors. 
#                           Note this does not change the "root" user permissions,
#                           which are the permissions directly applied onto the
#                           user (outside the parentheses).
#
# ACL rules can be specified in any order: for instance you can start with
# passwords, then flags, or key patterns. However note that the additive
# and subtractive rules will CHANGE MEANING depending on the ordering.
# For instance see the following example:
#
#   user alice on +@all -DEBUG ~* >somepassword
#
# This will allow "alice" to use all the commands with the exception of the
# DEBUG command, since +@all added all the commands to the set of the commands
# alice can use, and later DEBUG was removed. However if we invert the order
# of two ACL rules the result will be different:
#
#   user alice on -DEBUG +@all ~* >somepassword
#
# Now DEBUG was removed when alice had yet no commands in the set of allowed
# commands, later all the commands are added, so the user will be able to
# execute everything.
#
# Basically ACL rules are processed left-to-right.
#
# The following is a list of command categories and their meanings:
# * keyspace - Writing or reading from keys, databases, or their metadata 
#     in a type agnostic way. Includes DEL, RESTORE, DUMP, RENAME, EXISTS, DBSIZE,
#     KEYS, EXPIRE, TTL, FLUSHALL, etc. Commands that may modify the keyspace,
#     key or metadata will also have `write` category. Commands that only read
#     the keyspace, key or metadata will have the `read` category.
# * read - Reading from keys (values or metadata). Note that commands that don't
#     interact with keys, will not have either `read` or `write`.
# * write - Writing to keys (values or metadata)
# * admin - Administrative commands. Normal applications will never need to use
#     these. Includes REPLICAOF, CONFIG, DEBUG, SAVE, MONITOR, ACL, SHUTDOWN, etc.
# * dangerous - Potentially dangerous (each should be considered with care for
#     various reasons). This includes FLUSHALL, MIGRATE, RESTORE, SORT, KEYS,
#     CLIENT, DEBUG, INFO, CONFIG, SAVE, REPLICAOF, etc.
# * connection - Commands affecting the connection or other connections.
#     This includes AUTH, SELECT, COMMAND, CLIENT, ECHO, PING, etc.
# * blocking - Potentially blocking the connection until released by another
#     command.
# * fast - Fast O(1) commands. May loop on the number of arguments, but not the
#     number of elements in the key.
# * slow - All commands that are not Fast.
# * pubsub - PUBLISH / SUBSCRIBE related
# * transaction - WATCH / MULTI / EXEC related commands.
# * scripting - Scripting related.
# * set - Data type: sets related.
# * sortedset - Data type: zsets related.
# * list - Data type: lists related.
# * hash - Data type: hashes related.
# * string - Data type: strings related.
# * bitmap - Data type: bitmaps related.
# * hyperloglog - Data type: hyperloglog related.
# * geo - Data type: geo related.
# * stream - Data type: streams related.
#
# For more information about ACL configuration please refer to
# the Redis web site at https://redis.io/topics/acl

# ACL LOG
#
# The ACL Log tracks failed commands and authentication events associated
# with ACLs. The ACL Log is useful to troubleshoot failed commands blocked
# by ACLs. The ACL Log is stored in memory. You can reclaim memory with
# ACL LOG RESET. Define the maximum entry length of the ACL Log below.
acllog-max-len 128

# Using an external ACL file
#
# Instead of configuring users here in this file, it is possible to use
# a stand-alone file just listing users. The two methods cannot be mixed:
# if you configure users here and at the same time you activate the external
# ACL file, the server will refuse to start.
#
# The format of the external ACL user file is exactly the same as the
# format that is used inside redis.conf to describe users.
#
# aclfile /etc/redis/users.acl

# IMPORTANT NOTE: starting with Redis 6 "requirepass" is just a compatibility
# layer on top of the new ACL system. The option effect will be just setting
# the password for the default user. Clients will still authenticate using
# AUTH <password> as usually, or more explicitly with AUTH default <password>
# if they follow the new protocol: both will work.
#
# The requirepass is not compatible with aclfile option and the ACL LOAD
# command, these will cause requirepass to be ignored.
#
# requirepass foobared

# New users are initialized with restrictive permissions by default, via the
# equivalent of this ACL rule 'off resetkeys -@all'. Starting with Redis 6.2, it
# is possible to manage access to Pub/Sub channels with ACL rules as well. The
# default Pub/Sub channels permission if new users is controlled by the
# acl-pubsub-default configuration directive, which accepts one of these values:
#
# allchannels: grants access to all Pub/Sub channels
# resetchannels: revokes access to all Pub/Sub channels
#
# From Redis 7.0, acl-pubsub-default defaults to 'resetchannels' permission.
#
# acl-pubsub-default resetchannels

# Command renaming (DEPRECATED).
#
# ------------------------------------------------------------------------
# WARNING: avoid using this option if possible. Instead use ACLs to remove
# commands from the default user, and put them only in some admin user you
# create for administrative purposes.
# ------------------------------------------------------------------------
#
# It is possible to change the name of dangerous commands in a shared
# environment. For instance the CONFIG command may be renamed into something
# hard to guess so that it will still be available for internal-use tools
# but not available for general clients.
#
# Example:
#
# rename-command CONFIG b840fc02d524045429941cc15f59e41cb7be6c52
#
# It is also possible to completely kill a command by renaming it into
# an empty string:
#
# rename-command CONFIG ""
#
# Please note that changing the name of commands that are logged into the
# AOF file or transmitted to replicas may cause problems.

################################### CLIENTS ####################################

# Set the max number of connected clients at the same time. By default
# this limit is set to 10000 clients, however if the Redis server is not
# able to configure the process file limit to allow for the specified limit
# the max number of allowed clients is set to the current file limit
# minus 32 (as Redis reserves a few file descriptors for internal uses).
#
# Once the limit is reached Redis will close all the new connections sending
# an error 'max number of clients reached'.
#
# IMPORTANT: When Redis Cluster is used, the max number of connections is also
# shared with the cluster bus: every node in the cluster will use two
# connections, one incoming and another outgoing. It is important to size the
# limit accordingly in case of very large clusters.
#
# maxclients 10000

############################## MEMORY MANAGEMENT ################################

# Set a memory usage limit to the specified amount of bytes.
# When the memory limit is reached Redis will try to remove keys
# according to the eviction policy selected (see maxmemory-policy).
#
# If Redis can't remove keys according to the policy, or if the policy is
# set to 'noeviction', Redis will start to reply with errors to commands
# that would use more memory, like SET, LPUSH, and so on, and will continue
# to reply to read-only commands like GET.
#
# This option is usually useful when using Redis as an LRU or LFU cache, or to
# set a hard memory limit for an instance (using the 'noeviction' policy).
#
# WARNING: If you have replicas attached to an instance with maxmemory on,
# the size of the output buffers needed to feed the replicas are subtracted
# from the used memory count, so that network problems / resyncs will
# not trigger a loop where keys are evicted, and in turn the output
# buffer of replicas is full with DELs of keys evicted triggering the deletion
# of more keys, and so forth until the database is completely emptied.
#
# In short... if you have replicas attached it is suggested that you set a lower
# limit for maxmemory so that there is some free RAM on the system for replica
# output buffers (but this is not needed if the policy is 'noeviction').
#
# maxmemory <bytes>

# MAXMEMORY POLICY: how Redis will select what to remove when maxmemory
# is reached. You can select one from the following behaviors:
#
# volatile-lru -> Evict using approximated LRU, only keys with an expire set.
# allkeys-lru -> Evict any key using approximated LRU.
# volatile-lfu -> Evict using approximated LFU, only keys with an expire set.
# allkeys-lfu -> Evict any key using approximated LFU.
# volatile-random -> Remove a random key having an expire set.
# allkeys-random -> Remove a random key, any key.
# volatile-ttl -> Remove the key with the nearest expire time (minor TTL)
# noeviction -> Don't evict anything, just return an error on write operations.
#
# LRU means Least Recently Used
# LFU means Least Frequently Used
#
# Both LRU, LFU and volatile-ttl are implemented using approximated
# randomized algorithms.
#
# Note: with any of the above policies, when there are no suitable keys for
# eviction, Redis will return an error on write operations that require
# more memory. These are usually commands that create new keys, add data or
# modify existing keys. A few examples are: SET, INCR, HSET, LPUSH, SUNIONSTORE,
# SORT (due to the STORE argument), and EXEC (if the transaction includes any
# command that requires memory).
#
# The default is:
#
# maxmemory-policy noeviction

# LRU, LFU and minimal TTL algorithms are not precise algorithms but approximated
# algorithms (in order to save memory), so you can tune it for speed or
# accuracy. By default Redis will check five keys and pick the one that was
# used least recently, you can change the sample size using the following
# configuration directive.
#
# The default of 5 produces good enough results. 10 Approximates very closely
# true LRU but costs more CPU. 3 is faster but not very accurate.
#
# maxmemory-samples 5

# Eviction processing is designed to function well with the default setting.
# If there is an unusually large amount of write traffic, this value may need to
# be increased.  Decreasing this value may reduce latency at the risk of
# eviction processing effectiveness
#   0 = minimum latency, 10 = default, 100 = process without regard to latency
#
# maxmemory-eviction-tenacity 10

# Starting from Redis 5, by default a replica will ignore its maxmemory setting
# (unless it is promoted to master after a failover or manually). It means
# that the eviction of keys will be just handled by the master, sending the
# DEL commands to the replica as keys evict in the master side.
#
# This behavior ensures that masters and replicas stay consistent, and is usually
# what you want, however if your replica is writable, or you want the replica
# to have a different memory setting, and you are sure all the writes performed
# to the replica are idempotent, then you may change this default (but be sure
# to understand what you are doing).
#
# Note that since the replica by default does not evict, it may end using more
# memory than the one set via maxmemory (there are certain buffers that may
# be larger on the replica, or data structures may sometimes take more memory
# and so forth). So make sure you monitor your replicas and make sure they
# have enough memory to never hit a real out-of-memory condition before the
# master hits the configured maxmemory setting.
#
# replica-ignore-maxmemory yes

# Redis reclaims expired keys in two ways: upon access when those keys are
# found to be expired, and also in background, in what is called the
# "active expire key". The key space is slowly and interactively scanned
# looking for expired keys to reclaim, so that it is possible to free memory
# of keys that are expired and will never be accessed again in a short time.
#
# The default effort of the expire cycle will try to avoid having more than
# ten percent of expired keys still in memory, and will try to avoid consuming
# more than 25% of total memory and to add latency to the system. However
# it is possible to increase the expire "effort" that is normally set to
# "1", to a greater value, up to the value "10". At its maximum value the
# system will use more CPU, longer cycles (and technically may introduce
# more latency), and will tolerate less already expired keys still present
# in the system. It's a tradeoff between memory, CPU and latency.
#
# active-expire-effort 1

############################# LAZY FREEING ####################################

# Redis has two primitives to delete keys. One is called DEL and is a blocking
# deletion of the object. It means that the server stops processing new commands
# in order to reclaim all the memory associated with an object in a synchronous
# way. If the key deleted is associated with a small object, the time needed
# in order to execute the DEL command is very small and comparable to most other
# O(1) or O(log_N) commands in Redis. However if the key is associated with an
# aggregated value containing millions of elements, the server can block for
# a long time (even seconds) in order to complete the operation.
#
# For the above reasons Redis also offers non blocking deletion primitives
# such as UNLINK (non blocking DEL) and the ASYNC option of FLUSHALL and
# FLUSHDB commands, in order to reclaim memory in background. Those commands
# are executed in constant time. Another thread will incrementally free the
# object in the background as fast as possible.
#
# DEL, UNLINK and ASYNC option of FLUSHALL and FLUSHDB are user-controlled.
# It's up to the design of the application to understand when it is a good
# idea to use one or the other. However the Redis server sometimes has to
# delete keys or flush the whole database as a side effect of other operations.
# Specifically Redis deletes objects independently of a user call in the
# following scenarios:
#
# 1) On eviction, because of the maxmemory and maxmemory policy configurations,
#    in order to make room for new data, without going over the specified
#    memory limit.
# 2) Because of expire: when a key with an associated time to live (see the
#    EXPIRE command) must be deleted from memory.
# 3) Because of a side effect of a command that stores data on a key that may
#    already exist. For example the RENAME command may delete the old key
#    content when it is replaced with another one. Similarly SUNIONSTORE
#    or SORT with STORE option may delete existing keys. The SET command
#    itself removes any old content of the specified key in order to replace
#    it with the specified string.
# 4) During replication, when a replica performs a full resynchronization with
#    its master, the content of the whole database is removed in order to
#    load the RDB file just transferred.
#
# In all the above cases the default is to delete objects in a blocking way,
# like if DEL was called. However you can configure each case specifically
# in order to instead release memory in a non-blocking way like if UNLINK
# was called, using the following configuration directives.

lazyfree-lazy-eviction no
lazyfree-lazy-expire no
lazyfree-lazy-server-del no
replica-lazy-flush no

# It is also possible, for the case when to replace the user code DEL calls
# with UNLINK calls is not easy, to modify the default behavior of the DEL
# command to act exactly like UNLINK, using the following configuration
# directive:

lazyfree-lazy-user-del no

# FLUSHDB, FLUSHALL, SCRIPT FLUSH and FUNCTION FLUSH support both asynchronous and synchronous
# deletion, which can be controlled by passing the [SYNC|ASYNC] flags into the
# commands. When neither flag is passed, this directive will be used to determine
# if the data should be deleted asynchronously.

lazyfree-lazy-user-flush no

################################ THREADED I/O #################################

# Redis is mostly single threaded, however there are certain threaded
# operations such as UNLINK, slow I/O accesses and other things that are
# performed on side threads.
#
# Now it is also possible to handle Redis clients socket reads and writes
# in different I/O threads. Since especially writing is so slow, normally
# Redis users use pipelining in order to speed up the Redis performances per
# core, and spawn multiple instances in order to scale more. Using I/O
# threads it is possible to easily speedup two times Redis without resorting
# to pipelining nor sharding of the instance.
#
# By default threading is disabled, we suggest enabling it only in machines
# that have at least 4 or more cores, leaving at least one spare core.
# Using more than 8 threads is unlikely to help much. We also recommend using
# threaded I/O only if you actually have performance problems, with Redis
# instances being able to use a quite big percentage of CPU time, otherwise
# there is no point in using this feature.
#
# So for instance if you have a four cores boxes, try to use 2 or 3 I/O
# threads, if you have a 8 cores, try to use 6 threads. In order to
# enable I/O threads use the following configuration directive:
#
# io-threads 4
#
# Setting io-threads to 1 will just use the main thread as usual.
# When I/O threads are enabled, we only use threads for writes, that is
# to thread the write(2) syscall and transfer the client buffers to the
# socket. However it is also possible to enable threading of reads and
# protocol parsing using the following configuration directive, by setting
# it to yes:
#
# io-threads-do-reads no
#
# Usually threading reads doesn't help much.
#
# NOTE 1: This configuration directive cannot be changed at runtime via
# CONFIG SET. Also, this feature currently does not work when SSL is
# enabled.
#
# NOTE 2: If you want to test the Redis speedup using redis-benchmark, make
# sure you also run the benchmark itself in threaded mode, using the
# --threads option to match the number of Redis threads, otherwise you'll not
# be able to notice the improvements.

############################ KERNEL OOM CONTROL ##############################

# On Linux, it is possible to hint the kernel OOM killer on what processes
# should be killed first when out of memory.
#
# Enabling this feature makes Redis actively control the oom_score_adj value
# for all its processes, depending on their role. The default scores will
# attempt to have background child processes killed before all others, and
# replicas killed before masters.
#
# Redis supports these options:
#
# no:       Don't make changes to oom-score-adj (default).
# yes:      Alias to "relative" see below.
# absolute: Values in oom-score-adj-values are written as is to the kernel.
# relative: Values are used relative to the initial value of oom_score_adj when
#           the server starts and are then clamped to a range of -1000 to 1000.
#           Because typically the initial value is 0, they will often match the
#           absolute values.
oom-score-adj no

# When oom-score-adj is used, this directive controls the specific values used
# for master, replica and background child processes. Values range -2000 to
# 2000 (higher means more likely to be killed).
#
# Unprivileged processes (not root, and without CAP_SYS_RESOURCE capabilities)
# can freely increase their value, but not decrease it below its initial
# settings. This means that setting oom-score-adj to "relative" and setting the
# oom-score-adj-values to positive values will always succeed.
oom-score-adj-values 0 200 800


#################### KERNEL transparent hugepage CONTROL ######################

# Usually the kernel Transparent Huge Pages control is set to "madvise" or
# or "never" by default (/sys/kernel/mm/transparent_hugepage/enabled), in which
# case this config has no effect. On systems in which it is set to "always",
# redis will attempt to disable it specifically for the redis process in order
# to avoid latency problems specifically with fork(2) and CoW.
# If for some reason you prefer to keep it enabled, you can set this config to
# "no" and the kernel global to "always".

disable-thp yes

############################## APPEND ONLY MODE ###############################

# By default Redis asynchronously dumps the dataset on disk. This mode is
# good enough in many applications, but an issue with the Redis process or
# a power outage may result into a few minutes of writes lost (depending on
# the configured save points).
#
# The Append Only File is an alternative persistence mode that provides
# much better durability. For instance using the default data fsync policy
# (see later in the config file) Redis can lose just one second of writes in a
# dramatic event like a server power outage, or a single write if something
# wrong with the Redis process itself happens, but the operating system is
# still running correctly.
#
# AOF and RDB persistence can be enabled at the same time without problems.
# If the AOF is enabled on startup Redis will load the AOF, that is the file
# with the better durability guarantees.
#
# Please check https://redis.io/topics/persistence for more information.

appendonly no

# The base name of the append only file.
#
# Redis 7 and newer use a set of append-only files to persist the dataset
# and changes applied to it. There are two basic types of files in use:
#
# - Base files, which are a snapshot representing the complete state of the
#   dataset at the time the file was created. Base files can be either in
#   the form of RDB (binary serialized) or AOF (textual commands).
# - Incremental files, which contain additional commands that were applied
#   to the dataset following the previous file.
#
# In addition, manifest files are used to track the files and the order in
# which they were created and should be applied.
#
# Append-only file names are created by Redis following a specific pattern.
# The file name's prefix is based on the 'appendfilename' configuration
# parameter, followed by additional information about the sequence and type.
#
# For example, if appendfilename is set to appendonly.aof, the following file
# names could be derived:
#
# - appendonly.aof.1.base.rdb as a base file.
# - appendonly.aof.1.incr.aof, appendonly.aof.2.incr.aof as incremental files.
# - appendonly.aof.manifest as a manifest file.

appendfilename "appendonly.aof"

# For convenience, Redis stores all persistent append-only files in a dedicated
# directory. The name of the directory is determined by the appenddirname
# configuration parameter.

appenddirname "appendonlydir"

# The fsync() call tells the Operating System to actually write data on disk
# instead of waiting for more data in the output buffer. Some OS will really flush
# data on disk, some other OS will just try to do it ASAP.
#
# Redis supports three different modes:
#
# no: don't fsync, just let the OS flush the data when it wants. Faster.
# always: fsync after every write to the append only log. Slow, Safest.
# everysec: fsync only one time every second. Compromise.
#
# The default is "everysec", as that's usually the right compromise between
# speed and data safety. It's up to you to understand if you can relax this to
# "no" that will let the operating system flush the output buffer when
# it wants, for better performances (but if you can live with the idea of
# some data loss consider the default persistence mode that's snapshotting),
# or on the contrary, use "always" that's very slow but a bit safer than
# everysec.
#
# More details please check the following article:
# http://antirez.com/post/redis-persistence-demystified.html
#
# If unsure, use "everysec".

# appendfsync always
appendfsync everysec
# appendfsync no

# When the AOF fsync policy is set to always or everysec, and a background
# saving process (a background save or AOF log background rewriting) is
# performing a lot of I/O against the disk, in some Linux configurations
# Redis may block too long on the fsync() call. Note that there is no fix for
# this currently, as even performing fsync in a different thread will block
# our synchronous write(2) call.
#
# In order to mitigate this problem it's possible to use the following option
# that will prevent fsync() from being called in the main process while a
# BGSAVE or BGREWRITEAOF is in progress.
#
# This means that while another child is saving, the durability of Redis is
# the same as "appendfsync no". In practical terms, this means that it is
# possible to lose up to 30 seconds of log in the worst scenario (with the
# default Linux settings).
#
# If you have latency problems turn this to "yes". Otherwise leave it as
# "no" that is the safest pick from the point of view of durability.

no-appendfsync-on-rewrite no

# Automatic rewrite of the append only file.
# Redis is able to automatically rewrite the log file implicitly calling
# BGREWRITEAOF when the AOF log size grows by the specified percentage.
#
# This is how it works: Redis remembers the size of the AOF file after the
# latest rewrite (if no rewrite has happened since the restart, the size of
# the AOF at startup is used).
#
# This base size is compared to the current size. If the current size is
# bigger than the specified percentage, the rewrite is triggered. Also
# you need to specify a minimal size for the AOF file to be rewritten, this
# is useful to avoid rewriting the AOF file even if the percentage increase
# is reached but it is still pretty small.
#
# Specify a percentage of zero in order to disable the automatic AOF
# rewrite feature.

auto-aof-rewrite-percentage 100
auto-aof-rewrite-min-size 64mb

# An AOF file may be found to be truncated at the end during the Redis
# startup process, when the AOF data gets loaded back into memory.
# This may happen when the system where Redis is running
# crashes, especially when an ext4 filesystem is mounted without the
# data=ordered option (however this can't happen when Redis itself
# crashes or aborts but the operating system still works correctly).
#
# Redis can either exit with an error when this happens, or load as much
# data as possible (the default now) and start if the AOF file is found
# to be truncated at the end. The following option controls this behavior.
#
# If aof-load-truncated is set to yes, a truncated AOF file is loaded and
# the Redis server starts emitting a log to inform the user of the event.
# Otherwise if the option is set to no, the server aborts with an error
# and refuses to start. When the option is set to no, the user requires
# to fix the AOF file using the "redis-check-aof" utility before to restart
# the server.
#
# Note that if the AOF file will be found to be corrupted in the middle
# the server will still exit with an error. This option only applies when
# Redis will try to read more data from the AOF file but not enough bytes
# will be found.
aof-load-truncated yes

# Redis can create append-only base files in either RDB or AOF formats. Using
# the RDB format is always faster and more efficient, and disabling it is only
# supported for backward compatibility purposes.
aof-use-rdb-preamble yes

# Redis supports recording timestamp annotations in the AOF to support restoring
# the data from a specific point-in-time. However, using this capability changes
# the AOF format in a way that may not be compatible with existing AOF parsers.
aof-timestamp-enabled no

################################ SHUTDOWN #####################################

# Maximum time to wait for replicas when shutting down, in seconds.
#
# During shut down, a grace period allows any lagging replicas to catch up with
# the latest replication offset before the master exists. This period can
# prevent data loss, especially for deployments without configured disk backups.
#
# The 'shutdown-timeout' value is the grace period's duration in seconds. It is
# only applicable when the instance has replicas. To disable the feature, set
# the value to 0.
#
# shutdown-timeout 10

# When Redis receives a SIGINT or SIGTERM, shutdown is initiated and by default
# an RDB snapshot is written to disk in a blocking operation if save points are configured.
# The options used on signaled shutdown can include the following values:
# default:  Saves RDB snapshot only if save points are configured.
#           Waits for lagging replicas to catch up.
# save:     Forces a DB saving operation even if no save points are configured.
# nosave:   Prevents DB saving operation even if one or more save points are configured.
# now:      Skips waiting for lagging replicas.
# force:    Ignores any errors that would normally prevent the server from exiting.
#
# Any combination of values is allowed as long as "save" and "nosave" are not set simultaneously.
# Example: "nosave force now"
#
# shutdown-on-sigint default
# shutdown-on-sigterm default

################ NON-DETERMINISTIC LONG BLOCKING COMMANDS #####################

# Maximum time in milliseconds for EVAL scripts, functions and in some cases
# modules' commands before Redis can start processing or rejecting other clients.
#
# If the maximum execution time is reached Redis will start to reply to most
# commands with a BUSY error.
#
# In this state Redis will only allow a handful of commands to be executed.
# For instance, SCRIPT KILL, FUNCTION KILL, SHUTDOWN NOSAVE and possibly some
# module specific 'allow-busy' commands.
#
# SCRIPT KILL and FUNCTION KILL will only be able to stop a script that did not
# yet call any write commands, so SHUTDOWN NOSAVE may be the only way to stop
# the server in the case a write command was already issued by the script when
# the user doesn't want to wait for the natural termination of the script.
#
# The default is 5 seconds. It is possible to set it to 0 or a negative value
# to disable this mechanism (uninterrupted execution). Note that in the past
# this config had a different name, which is now an alias, so both of these do
# the same:
# lua-time-limit 5000
# busy-reply-threshold 5000

################################ REDIS CLUSTER  ###############################

# Normal Redis instances can't be part of a Redis Cluster; only nodes that are
# started as cluster nodes can. In order to start a Redis instance as a
# cluster node enable the cluster support uncommenting the following:
#
# cluster-enabled yes

# Every cluster node has a cluster configuration file. This file is not
# intended to be edited by hand. It is created and updated by Redis nodes.
# Every Redis Cluster node requires a different cluster configuration file.
# Make sure that instances running in the same system do not have
# overlapping cluster configuration file names.
#
# cluster-config-file nodes-6379.conf

# Cluster node timeout is the amount of milliseconds a node must be unreachable
# for it to be considered in failure state.
# Most other internal time limits are a multiple of the node timeout.
#
# cluster-node-timeout 15000

# The cluster port is the port that the cluster bus will listen for inbound connections on. When set 
# to the default value, 0, it will be bound to the command port + 10000. Setting this value requires 
# you to specify the cluster bus port when executing cluster meet.
# cluster-port 0

# A replica of a failing master will avoid to start a failover if its data
# looks too old.
#
# There is no simple way for a replica to actually have an exact measure of
# its "data age", so the following two checks are performed:
#
# 1) If there are multiple replicas able to failover, they exchange messages
#    in order to try to give an advantage to the replica with the best
#    replication offset (more data from the master processed).
#    Replicas will try to get their rank by offset, and apply to the start
#    of the failover a delay proportional to their rank.
#
# 2) Every single replica computes the time of the last interaction with
#    its master. This can be the last ping or command received (if the master
#    is still in the "connected" state), or the time that elapsed since the
#    disconnection with the master (if the replication link is currently down).
#    If the last interaction is too old, the replica will not try to failover
#    at all.
#
# The point "2" can be tuned by user. Specifically a replica will not perform
# the failover if, since the last interaction with the master, the time
# elapsed is greater than:
#
#   (node-timeout * cluster-replica-validity-factor) + repl-ping-replica-period
#
# So for example if node-timeout is 30 seconds, and the cluster-replica-validity-factor
# is 10, and assuming a default repl-ping-replica-period of 10 seconds, the
# replica will not try to failover if it was not able to talk with the master
# for longer than 310 seconds.
#
# A large cluster-replica-validity-factor may allow replicas with too old data to failover
# a master, while a too small value may prevent the cluster from being able to
# elect a replica at all.
#
# For maximum availability, it is possible to set the cluster-replica-validity-factor
# to a value of 0, which means, that replicas will always try to failover the
# master regardless of the last time they interacted with the master.
# (However they'll always try to apply a delay proportional to their
# offset rank).
#
# Zero is the only value able to guarantee that when all the partitions heal
# the cluster will always be able to continue.
#
# cluster-replica-validity-factor 10

# Cluster replicas are able to migrate to orphaned masters, that are masters
# that are left without working replicas. This improves the cluster ability
# to resist to failures as otherwise an orphaned master can't be failed over
# in case of failure if it has no working replicas.
#
# Replicas migrate to orphaned masters only if there are still at least a
# given number of other working replicas for their old master. This number
# is the "migration barrier". A migration barrier of 1 means that a replica
# will migrate only if there is at least 1 other working replica for its master
# and so forth. It usually reflects the number of replicas you want for every
# master in your cluster.
#
# Default is 1 (replicas migrate only if their masters remain with at least
# one replica). To disable migration just set it to a very large value or
# set cluster-allow-replica-migration to 'no'.
# A value of 0 can be set but is useful only for debugging and dangerous
# in production.
#
# cluster-migration-barrier 1

# Turning off this option allows to use less automatic cluster configuration.
# It both disables migration to orphaned masters and migration from masters
# that became empty.
#
# Default is 'yes' (allow automatic migrations).
#
# cluster-allow-replica-migration yes

# By default Redis Cluster nodes stop accepting queries if they detect there
# is at least a hash slot uncovered (no available node is serving it).
# This way if the cluster is partially down (for example a range of hash slots
# are no longer covered) all the cluster becomes, eventually, unavailable.
# It automatically returns available as soon as all the slots are covered again.
#
# However sometimes you want the subset of the cluster which is working,
# to continue to accept queries for the part of the key space that is still
# covered. In order to do so, just set the cluster-require-full-coverage
# option to no.
#
# cluster-require-full-coverage yes

# This option, when set to yes, prevents replicas from trying to failover its
# master during master failures. However the replica can still perform a
# manual failover, if forced to do so.
#
# This is useful in different scenarios, especially in the case of multiple
# data center operations, where we want one side to never be promoted if not
# in the case of a total DC failure.
#
# cluster-replica-no-failover no

# This option, when set to yes, allows nodes to serve read traffic while the
# cluster is in a down state, as long as it believes it owns the slots.
#
# This is useful for two cases.  The first case is for when an application
# doesn't require consistency of data during node failures or network partitions.
# One example of this is a cache, where as long as the node has the data it
# should be able to serve it.
#
# The second use case is for configurations that don't meet the recommended
# three shards but want to enable cluster mode and scale later. A
# master outage in a 1 or 2 shard configuration causes a read/write outage to the
# entire cluster without this option set, with it set there is only a write outage.
# Without a quorum of masters, slot ownership will not change automatically.
#
# cluster-allow-reads-when-down no

# This option, when set to yes, allows nodes to serve pubsub shard traffic while
# the cluster is in a down state, as long as it believes it owns the slots.
#
# This is useful if the application would like to use the pubsub feature even when
# the cluster global stable state is not OK. If the application wants to make sure only
# one shard is serving a given channel, this feature should be kept as yes.
#
# cluster-allow-pubsubshard-when-down yes

# Cluster link send buffer limit is the limit on the memory usage of an individual
# cluster bus link's send buffer in bytes. Cluster links would be freed if they exceed
# this limit. This is to primarily prevent send buffers from growing unbounded on links
# toward slow peers (E.g. PubSub messages being piled up).
# This limit is disabled by default. Enable this limit when 'mem_cluster_links' INFO field
# and/or 'send-buffer-allocated' entries in the 'CLUSTER LINKS` command output continuously increase.
# Minimum limit of 1gb is recommended so that cluster link buffer can fit in at least a single
# PubSub message by default. (client-query-buffer-limit default value is 1gb)
#
# cluster-link-sendbuf-limit 0
 
# Clusters can configure their announced hostname using this config. This is a common use case for 
# applications that need to use TLS Server Name Indication (SNI) or dealing with DNS based
# routing. By default this value is only shown as additional metadata in the CLUSTER SLOTS
# command, but can be changed using 'cluster-preferred-endpoint-type' config. This value is 
# communicated along the clusterbus to all nodes, setting it to an empty string will remove 
# the hostname and also propagate the removal.
#
# cluster-announce-hostname ""

# Clusters can advertise how clients should connect to them using either their IP address,
# a user defined hostname, or by declaring they have no endpoint. Which endpoint is
# shown as the preferred endpoint is set by using the cluster-preferred-endpoint-type
# config with values 'ip', 'hostname', or 'unknown-endpoint'. This value controls how
# the endpoint returned for MOVED/ASKING requests as well as the first field of CLUSTER SLOTS. 
# If the preferred endpoint type is set to hostname, but no announced hostname is set, a '?' 
# will be returned instead.
#
# When a cluster advertises itself as having an unknown endpoint, it's indicating that
# the server doesn't know how clients can reach the cluster. This can happen in certain 
# networking situations where there are multiple possible routes to the node, and the 
# server doesn't know which one the client took. In this case, the server is expecting
# the client to reach out on the same endpoint it used for making the last request, but use
# the port provided in the response.
#
# cluster-preferred-endpoint-type ip

# In order to setup your cluster make sure to read the documentation
# available at https://redis.io web site.

########################## CLUSTER DOCKER/NAT support  ########################

# In certain deployments, Redis Cluster nodes address discovery fails, because
# addresses are NAT-ted or because ports are forwarded (the typical case is
# Docker and other containers).
#
# In order to make Redis Cluster working in such environments, a static
# configuration where each node knows its public address is needed. The
# following four options are used for this scope, and are:
#
# * cluster-announce-ip
# * cluster-announce-port
# * cluster-announce-tls-port
# * cluster-announce-bus-port
#
# Each instructs the node about its address, client ports (for connections
# without and with TLS) and cluster message bus port. The information is then
# published in the header of the bus packets so that other nodes will be able to
# correctly map the address of the node publishing the information.
#
# If cluster-tls is set to yes and cluster-announce-tls-port is omitted or set
# to zero, then cluster-announce-port refers to the TLS port. Note also that
# cluster-announce-tls-port has no effect if cluster-tls is set to no.
#
# If the above options are not used, the normal Redis Cluster auto-detection
# will be used instead.
#
# Note that when remapped, the bus port may not be at the fixed offset of
# clients port + 10000, so you can specify any port and bus-port depending
# on how they get remapped. If the bus-port is not set, a fixed offset of
# 10000 will be used as usual.
#
# Example:
#
# cluster-announce-ip 10.1.1.5
# cluster-announce-tls-port 6379
# cluster-announce-port 0
# cluster-announce-bus-port 6380

################################## SLOW LOG ###################################

# The Redis Slow Log is a system to log queries that exceeded a specified
# execution time. The execution time does not include the I/O operations
# like talking with the client, sending the reply and so forth,
# but just the time needed to actually execute the command (this is the only
# stage of command execution where the thread is blocked and can not serve
# other requests in the meantime).
#
# You can configure the slow log with two parameters: one tells Redis
# what is the execution time, in microseconds, to exceed in order for the
# command to get logged, and the other parameter is the length of the
# slow log. When a new command is logged the oldest one is removed from the
# queue of logged commands.

# The following time is expressed in microseconds, so 1000000 is equivalent
# to one second. Note that a negative number disables the slow log, while
# a value of zero forces the logging of every command.
slowlog-log-slower-than 10000

# There is no limit to this length. Just be aware that it will consume memory.
# You can reclaim memory used by the slow log with SLOWLOG RESET.
slowlog-max-len 128

################################ LATENCY MONITOR ##############################

# The Redis latency monitoring subsystem samples different operations
# at runtime in order to collect data related to possible sources of
# latency of a Redis instance.
#
# Via the LATENCY command this information is available to the user that can
# print graphs and obtain reports.
#
# The system only logs operations that were performed in a time equal or
# greater than the amount of milliseconds specified via the
# latency-monitor-threshold configuration directive. When its value is set
# to zero, the latency monitor is turned off.
#
# By default latency monitoring is disabled since it is mostly not needed
# if you don't have latency issues, and collecting data has a performance
# impact, that while very small, can be measured under big load. Latency
# monitoring can easily be enabled at runtime using the command
# "CONFIG SET latency-monitor-threshold <milliseconds>" if needed.
latency-monitor-threshold 0

################################ LATENCY TRACKING ##############################

# The Redis extended latency monitoring tracks the per command latencies and enables
# exporting the percentile distribution via the INFO latencystats command,
# and cumulative latency distributions (histograms) via the LATENCY command.
#
# By default, the extended latency monitoring is enabled since the overhead
# of keeping track of the command latency is very small.
# latency-tracking yes

# By default the exported latency percentiles via the INFO latencystats command
# are the p50, p99, and p999.
# latency-tracking-info-percentiles 50 99 99.9

############################# EVENT NOTIFICATION ##############################

# Redis can notify Pub/Sub clients about events happening in the key space.
# This feature is documented at https://redis.io/topics/notifications
#
# For instance if keyspace events notification is enabled, and a client
# performs a DEL operation on key "foo" stored in the Database 0, two
# messages will be published via Pub/Sub:
#
# PUBLISH __keyspace@0__:foo del
# PUBLISH __keyevent@0__:del foo
#
# It is possible to select the events that Redis will notify among a set
# of classes. Every class is identified by a single character:
#
#  K     Keyspace events, published with __keyspace@<db>__ prefix.
#  E     Keyevent events, published with __keyevent@<db>__ prefix.
#  g     Generic commands (non-type specific) like DEL, EXPIRE, RENAME, ...
#  $     String commands
#  l     List commands
#  s     Set commands
#  h     Hash commands
#  z     Sorted set commands
#  x     Expired events (events generated every time a key expires)
#  e     Evicted events (events generated when a key is evicted for maxmemory)
#  n     New key events (Note: not included in the 'A' class)
#  t     Stream commands
#  d     Module key type events
#  m     Key-miss events (Note: It is not included in the 'A' class)
#  A     Alias for g$lshzxetd, so that the "AKE" string means all the events
#        (Except key-miss events which are excluded from 'A' due to their
#         unique nature).
#
#  The "notify-keyspace-events" takes as argument a string that is composed
#  of zero or multiple characters. The empty string means that notifications
#  are disabled.
#
#  Example: to enable list and generic events, from the point of view of the
#           event name, use:
#
#  notify-keyspace-events Elg
#
#  Example 2: to get the stream of the expired keys subscribing to channel
#             name __keyevent@0__:expired use:
#
#  notify-keyspace-events Ex
#
#  By default all notifications are disabled because most users don't need
#  this feature and the feature has some overhead. Note that if you don't
#  specify at least one of K or E, no events will be delivered.
notify-keyspace-events ""

############################### ADVANCED CONFIG ###############################

# Hashes are encoded using a memory efficient data structure when they have a
# small number of entries, and the biggest entry does not exceed a given
# threshold. These thresholds can be configured using the following directives.
hash-max-listpack-entries 512
hash-max-listpack-value 64

# Lists are also encoded in a special way to save a lot of space.
# The number of entries allowed per internal list node can be specified
# as a fixed maximum size or a maximum number of elements.
# For a fixed maximum size, use -5 through -1, meaning:
# -5: max size: 64 Kb  <-- not recommended for normal workloads
# -4: max size: 32 Kb  <-- not recommended
# -3: max size: 16 Kb  <-- probably not recommended
# -2: max size: 8 Kb   <-- good
# -1: max size: 4 Kb   <-- good
# Positive numbers mean store up to _exactly_ that number of elements
# per list node.
# The highest performing option is usually -2 (8 Kb size) or -1 (4 Kb size),
# but if your use case is unique, adjust the settings as necessary.
list-max-listpack-size -2

# Lists may also be compressed.
# Compress depth is the number of quicklist ziplist nodes from *each* side of
# the list to *exclude* from compression.  The head and tail of the list
# are always uncompressed for fast push/pop operations.  Settings are:
# 0: disable all list compression
# 1: depth 1 means "don't start compressing until after 1 node into the list,
#    going from either the head or tail"
#    So: [head]->node->node->...->node->[tail]
#    [head], [tail] will always be uncompressed; inner nodes will compress.
# 2: [head]->[next]->node->node->...->node->[prev]->[tail]
#    2 here means: don't compress head or head->next or tail->prev or tail,
#    but compress all nodes between them.
# 3: [head]->[next]->[next]->node->node->...->node->[prev]->[prev]->[tail]
# etc.
list-compress-depth 0

# Sets have a special encoding in just one case: when a set is composed
# of just strings that happen to be integers in radix 10 in the range
# of 64 bit signed integers.
# The following configuration setting sets the limit in the size of the
# set in order to use this special memory saving encoding.
set-max-intset-entries 512

# Similarly to hashes and lists, sorted sets are also specially encoded in
# order to save a lot of space. This encoding is only used when the length and
# elements of a sorted set are below the following limits:
zset-max-listpack-entries 128
zset-max-listpack-value 64

# HyperLogLog sparse representation bytes limit. The limit includes the
# 16 bytes header. When an HyperLogLog using the sparse representation crosses
# this limit, it is converted into the dense representation.
#
# A value greater than 16000 is totally useless, since at that point the
# dense representation is more memory efficient.
#
# The suggested value is ~ 3000 in order to have the benefits of
# the space efficient encoding without slowing down too much PFADD,
# which is O(N) with the sparse encoding. The value can be raised to
# ~ 10000 when CPU is not a concern, but space is, and the data set is
# composed of many HyperLogLogs with cardinality in the 0 - 15000 range.
hll-sparse-max-bytes 3000

# Streams macro node max size / items. The stream data structure is a radix
# tree of big nodes that encode multiple items inside. Using this configuration
# it is possible to configure how big a single node can be in bytes, and the
# maximum number of items it may contain before switching to a new node when
# appending new stream entries. If any of the following settings are set to
# zero, the limit is ignored, so for instance it is possible to set just a
# max entries limit by setting max-bytes to 0 and max-entries to the desired
# value.
stream-node-max-bytes 4096
stream-node-max-entries 100

# Active rehashing uses 1 millisecond every 100 milliseconds of CPU time in
# order to help rehashing the main Redis hash table (the one mapping top-level
# keys to values). The hash table implementation Redis uses (see dict.c)
# performs a lazy rehashing: the more operation you run into a hash table
# that is rehashing, the more rehashing "steps" are performed, so if the
# server is idle the rehashing is never complete and some more memory is used
# by the hash table.
#
# The default is to use this millisecond 10 times every second in order to
# actively rehash the main dictionaries, freeing memory when possible.
#
# If unsure:
# use "activerehashing no" if you have hard latency requirements and it is
# not a good thing in your environment that Redis can reply from time to time
# to queries with 2 milliseconds delay.
#
# use "activerehashing yes" if you don't have such hard requirements but
# want to free memory asap when possible.
activerehashing yes

# The client output buffer limits can be used to force disconnection of clients
# that are not reading data from the server fast enough for some reason (a
# common reason is that a Pub/Sub client can't consume messages as fast as the
# publisher can produce them).
#
# The limit can be set differently for the three different classes of clients:
#
# normal -> normal clients including MONITOR clients
# replica -> replica clients
# pubsub -> clients subscribed to at least one pubsub channel or pattern
#
# The syntax of every client-output-buffer-limit directive is the following:
#
# client-output-buffer-limit <class> <hard limit> <soft limit> <soft seconds>
#
# A client is immediately disconnected once the hard limit is reached, or if
# the soft limit is reached and remains reached for the specified number of
# seconds (continuously).
# So for instance if the hard limit is 32 megabytes and the soft limit is
# 16 megabytes / 10 seconds, the client will get disconnected immediately
# if the size of the output buffers reach 32 megabytes, but will also get
# disconnected if the client reaches 16 megabytes and continuously overcomes
# the limit for 10 seconds.
#
# By default normal clients are not limited because they don't receive data
# without asking (in a push way), but just after a request, so only
# asynchronous clients may create a scenario where data is requested faster
# than it can read.
#
# Instead there is a default limit for pubsub and replica clients, since
# subscribers and replicas receive data in a push fashion.
#
# Note that it doesn't make sense to set the replica clients output buffer
# limit lower than the repl-backlog-size config (partial sync will succeed
# and then replica will get disconnected).
# Such a configuration is ignored (the size of repl-backlog-size will be used).
# This doesn't have memory consumption implications since the replica client
# will share the backlog buffers memory.
#
# Both the hard or the soft limit can be disabled by setting them to zero.
client-output-buffer-limit normal 0 0 0
client-output-buffer-limit replica 256mb 64mb 60
client-output-buffer-limit pubsub 32mb 8mb 60

# Client query buffers accumulate new commands. They are limited to a fixed
# amount by default in order to avoid that a protocol desynchronization (for
# instance due to a bug in the client) will lead to unbound memory usage in
# the query buffer. However you can configure it here if you have very special
# needs, such us huge multi/exec requests or alike.
#
# client-query-buffer-limit 1gb

# In some scenarios client connections can hog up memory leading to OOM
# errors or data eviction. To avoid this we can cap the accumulated memory
# used by all client connections (all pubsub and normal clients). Once we
# reach that limit connections will be dropped by the server freeing up
# memory. The server will attempt to drop the connections using the most 
# memory first. We call this mechanism "client eviction".
#
# Client eviction is configured using the maxmemory-clients setting as follows:
# 0 - client eviction is disabled (default)
#
# A memory value can be used for the client eviction threshold,
# for example:
# maxmemory-clients 1g
#
# A percentage value (between 1% and 100%) means the client eviction threshold
# is based on a percentage of the maxmemory setting. For example to set client
# eviction at 5% of maxmemory:
# maxmemory-clients 5%

# In the Redis protocol, bulk requests, that are, elements representing single
# strings, are normally limited to 512 mb. However you can change this limit
# here, but must be 1mb or greater
#
# proto-max-bulk-len 512mb

# Redis calls an internal function to perform many background tasks, like
# closing connections of clients in timeout, purging expired keys that are
# never requested, and so forth.
#
# Not all tasks are performed with the same frequency, but Redis checks for
# tasks to perform according to the specified "hz" value.
#
# By default "hz" is set to 10. Raising the value will use more CPU when
# Redis is idle, but at the same time will make Redis more responsive when
# there are many keys expiring at the same time, and timeouts may be
# handled with more precision.
#
# The range is between 1 and 500, however a value over 100 is usually not
# a good idea. Most users should use the default of 10 and raise this up to
# 100 only in environments where very low latency is required.
hz 10

# Normally it is useful to have an HZ value which is proportional to the
# number of clients connected. This is useful in order, for instance, to
# avoid too many clients are processed for each background task invocation
# in order to avoid latency spikes.
#
# Since the default HZ value by default is conservatively set to 10, Redis
# offers, and enables by default, the ability to use an adaptive HZ value
# which will temporarily raise when there are many connected clients.
#
# When dynamic HZ is enabled, the actual configured HZ will be used
# as a baseline, but multiples of the configured HZ value will be actually
# used as needed once more clients are connected. In this way an idle
# instance will use very little CPU time while a busy instance will be
# more responsive.
dynamic-hz yes

# When a child rewrites the AOF file, if the following option is enabled
# the file will be fsync-ed every 4 MB of data generated. This is useful
# in order to commit the file to the disk more incrementally and avoid
# big latency spikes.
aof-rewrite-incremental-fsync yes

# When redis saves RDB file, if the following option is enabled
# the file will be fsync-ed every 4 MB of data generated. This is useful
# in order to commit the file to the disk more incrementally and avoid
# big latency spikes.
rdb-save-incremental-fsync yes

# Redis LFU eviction (see maxmemory setting) can be tuned. However it is a good
# idea to start with the default settings and only change them after investigating
# how to improve the performances and how the keys LFU change over time, which
# is possible to inspect via the OBJECT FREQ command.
#
# There are two tunable parameters in the Redis LFU implementation: the
# counter logarithm factor and the counter decay time. It is important to
# understand what the two parameters mean before changing them.
#
# The LFU counter is just 8 bits per key, it's maximum value is 255, so Redis
# uses a probabilistic increment with logarithmic behavior. Given the value
# of the old counter, when a key is accessed, the counter is incremented in
# this way:
#
# 1. A random number R between 0 and 1 is extracted.
# 2. A probability P is calculated as 1/(old_value*lfu_log_factor+1).
# 3. The counter is incremented only if R < P.
#
# The default lfu-log-factor is 10. This is a table of how the frequency
# counter changes with a different number of accesses with different
# logarithmic factors:
#
# +--------+------------+------------+------------+------------+------------+
# | factor | 100 hits   | 1000 hits  | 100K hits  | 1M hits    | 10M hits   |
# +--------+------------+------------+------------+------------+------------+
# | 0      | 104        | 255        | 255        | 255        | 255        |
# +--------+------------+------------+------------+------------+------------+
# | 1      | 18         | 49         | 255        | 255        | 255        |
# +--------+------------+------------+------------+------------+------------+
# | 10     | 10         | 18         | 142        | 255        | 255        |
# +--------+------------+------------+------------+------------+------------+
# | 100    | 8          | 11         | 49         | 143        | 255        |
# +--------+------------+------------+------------+------------+------------+
#
# NOTE: The above table was obtained by running the following commands:
#
#   redis-benchmark -n 1000000 incr foo
#   redis-cli object freq foo
#
# NOTE 2: The counter initial value is 5 in order to give new objects a chance
# to accumulate hits.
#
# The counter decay time is the time, in minutes, that must elapse in order
# for the key counter to be divided by two (or decremented if it has a value
# less <= 10).
#
# The default value for the lfu-decay-time is 1. A special value of 0 means to
# decay the counter every time it happens to be scanned.
#
# lfu-log-factor 10
# lfu-decay-time 1

########################### ACTIVE DEFRAGMENTATION #######################
#
# What is active defragmentation?
# -------------------------------
#
# Active (online) defragmentation allows a Redis server to compact the
# spaces left between small allocations and deallocations of data in memory,
# thus allowing to reclaim back memory.
#
# Fragmentation is a natural process that happens with every allocator (but
# less so with Jemalloc, fortunately) and certain workloads. Normally a server
# restart is needed in order to lower the fragmentation, or at least to flush
# away all the data and create it again. However thanks to this feature
# implemented by Oran Agra for Redis 4.0 this process can happen at runtime
# in a "hot" way, while the server is running.
#
# Basically when the fragmentation is over a certain level (see the
# configuration options below) Redis will start to create new copies of the
# values in contiguous memory regions by exploiting certain specific Jemalloc
# features (in order to understand if an allocation is causing fragmentation
# and to allocate it in a better place), and at the same time, will release the
# old copies of the data. This process, repeated incrementally for all the keys
# will cause the fragmentation to drop back to normal values.
#
# Important things to understand:
#
# 1. This feature is disabled by default, and only works if you compiled Redis
#    to use the copy of Jemalloc we ship with the source code of Redis.
#    This is the default with Linux builds.
#
# 2. You never need to enable this feature if you don't have fragmentation
#    issues.
#
# 3. Once you experience fragmentation, you can enable this feature when
#    needed with the command "CONFIG SET activedefrag yes".
#
# The configuration parameters are able to fine tune the behavior of the
# defragmentation process. If you are not sure about what they mean it is
# a good idea to leave the defaults untouched.

# Active defragmentation is disabled by default
# activedefrag no

# Minimum amount of fragmentation waste to start active defrag
# active-defrag-ignore-bytes 100mb

# Minimum percentage of fragmentation to start active defrag
# active-defrag-threshold-lower 10

# Maximum percentage of fragmentation at which we use maximum effort
# active-defrag-threshold-upper 100

# Minimal effort for defrag in CPU percentage, to be used when the lower
# threshold is reached
# active-defrag-cycle-min 1

# Maximal effort for defrag in CPU percentage, to be used when the upper
# threshold is reached
# active-defrag-cycle-max 25

# Maximum number of set/hash/zset/list fields that will be processed from
# the main dictionary scan
# active-defrag-max-scan-fields 1000

# Jemalloc background thread for purging will be enabled by default
jemalloc-bg-thread yes

# It is possible to pin different threads and processes of Redis to specific
# CPUs in your system, in order to maximize the performances of the server.
# This is useful both in order to pin different Redis threads in different
# CPUs, but also in order to make sure that multiple Redis instances running
# in the same host will be pinned to different CPUs.
#
# Normally you can do this using the "taskset" command, however it is also
# possible to this via Redis configuration directly, both in Linux and FreeBSD.
#
# You can pin the server/IO threads, bio threads, aof rewrite child process, and
# the bgsave child process. The syntax to specify the cpu list is the same as
# the taskset command:
#
# Set redis server/io threads to cpu affinity 0,2,4,6:
# server_cpulist 0-7:2
#
# Set bio threads to cpu affinity 1,3:
# bio_cpulist 1,3
#
# Set aof rewrite child process to cpu affinity 8,9,10,11:
# aof_rewrite_cpulist 8-11
#
# Set bgsave child process to cpu affinity 1,10,11
# bgsave_cpulist 1,10-11

# In some cases redis will emit warnings and even refuse to start if it detects
# that the system is in bad state, it is possible to suppress these warnings
# by setting the following config which takes a space delimited list of warnings
# to suppress
#
# ignore-warnings ARM64-COW-BUG
```

### `builtin/builtin/redis/pkg.py`

```python
"""
This module provides classes and methods to launch Redis.
Redis cluster is used if the hostfile has many hosts
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class Redis(Application):
    """
    This class provides methods to launch the Ior application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'port',
                'msg': 'The port to use for the cluster',
                'type': int,
                'default': 6379,
                'choices': [],
                'args': [],
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        # Create the redis hostfile
        self.copy_template_file(f'{self.pkg_dir}/config/redis.conf',
                                f'{self.shared_dir}/redis.conf',
                                {
                                    'PORT': self.config['port']
                                })

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        hostfile = self.jarvis.hostfile
        host_str = [f'{host}:{self.config["port"]}' for host in hostfile.hosts]
        host_str = ' '.join(host_str)
        cluster_config_file = f'{self.private_dir}/nodes.conf'
        # Create redis servers
        self.log('Starting individual servers', color=Color.YELLOW)
        cmd = [
            'redis-server',
            f'{self.shared_dir}/redis.conf',
        ]
        if len(hostfile) > 1:
            cmd += [
                f'--cluster-enabled yes',
                f'--cluster-config-file {cluster_config_file}',
                f'--cluster-node-timeout 5000',
            ]

        cmd = ' '.join(cmd)
        Exec(cmd,
             PsshExecInfo(env=self.mod_env,
                          hostfile=hostfile,
                          do_dbg=self.config['do_dbg'],
                          dbg_port=self.config['dbg_port'],
                          exec_async=True))
        self.log(f'Sleeping for {self.config["sleep"]} seconds', color=Color.YELLOW)
        time.sleep(self.config['sleep'])

        # Create redis clients
        if len(hostfile) > 1:
            self.log('Flushing all data and resetting the cluster', color=Color.YELLOW)
            for host in hostfile.hosts:
                Exec(f'redis-cli -p {self.config["port"]} -h {host} flushall',
                     LocalExecInfo(env=self.mod_env,
                                   hostfile=hostfile,
                                   do_dbg=self.config['do_dbg'],
                                   dbg_port=self.config['dbg_port']))
                Exec(f'redis-cli -p {self.config["port"]} -h {host} cluster reset',
                     LocalExecInfo(env=self.mod_env,
                                   hostfile=hostfile,
                                   do_dbg=self.config['do_dbg'],
                                   dbg_port=self.config['dbg_port']))

            self.log('Creating the cluster', color=Color.YELLOW)
            cmd = [
                'redis-cli',
                f'--cluster create {host_str}',
                '--cluster-replicas 0',
                '--cluster-yes'
            ]
            cmd = ' '.join(cmd)
            print(cmd)
            Exec(cmd,
                 LocalExecInfo(env=self.mod_env,
                               hostfile=hostfile,
                               do_dbg=self.config['do_dbg'],
                               dbg_port=self.config['dbg_port']))
            self.log(f'Sleeping for {self.config["sleep"]} seconds', color=Color.YELLOW)
            time.sleep(self.config['sleep'])

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        for i in range(3):
            Kill('redis-server',
                 PsshExecInfo(env=self.env,
                              hostfile=self.jarvis.hostfile))

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass
```

### `builtin/builtin/spark_cluster/pkg.py`

```python
"""
This module provides classes and methods to launch the SparkCluster service.
SparkCluster is ....
"""

from jarvis_cd.basic.pkg import Service
from jarvis_util import *


class SparkCluster(Service):
    """
    This class provides methods to launch the SparkCluster service.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'port',
                'msg': '',
                'type': int,
                'default': 7077,
            },
            {
                'name': 'num_nodes',
                'msg': '',
                'type': int,
                'default': 1,
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        self.config['SPARK_SCRIPTS'] = self.env['SPARK_SCRIPTS']
        self.env['SPARK_MASTER_HOST'] = self.jarvis.hostfile.hosts[0]
        self.env['SPARK_MASTER_PORT'] = '7077'
        self.env['SPARK_WORKER_PORT'] = '7078'

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        # Start the master node
        Exec(f'{self.config["SPARK_SCRIPTS"]}/sbin/start-master.sh',
             PsshExecInfo(env=self.env,
                          hosts=self.jarvis.hostfile.subset(1)))
        time.sleep(1)
        # Start the worker nodes
        Exec(f'{self.config["SPARK_SCRIPTS"]}/sbin/start-worker.sh '
             f'{self.env["SPARK_MASTER_HOST"]}:{self.env["SPARK_MASTER_PORT"]}',
             PsshExecInfo(env=self.mod_env,
                          hosts=self.jarvis.hostfile.subset(self.config['num_nodes'])))
        time.sleep(self.config['sleep'])

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        # Start the master node
        Exec(f'{self.config["SPARK_SCRIPTS"]}/sbin/stop-master.sh',
             PsshExecInfo(env=self.env,
                          hosts=self.jarvis.hostfile.subset(1)))
        # Start the worker nodes
        Exec(f'{self.config["SPARK_SCRIPTS"]}/sbin/stop-worker.sh '
             f'{self.env["SPARK_MASTER_HOST"]}',
             PsshExecInfo(env=self.env,
                          hosts=self.jarvis.hostfile))

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass

    def status(self):
        """
        Check whether or not an application is running. E.g., are OrangeFS
        servers running?

        :return: True or false
        """
        return True
```

### `builtin/builtin/ycsbc/pkg.py`

```python
"""
This module provides classes and methods to launch Redis.
Redis cluster is used if the hostfile has many hosts
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class Ycsbc(Application):
    """
    This class provides methods to launch the Ior application.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'db_name',
                'msg': 'The DB to test',
                'type': str,
                'default': 'rocksdb',
                'choices': ['hermes', 'rocksdb', 'leveldb', 'redis'],
                'args': [],
            },
            {
                'name': 'workload',
                'msg': 'The workload to use',
                'type': str,
                'default': 'a',
                'choices': ['a', 'b', 'c', 'd', 'e', 'f'],
                'args': [],
            },
            {
                'name': 'status',
                'msg': 'Whether or not to print statuses every 10 sec',
                'type': bool,
                'default': True,
                'args': [],
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        root = self.env['YCSBC_ROOT']
        db_name = self.config["db_name"]
        workload = f'workload{self.config["workload"]}'
        props = f'{root}/{db_name}/{db_name}.properties'
        if not os.path.exists(props):
            props_arg = ''
        else:
            props_arg = f'-P {props}'
        cmd = [
            'ycsb -run',
            f'-db {db_name}',
            f'-P {root}/workloads/{workload}',
            props_arg,
            f'-s' if self.config['status'] else ''
        ]
        cmd = ' '.join(cmd)
        print(cmd)
        self.exec = Exec(cmd,
             LocalExecInfo(env=self.mod_env,
                           hostfile=self.jarvis.hostfile,
                           do_dbg=self.config['do_dbg'],
                           dbg_port=self.config['dbg_port'],
                           collect_output=True))

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass

    def _get_stat(self, stat_dict):
        """
        Get statistics from the application.

        :param stat_dict: A dictionary of statistics.
        :return: None
        """
        output = self.exec.stdout['localhost']
        if 'throughput(ops/sec)' in output:
            throughput = re.search(r'throughput\(ops\/sec\): ([0-9.]+)', output).group(1)
            stat_dict[f'{self.pkg_id}.throughput'] = throughput
        stat_dict[f'{self.pkg_id}.runtime'] = self.start_time
```

### `builtin/config/ares.yaml`

```yaml
CONFIG_DIR: ${HOME}/jarvis-pipelines
CUR_PIPELINE: null
HOSTFILE: null
PRIVATE_DIR: /mnt/ssd/${USER}/jarvis-pipelines
SHARED_DIR: ${HOME}/jarvis-pipelines
```

### `builtin/config/deception.yaml`

```yaml
CONFIG_DIR: ${HOME}/jarvis-pipelines
CUR_PIPELINE: null
HOSTFILE: null
PRIVATE_DIR: /scratch/${USER}/jarvis-pipelines # local SSD
SHARED_DIR: ${HOME}/jarvis-pipelines
```

### `builtin/config/polaris.yaml`

```yaml
CONFIG_DIR: ${HOME}/SCS_lab/jarvis_pipeline
CUR_PIPELINE: null
HOSTFILE: null
PRIVATE_DIR: /tmp/${USER}/jarvis
SHARED_DIR: /lus/grand/projects/VeloC/${USER}/SCS_lab/
```

### `builtin/resource_graph/ares.yaml`

```yaml
fs:
- avail: 500GB
  dev_type: ssd
  device: /dev/sdb1
  fs_type: xfs
  model: Samsung SSD 860
  mount: /mnt/ssd/${USER}
  parent: /dev/sdb
  shared: false
  uuid: 45b6abb3-7786-4b68-95d0-a8fac92e0d70
  needs_root: false
- avail: 500GB
  dev_type: hdd
  device: null
  fs_type: xfs
  model: null
  mount: ${HOME}
  parent: null
  shared: true
  uuid: null
  needs_root: false
- avail: 240GB
  dev_type: nvme
  device: /dev/nvme0n1p1
  fs_type: xfs
  model: TOSHIBA-RD400
  mount: /mnt/nvme/${USER}
  parent: /dev/nvme0n1
  shared: false
  uuid: cbc9b18c-fbb0-4ab7-a9fd-8cc719a93f64
  needs_root: false
- avail: 900GB
  dev_type: hdd
  device: /dev/sdc1
  fs_type: xfs
  model: ST1000LM049-2GH1
  mount: /mnt/hdd/${USER}
  parent: /dev/sdc
  shared: false
  uuid: 7857cbad-2e46-40c2-835a-b297bc5ee1d2
  needs_root: false
net:
- domain: lo
  fabric: 127.0.0.1/32
  protocol: FI_PROTO_RXM
  provider: tcp;ofi_rxm
  shared: false
  speed: 42949672960
  type: FI_EP_RDM
  version: '114.10'
- domain: eno1
  fabric: 172.20.0.0/16
  protocol: FI_PROTO_UDP
  provider: udp
  shared: true
  speed: 42949672960
  type: FI_EP_DGRAM
  version: '114.10'
- domain: lo
  fabric: 127.0.0.1/32
  protocol: FI_PROTO_SOCK_TCP
  provider: tcp
  shared: false
  speed: 42949672960
  type: FI_EP_MSG
  version: '114.10'
- domain: lo
  fabric: 127.0.0.1/32
  protocol: FI_PROTO_UDP
  provider: udp
  shared: false
  speed: 42949672960
  type: FI_EP_DGRAM
  version: '114.10'
- domain: enp47s0np0
  fabric: 172.25.0.0/16
  protocol: FI_PROTO_RXD
  provider: udp;ofi_rxd
  shared: true
  speed: 42949672960
  type: FI_EP_RDM
  version: '114.10'
- domain: eno1
  fabric: 172.20.0.0/16
  protocol: FI_PROTO_RXM
  provider: tcp;ofi_rxm
  shared: true
  speed: 42949672960
  type: FI_EP_RDM
  version: '114.10'
- domain: lo
  fabric: 127.0.0.1/32
  protocol: FI_PROTO_SOCK_TCP
  provider: sockets
  shared: false
  speed: 42949672960
  type: FI_EP_DGRAM
  version: '114.10'
- domain: lo
  fabric: 127.0.0.1/32
  protocol: FI_PROTO_RXD
  provider: udp;ofi_rxd
  shared: false
  speed: 42949672960
  type: FI_EP_RDM
  version: '114.10'
- domain: eno1
  fabric: 172.20.0.0/16
  protocol: FI_PROTO_SOCK_TCP
  provider: tcp
  shared: true
  speed: 42949672960
  type: FI_EP_MSG
  version: '114.10'
- domain: enp47s0np0
  fabric: 172.25.0.0/16
  protocol: FI_PROTO_RXM
  provider: tcp;ofi_rxm
  shared: true
  speed: 42949672960
  type: FI_EP_RDM
  version: '114.10'
- domain: enp47s0np0
  fabric: 172.25.0.0/16
  protocol: FI_PROTO_UDP
  provider: udp
  shared: true
  speed: 42949672960
  type: FI_EP_DGRAM
  version: '114.10'
- domain: enp47s0np0
  fabric: 172.25.0.0/16
  protocol: FI_PROTO_SOCK_TCP
  provider: sockets
  shared: true
  speed: 42949672960
  type: FI_EP_DGRAM
  version: '114.10'
- domain: enp47s0np0
  fabric: 172.25.0.0/16
  protocol: FI_PROTO_SOCK_TCP
  provider: tcp
  shared: true
  speed: 42949672960
  type: FI_EP_MSG
  version: '114.10'
- domain: eno1
  fabric: 172.20.0.0/16
  protocol: FI_PROTO_SOCK_TCP
  provider: sockets
  shared: true
  speed: 42949672960
  type: FI_EP_DGRAM
  version: '114.10'
- domain: eno1
  fabric: 172.20.0.0/16
  protocol: FI_PROTO_RXD
  provider: udp;ofi_rxd
  shared: true
  speed: 42949672960
  type: FI_EP_RDM
  version: '114.10'
- domain: ''
  fabric: 172.25.0.0/16
  protocol: ''
  provider: ofi+verbs;ofi_rxm
  shared: true
  speed: 42949672961
  type: ''
  version: '114.10'
```

### `builtin/resource_graph/deception.yaml`

```yaml
fs:
- avail: 262200417583104
  dev_type: nvme
  device: nvme0n1
  fs_type: null
  needs_root: false
  model: INTEL SSDPEKKA512G8
  mount: /scratch/${USER}
  parent: null
  shared: false
  uuid: null
- avail: 2147483648000
  dev_type: hdd
  device: null
  fs_type: null
  needs_root: false
  model: null
  mount: /rcfs/projects/chess/${USER}
  parent: null
  shared: true
  uuid: null
hosts:
- localhost
net:
- domain: mlx5_0:1
  fabric: 172.17.0.0/16
  protocol: FI_PROTO_SOCK_TCP
  provider: ucx+rc_verbs
  shared: true
  speed: 12884901888
  type: FI_EP_MSG
  version: '116.10'
```

### `builtin/resource_graph/delta.yaml`

```yaml
fs:
- device: nvme0n1p1
  model: MZXL5800HBHQ-000H3
  mount: /tmp
  parent: nvme0n1
  rota: 0
  sector_size: 512
  size: 800165027840
  tran: pcie
- avail: 2026619832316723
  dev_type: null
  device: harbor-dt.delta.internal.ncsa.edu:/harbor/ncsa/delta/u
  fs_type: null
  model: null
  mount: /u/${USER}
  needs_root: false
  parent: null
  shared: true
  size: 2026619832316723
  tran: ''
  uuid: null
net:
- domain: eth1
  fabric: 172.28.22.0/23
  provider: tcp
  shared: true
  speed: 0
- domain: eth1
  fabric: 172.28.22.0/23
  provider: tcp;ofi_rxm
  shared: true
  speed: 0
- domain: hsn0
  fabric: 172.28.80.0/21
  provider: tcp
  shared: true
  speed: 0
- domain: hsn0
  fabric: 172.28.80.0/21
  provider: tcp;ofi_rxm
  shared: true
  speed: 0
- domain: lo
  fabric: 127.0.0.1/32
  provider: tcp;ofi_rxm
  shared: false
  speed: 0
- domain: lo
  fabric: 127.0.0.1/32
  provider: tcp
  shared: false
  speed: 0
```

### `builtin/resource_graph/g2-standard-4.yaml`

```yaml
fs:
- avail: 107238916608
  dev_type: null
  device: nvme0n1p1
  fs_mount: null
  fs_size: null
  fs_type: null
  needs_root: false
  model: nvme_card-pd
  mount: ${HOME}
  parent: nvme0n1
  rota: 0
  sector_size: 512
  shared: false
  size: 107238916608
  tran: nvme
  use%: null
  used: null
  uuid: null
hosts:
- localhost
net:
- domain: lo
  fabric: ''
  protocol: FI_PROTO_SOCK_TCP
  provider: sockets
  shared: null
  speed: 0
  type: FI_EP_DGRAM
  version: '121.0'
```

### `builtin/resource_graph/polaris.yaml`

```yaml
fs:
- avail: 54975581388800
  dev_type: hdd
  device: null
  fs_type: null
  needs_root: false
  model: null
  mount: /lus/grand/projects/VeloC/${USER}/SCS_lab
  parent: null
  shared: true
  uuid: null
hosts:
- localhost
net:
- domain: mlx5_3-dgram
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_IB_UD
  provider: verbs
  shared: true
  speed: 107374182400
  type: FI_EP_DGRAM
  version: '111.0'
- domain: mlx5_bond_0
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RDMA_CM_IB_RC
  provider: verbs
  shared: true
  speed: 107374182400
  type: FI_EP_MSG
  version: '111.0'
- domain: mlx5_3
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RDMA_CM_IB_RC
  provider: verbs
  shared: true
  speed: 107374182400
  type: FI_EP_MSG
  version: '111.0'
- domain: mlx5_bond_0-xrc
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RXM
  provider: verbs;ofi_rxm
  shared: true
  speed: 107374182400
  type: FI_EP_RDM
  version: '111.0'
- domain: mlx5_3-xrc
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RDMA_CM_IB_XRC
  provider: verbs
  shared: true
  speed: 107374182400
  type: FI_EP_MSG
  version: '111.0'
- domain: mlx5_3-xrc
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RXM
  provider: verbs;ofi_rxm
  shared: true
  speed: 107374182400
  type: FI_EP_RDM
  version: '111.0'
- domain: mlx5_0-xrc
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RDMA_CM_IB_XRC
  provider: verbs
  shared: true
  speed: 107374182400
  type: FI_EP_MSG
  version: '111.0'
- domain: mlx5_0
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RDMA_CM_IB_RC
  provider: verbs
  shared: true
  speed: 107374182400
  type: FI_EP_MSG
  version: '111.0'
- domain: mlx5_0
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RXM
  provider: verbs;ofi_rxm
  shared: true
  speed: 107374182400
  type: FI_EP_RDM
  version: '111.0'
- domain: mlx5_0-xrc
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RXM
  provider: verbs;ofi_rxm
  shared: true
  speed: 107374182400
  type: FI_EP_RDM
  version: '111.0'
- domain: mlx5_bond_0-dgram
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_IB_UD
  provider: verbs
  shared: true
  speed: 107374182400
  type: FI_EP_DGRAM
  version: '111.0'
- domain: hsn0
  fabric: 10.201.0.0/16
  protocol: FI_PROTO_SOCK_TCP
  provider: sockets
  shared: true
  speed: 107374182400
  type: FI_EP_RDM
  version: '111.0'
- domain: mlx5_0-dgram
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_IB_UD
  provider: verbs
  shared: true
  speed: 107374182400
  type: FI_EP_DGRAM
  version: '111.0'
- domain: mlx5_3
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RXM
  provider: verbs;ofi_rxm
  shared: true
  speed: 107374182400
  type: FI_EP_RDM
  version: '111.0'
- domain: mlx5_bond_0-xrc
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RDMA_CM_IB_XRC
  provider: verbs
  shared: true
  speed: 107374182400
  type: FI_EP_MSG
  version: '111.0'
- domain: mlx5_bond_0
  fabric: IB-0xfe80000000000000
  protocol: FI_PROTO_RXM
  provider: verbs;ofi_rxm
  shared: true
  speed: 107374182400
  type: FI_EP_RDM
  version: '111.0'
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
pushd ${GITHUB_WORKSPACE} || exit
git clone https://github.com/scs-lab/jarvis-util.git
pushd jarvis-util || exit
python3 -m pip install -r requirements.txt
python3 -m pip install -e .
popd || exit
popd || exit

python3 -m pip install -r requirements.txt
python3 -m pip install -e .

jarvis init "${HOME}/jarvis-pipelines" "${HOME}/jarvis-pipelines" "${HOME}/jarvis-pipelines"
```

### `ci/lint.sh`

```bash
#!/bin/bash
pylint --disable=W0212 "${PWD}/jarvis_cd" "${PWD}/test" # "${PWD}"/builtin
```

### `ci/run_tests.sh`

```bash
#!/bin/bash
pip install coverage
pip install coverage-lcov
pip install pytest
coverage run -m pytest test
rm -rf "*.pyc"
coverage report
coverage-lcov
```

### `docs/make.bat`

```batch
@ECHO OFF

pushd %~dp0

REM Command file for Sphinx documentation

if "%SPHINXBUILD%" == "" (
	set SPHINXBUILD=sphinx-build
)
set SOURCEDIR=source
set BUILDDIR=build

%SPHINXBUILD% >NUL 2>NUL
if errorlevel 9009 (
	echo.
	echo.The 'sphinx-build' command was not found. Make sure you have Sphinx
	echo.installed, then set the SPHINXBUILD environment variable to point
	echo.to the full path of the 'sphinx-build' executable. Alternatively you
	echo.may add the Sphinx directory to PATH.
	echo.
	echo.If you don't have Sphinx installed, grab it from
	echo.https://www.sphinx-doc.org/
	exit /b 1
)

if "%1" == "" goto help

%SPHINXBUILD% -M %1 %SOURCEDIR% %BUILDDIR% %SPHINXOPTS% %O%
goto end

:help
%SPHINXBUILD% -M help %SOURCEDIR% %BUILDDIR% %SPHINXOPTS% %O%

:end
popd
```

### `docs/source/conf.py`

```python
# Configuration file for the Sphinx documentation builder.
#
# For the full list of built-in configuration values, see the documentation:
# https://www.sphinx-doc.org/en/master/usage/configuration.html

# -- Project information -----------------------------------------------------
# https://www.sphinx-doc.org/en/master/usage/configuration.html#project-information

project = 'Jarvis-CD'
copyright = '2022, Luke Logan, Jaime Cernuda Garcia, Hariharan Devarajan'
author = 'Luke Logan, Jaime Cernuda Garcia, Hariharan Devarajan'
release = '0.0.0'

# -- General configuration ---------------------------------------------------
# https://www.sphinx-doc.org/en/master/usage/configuration.html#general-configuration

extensions = []

templates_path = ['_templates']
exclude_patterns = []

language = 'Python'

# -- Options for HTML output -------------------------------------------------
# https://www.sphinx-doc.org/en/master/usage/configuration.html#options-for-html-output

html_theme = 'alabaster'
html_static_path = ['_static']
```

### `docs/source/development.rst`

```rst

```

### `docs/source/index.rst`

```rst
.. Jarvis-CD documentation master file, created by
   sphinx-quickstart on Thu Aug 11 06:07:32 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Jarvis-CD's documentation!
=====================================

Jarvis is a tool for deploying and configuring complex applications, mainly
distributed storage systems. It also includes a Python library, which can be
used for launching applications within python scripts.

.. toctree::
   :maxdepth: 2
   :caption: Contents:
   usage/install
   usage/quickstart
   usage/python-api
   development/launchers
   development/environments



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
```

### `docs/source/install.rst`

```rst
Install
=======

To install Jarvis:

``
cd jarvis-cd
bash dependencies.sh
source ~/.bashrc
python3 -m pip install -e . --user -r requirements.txt
jarvis deps scaffold local
jarvis deps local-install all
source ~/.bashrc
``
```

### `docs/source/usage.rst`

```rst

```

### `jarvis_cd/__init__.py`

```python

```

### `jarvis_cd/basic/__init__.py`

```python

```

### `jarvis_cd/basic/jarvis_manager.py`

```python
"""
This module represents the JarvisCD Manager singleton. It stores an index
of all relevant paths needed by most jarvis repos.
"""

import pathlib
import os
from jarvis_util.shell.filesystem import Rm
from jarvis_util.serialize.yaml_file import YamlFile
from jarvis_util.util.import_mod import load_class
from jarvis_util.util.naming import to_camel_case
from jarvis_util.util.expand_env import expand_env
from jarvis_util.util.hostfile import Hostfile
from jarvis_util.introspect.system_info import ResourceGraph
from jarvis_util.shell.filesystem import Mkdir
from jarvis_util.shell.pssh_exec import PsshExecInfo
from jarvis_util.shell.local_exec import LocalExecInfo
from pathlib import Path
import getpass
import yaml
import sys


class JarvisManager:
    """
    This class stores relevant paths and loads global configurations for
    internal use by jarvis repos.
    """
    instance_ = None

    @staticmethod
    def get_instance():
        if JarvisManager.instance_ is None:
            JarvisManager.instance_ = JarvisManager()
        return JarvisManager.instance_

    def __init__(self):
        self.jarvis_root = str(
            pathlib.Path(__file__).parent.parent.parent.resolve())
        # The current user
        self.user = getpass.getuser()
        # Where Jarvis stores pipeline data (per-user)
        self.config_dir = None
        # The path to named Jarvis environment caches
        self.env_dir = None
        # Where Jarvis stores data locally to a pkg (per-user)
        self.private_dir = None
        # Where Jarvis stores data in a shared directory (per-user)
        self.shared_dir = None
        # The current pipeline (per-user)
        self.cur_pipeline = None
        # Path to local jarvis configuration directory
        self.local_config_dir = os.path.join(Path.home(), '.jarvis')
        # Path to local jarvis builtin package directory
        self.builtin_dir = os.path.join(self.local_config_dir, 'builtin')
        # Path to the global jarvis configuration
        self.jarvis_conf_path = os.path.join(self.local_config_dir,
                                             'jarvis_config.yaml')
        # Path to the global jarvis resource graph
        self.jarvis_repos_path = os.path.join(self.local_config_dir,
                                              'repos.yaml')
        # The Jarvis configuration (per-user)
        self.jarvis_conf = None
        #  The path to the jarvis resource graph (global across users)
        self.resource_graph_path = os.path.join(self.local_config_dir,
                                                'resource_graph.yaml')
        # The Jarvis resource graph (global across users)
        self.resource_graph = None
        self.hostfile = None
        self.repos = []
        self.load()

    def create(self, config_dir, private_dir, shared_dir=None):
        """
        Create a new root jarvis config under config/$USER/jarvis_config.yaml

        :param config_dir: the directory where jarvis stores pipeline
        metadata
        :param private_dir: a directory which is shared on all pkgs, but
        stores data privately to the pkg
        :param shared_dir: a directory which is shared on all pkgs, where
        all pkgs have the same view of the data
        :return: None
        """
        self.config_dir = expand_env(config_dir)
        self.private_dir = expand_env(private_dir)
        self.shared_dir = expand_env(shared_dir)
        self.jarvis_conf = {
            # Global parameters
            'CONFIG_DIR': config_dir,
            'PRIVATE_DIR': private_dir,
            'SHARED_DIR': shared_dir,
            'REPOS': [],

            # Per-user parameters
            'HOSTFILE': None,
            'CUR_PIPELINE': None,
        }
        self.load_repos()
        self.resource_graph = ResourceGraph()
        self.hostfile = Hostfile()
        os.makedirs(self.local_config_dir, exist_ok=True)
        self.save()

    def load_repos(self):
        # Read repos conf
        if os.path.exists(self.jarvis_repos_path):
            self.repos = YamlFile(self.jarvis_repos_path).load()['REPOS']
        else:
            self.repos = [
                {
                    'path': self.builtin_dir,
                    'name': 'builtin'
                }
            ]

    def load(self):
        """
        Load the jarvis config from config/jarvis_config.yaml

        :return: None
        """
        if not os.path.exists(self.jarvis_conf_path):
            print('No configuration was found. Run jarvis init or bootstrap. '
                  'If you are currently running those commands, '
                  'please ignore this message.')
            return
        self.jarvis_conf = {}
        # Read global jarvis conf
        self.jarvis_conf.update(YamlFile(self.jarvis_conf_path).load())
        # Read repos files
        self.load_repos()
        # Get the various jarvis paths
        self.config_dir = expand_env(self.jarvis_conf['CONFIG_DIR'])
        self.env_dir = os.path.join(self.config_dir, 'env')
        os.makedirs(f'{self.config_dir}', exist_ok=True)
        os.makedirs(f'{self.env_dir}', exist_ok=True)
        self.private_dir = expand_env(self.jarvis_conf['PRIVATE_DIR'])
        Mkdir(self.private_dir,
              PsshExecInfo(hostfile=self.hostfile))
        if self.jarvis_conf['SHARED_DIR'] is not None:
            self.shared_dir = expand_env(self.jarvis_conf['SHARED_DIR'])
            os.makedirs(f'{self.shared_dir}', exist_ok=True)
        # Read global resource graph
        if os.path.exists(self.resource_graph_path):
            self.resource_graph = ResourceGraph().load(self.resource_graph_path)
        else:
            self.resource_graph = ResourceGraph()
        self.cur_pipeline = self.jarvis_conf['CUR_PIPELINE']
        try:
            self.hostfile = Hostfile(hostfile=self.jarvis_conf['HOSTFILE'])
        except Exception as e:
            print(f"Failed to open hostfile {self.jarvis_conf['HOSTFILE']}")
            self.hostfile = Hostfile()
            print(f"An error occurred: {e}")
            print(f"Error arguments: {e.args}")
        return self

    def save(self):
        """
        Save the jarvis config to config/jarvis_config.yaml

        :return: None
        """
        # Update jarvis conf
        if self.jarvis_conf:
            self.jarvis_conf['CUR_PIPELINE'] = self.cur_pipeline
            self.jarvis_conf['HOSTFILE'] = self.hostfile.path
        # Update repos
        YamlFile(self.jarvis_repos_path).save({'REPOS': self.repos})
        # Save global resource graph
        if self.resource_graph:
            self.resource_graph.save(self.resource_graph_path)
        # Save global and per-user conf
        if self.jarvis_conf:
            YamlFile(self.jarvis_conf_path).save(self.jarvis_conf)

    def set_hostfile(self, path):
        """
        Set the hostfile and re-configure all existing jarvis pipelines

        :return: None
        """
        if len(path) > 0:
            self.hostfile = Hostfile(hostfile=path)
        else:
            self.hostfile = Hostfile()

    def bootstrap_from(self, machine):
        """
        Bootstrap jarvis for a particular machine

        :param machine: The machine config to copy
        :return: None
        """
        if machine == 'local':
            #
            self.create(
                os.path.join(self.local_config_dir, 'config'),
                os.path.join(self.local_config_dir, 'private'),
                os.path.join(self.local_config_dir, 'shared'))
            self.save()
            return
        self.load_repos()
        os.makedirs(self.local_config_dir, exist_ok=True)
        config_path = f'{self.builtin_dir}/config/{machine}.yaml'
        if os.path.exists(config_path):
            config = expand_env(YamlFile(config_path).load())
            new_config_path = f'{self.local_config_dir}/jarvis_config.yaml'
            YamlFile(new_config_path).save(config)

        rg_path = f'{self.builtin_dir}/resource_graph/{machine}.yaml'
        if os.path.exists(rg_path):
            self.resource_graph = ResourceGraph().load(rg_path)
            new_rg_path = f'{self.local_config_dir}/resource_graph.yaml'
            self.resource_graph.save(new_rg_path)

    def bootstrap_list(self):
        """
        List machines we can bootstrap with no additional configuration

        :return: None
        """
        configs = os.listdir(f'{self.builtin_dir}/config')
        for config in configs:
            print(config.replace('.yaml', ''))

    def reset(self):
        """
        Destroy all pipelines and their data

        :return: None
        """
        Rm(self.shared_dir, LocalExecInfo())
        Rm(self.private_dir, PsshExecInfo(
            hostfile=self.hostfile))

    def print_config(self):
        print(yaml.dump(self.jarvis_conf))

    def print_config_path(self):
        print(self.jarvis_conf_path)

    def resource_graph_show(self):
        """
        Print the resource graph

        :return: None
        """
        print('fs:')
        self.resource_graph.print_df(self.resource_graph.fs)
        print('net:')
        self.resource_graph.print_df(self.resource_graph.net)

    def resource_graph_build(self, net_sleep):
        """
        Introspect the system and construct a resource graph.

        :return: None
        """
        self.resource_graph = ResourceGraph()
        self.resource_graph.build(
            PsshExecInfo(hostfile=self.hostfile), net_sleep=net_sleep)

    def resource_graph_modify(self, net_sleep):
        """
        Modify the resource graph to retest resources
        """
        self.resource_graph.modify(
            PsshExecInfo(hostfile=self.hostfile), net_sleep=net_sleep)

    def list_pipelines(self):
        """
        Get a list of all created pipelines

        :return: List of pipelines
        """
        pipelines = os.listdir(self.config_dir)
        pipelines.sort()
        pipelines.remove('env')
        return pipelines

    def cd(self, pipeline_id):
        """
        Make jarvis focus on the pipeline with id ID.
        This pipeline will be used for subsequent operations:
            jarvis [start/stop/clean/stop/destroy/configure]

        :param pipeline_id: The id of the pipeline to focus on
        :return: None
        """
        self.cur_pipeline = pipeline_id

    def add_repo(self, path, force):
        """
        Induct a repo into the jarvis managers repo search variable.
        Does not create data on the filesystem.

        :param path: The path to the repo to induct. The basename of the
        repo is assumed to be its repo name. E.g., for /home/hi/myrepo,
        my repo would be the basename.
        :param force: If true, overwrite the repo if it already exists
        :return: None
        """

        repo_name = os.path.basename(path)
        path = os.path.abspath(path)
        for repo in self.repos:
            if repo['name'] == repo_name:
                if os.path.exists(repo['path']) and not force:
                    print('Warning: repo already exists. '
                          'Use --force to overwrite')
                    return
                else:
                    repo['path'] = path
                    print(f'Updated the {repo_name} to path {path}')
                    return
        if not os.path.exists(os.path.join(path, repo_name)):
            print('Error: repo must have a subdirectory with the same name')
            sys.exit(1)
        self.repos.insert(0, {
            'path': path,
            'name': repo_name
        })
        print(f'Added the {repo_name} repo')

    def create_pkg(self, pkg_cls, pkg_type):
        """
        Creates the skeleton of a pkg within the primary repo.

        :param pkg_type: The name of the pkg to create
        :param pkg_cls: The type of pkg to create (Service, Application, etc.)
        :return: None
        """
        # load the template data
        tmpl_dir = f'{self.jarvis_root}/jarvis_cd/template'
        with open(f'{tmpl_dir}/{pkg_cls}_templ.py',
                  encoding='utf-8') as fp:
            text = fp.read()

        # Replace MyPkg with the pkg name
        text = text.replace('MyPkg', to_camel_case(pkg_type))

        # Write the specialized data
        repo_name = self.repos[0]['name']
        repo_dir = self.repos[0]['path']
        pkg_path = f'{repo_dir}/{repo_name}/{pkg_type}'
        os.makedirs(pkg_path, exist_ok=True)
        with open(f'{pkg_path}/pkg.py', 'w',
                  encoding='utf-8') as fp:
            fp.write(text)

    def get_repo(self, repo_name):
        """
        Get the repo information associated with the repo name

        :param repo_name: The repo to get info for
        :return: A dictionary containing the name of the repo and the
        path to the repo
        """

        matches = [repo for repo in self.repos if repo_name == repo['name']]
        if len(matches) == 0:
            return None
        return matches[0]

    def promote_repo(self, repo_name):
        """
        Make all subsequent jarvis append operations track this repo first.

        :param repo_name: The repo to prioritize
        :return: None
        """

        main_repo = self.get_repo(repo_name)
        if main_repo is None:
            raise Exception(f'Could not find repo: {repo_name}')
        self.repos = [repo for repo in self.repos if repo_name != repo['name']]
        self.repos.insert(0, main_repo)

    def remove_repo(self, repo_name):
        """
        Remove a repo from consideration. Does not destroy data.

        :param repo_name: the name of the repo to remove
        :return: None
        """
        self.repos = [repo for repo in self.repos if repo_name != repo['name']]

    def list_repos(self):
        """
        Print all repos in jarvis

        :return: None
        """
        for repo in self.repos:
            self.list_repo(repo['name'])


    def list_repo(self, repo_name):
        """
        List all of the pkgs in a repo

        :param repo_name: The repo to list
        :return: None
        """
        repo = self.get_repo(repo_name)
        if not os.path.exists(repo['path']):
            print(f"Repo {repo['path']} does not exist")
            return
        pkg_types = os.listdir(os.path.join(repo['path'], repo['name']))
        pkg_types.sort()
        print(f"{repo['name']}: {repo['path']}")
        for pkg_type in pkg_types:
            if not pkg_type.startswith('_'):
                print(f'  {pkg_type}')

    def construct_pkg(self, pkg_type):
        """
        Construct a pkg by searching repos for the pkg type

        :param pkg_type: The type of pkg to load (snake case).
        :return: A object of type "pkg_type"
        """
        for repo in self.repos:
            cls = load_class(f"{repo['name']}.{pkg_type}.pkg",
                             repo['path'],
                             to_camel_case(pkg_type))
            if cls is None:
                continue
            return cls()
```

### `jarvis_cd/basic/pkg.py`

```python
"""
This module contains abstract base classes which represent the different
pkg types in Jarvis.
"""

from abc import ABC, abstractmethod
from jarvis_cd.basic.jarvis_manager import JarvisManager
from jarvis_util.util.logging import ColorPrinter, Color
from jarvis_util.util.naming import to_snake_case
from jarvis_util.serialize.yaml_file import YamlFile
from jarvis_util.shell.local_exec import LocalExecInfo
from jarvis_util.shell.exec import Exec
from jarvis_util.util.argparse import ArgParse
from jarvis_util.jutil_manager import JutilManager
from jarvis_util.shell.filesystem import Mkdir, Rm
from jarvis_util.shell.pssh_exec import PsshExecInfo
import yaml
import inspect
import pathlib
import shutil
import math
import os
import time
import pandas as pd


class PkgArgParse(ArgParse):
    def define_options(self):
        self.add_cmd()
        self.add_args(self.custom_info['menu'])

    def main_menu(self):
        pass


class PipelineZip:
    """
    A class to represent a zip of pipeline configurations
    """
    def __init__(self):
        self.zip = []
        self.zip_len = 0

    def add_param_set(self, pkg, var_name, var_vals):
        self.zip_len = len(var_vals)
        self.zip.append((pkg, var_name, var_vals))


class PipelineIterator:
    """
    Grid searching pipeline parameters
    """
    def __init__(self, ppl):
        """
        Initialize grid search

        fors: A list of lists [(pkg, var_name, var_vals)]
        """
        self.ppl = ppl
        self.norerun = set()
        if 'norerun' in ppl.config['iterator']:
            self.norerun = set(ppl.config['iterator']['norerun'])
        self.fors = []
        self.cur_iters = []
        self.cur_pos = []
        self.cur_pos_diff = []
        self.iter_count = 0
        self.max_iter_count = 0
        self.conf_dict = {}
        self.linear_conf_dict = {}
        self.iter_vars = ppl.config['iterator']['vars']
        self.iter_loop = ppl.config['iterator']['loop']
        self.repeat = ppl.config['iterator']['repeat']
        ppl.set_config_env_vars()
        self.iter_out = os.path.expandvars(ppl.config['iterator']['output'])
        print(f'ITER OUT: {self.iter_out} '
              f"(from: {ppl.config['iterator']['output']})")
        self.stats_path = f'{self.iter_out}/stats_dict.csv'
        self.stats = []

        Mkdir(self.iter_out)
        self.iter_vars = self.iter_vars
        for zip_set in self.iter_loop:
            self.add_for()
            for zip_name in zip_set:
                pkg_name, var_name = zip_name.split('.')
                pkg = ppl.sub_pkgs_dict[pkg_name]
                self.add_to_for_zip(pkg, var_name, self.iter_vars[zip_name])

    def add_for(self):
        self.fors.append(PipelineZip())

    def add_to_for_zip(self, pkg, var_name, var_vals):
        for_zip = self.fors[-1]
        for_zip.add_param_set(pkg, var_name, var_vals)
        self.conf_dict[pkg] = {}

    def begin(self):
        for i in range(len(self.fors)):
            self.cur_iters.append(iter(range(self.fors[i].zip_len)))
            self.cur_pos.append(next(self.cur_iters[i]))
        self.cur_pos_diff = [1] * len(self.cur_pos)
        self.conf_dict = self.current()
        self.iter_count = 0
        self.max_iter_count = math.prod([for_zip.zip_len for for_zip
                                         in self.fors])
        return self.conf_dict

    def current(self):
        for i in range(len(self.cur_iters)):
            for pkg, var_name, var_vals in self.fors[i].zip:
                self.conf_dict[pkg][var_name] = var_vals[self.cur_pos[i]]
                pkg.iter_diff = self.cur_pos_diff[i]
        for pkg, conf in self.conf_dict.items():
            for key, val in conf.items():
                self.linear_conf_dict[f'{pkg.pkg_id}.{key}'] = val
        return self.conf_dict

    def next(self):
        self.cur_pos_diff = [0] * len(self.cur_pos)
        for i in range(len(self.cur_iters) - 1, -1, -1):
            try:
                self.cur_pos[i] = next(self.cur_iters[i])
                self.cur_pos_diff[i] = 1
                break
            except StopIteration:
                if i == 0:
                    return None
                else:
                    self.cur_iters[i] = iter(range(self.fors[i].zip_len))
                    self.cur_pos[i] = next(self.cur_iters[i])
                    self.cur_pos_diff[i] = 1
        conf_dict = self.current()
        self.iter_count += 1
        return conf_dict

    def config_pkgs(self, conf_dict):
        for pkg, conf in conf_dict.items():
            pkg.skip_run = False
            if pkg.pkg_id in self.norerun and pkg.iter_diff == 0:
                pkg.skip_run = True
            pkg.set_config_env_vars()
            pkg.configure(**conf)
            pkg.save()

    def save_run(self, conf_dict):
        if conf_dict:
            print('WARNING: conf_dict is defined but not used.')
        stat_dict = {**self.linear_conf_dict}
        # Get the package-specific stats
        for pkg in self.ppl.sub_pkgs:
            if hasattr(pkg, '_get_stat'):
                pkg._get_stat(stat_dict)
        # Save the stats to the list
        self.stats.append(stat_dict)

    def analysis(self):
        for pkg in self.ppl.sub_pkgs:
            if hasattr(pkg, '_analysis'):
                pkg._analysis(self.stats)
        df = pd.DataFrame(self.stats)
        df.to_csv(self.stats_path, index=False)

class Pkg(ABC):
    """
    Represents a generic Jarvis pkg. Includes methods to load configurations
    and to specialize the pkg using a global_id.
    """

    def __init__(self):
        """
        Initialize paths
        
        jarvis: the JarvisManager singleton
        jutil: the JutilManager singleton
        pkg_type: the type of this package (semantic string)
        root: the root package of this package
        global_id: the unique identifier for this package (dot-separated string)
        pkg_id: the semantic name of this package (last part of globl_id)
        pkg_dir: the code's source directory
        config_dir: the directory where configuration data is stored
        private_dir: the directory where private data is stored
        shared_dir: the directory where shared data is stored
        config_path: the path to the configuration file
        config: the configuration data
        sub_pkgs: the sub-packages of this package (ordered list)
        sub_pkgs_dict: the sub-packages of this package (dict)
        env_path: the path to the environment file
        env: the environment data
        mod_env: the environment data + LD_PRELOAD
        iter_vars: the iteration variables
        iter_loop: the iteration loop
        iter_out: the iteration output
        stats_path: the path to the statistics file
        stats: the statistics list
        """
        self.jarvis = JarvisManager.get_instance()
        self.jutil = JutilManager.get_instance()
        self.pkg_type = to_snake_case(self.__class__.__name__)
        self.root = None
        self.global_id = None
        self.pkg_id = None
        """The pkg dir (e.g., ${JARVIS_ROOT}/builtin/orangefs)"""
        self.pkg_dir = str(
            pathlib.Path(inspect.getfile(self.__class__)).parent.resolve())
        self.config_dir = None
        self.private_dir = None
        self.shared_dir = None
        self.config_path = None
        self.config = None
        self.sub_pkgs = []
        self.sub_pkgs_dict = {}
        self.env_path = None
        self.env = None
        self.mod_env = None
        self.iterator = None
        self.exit_code = 0
        self.start_time = 0
        self.stop_time = 0
        self.skip_run = False

    def log(self, msg, color=None):
        ColorPrinter.print(msg, color)

    def _init_common(self, global_id, root):
        """
        Update paths in this package based on the global_id

        :param global_id: The unique identifier for this package
        :return: None
        """
        if root is None:
            root = self
        self.root = root
        self.global_id = self._get_global_id(global_id)
        id_split = self.global_id.split('.')
        self.pkg_id = id_split[-1]
        relpath = self.global_id.replace('.', '/')
        self.config_dir = f'{self.jarvis.config_dir}/{relpath}'
        self.private_dir = f'{self.jarvis.private_dir}/{relpath}'
        if self.jarvis.shared_dir is not None:
            self.shared_dir = f'{self.jarvis.shared_dir}/{relpath}'
        self.config_path = f'{self.config_dir}/{self.pkg_id}.yaml'
        if len(id_split) > 1:
            self.env_path = None
        else:
            self.env_path = f'{self.config_dir}/env.yaml'

    def _get_global_id(self, global_id):
        if global_id is None:
            global_id = self.jarvis.cur_pipeline
        if global_id is None:
            raise Exception('No pipeline currently selected')
        return global_id

    def create(self, global_id):
        """
        Create a new pkg and its filesystem data

        :param global_id: A dot-separated, globally unique identifier for
        this pkg. Indicates where configuration data is stored.
        :return: self
        """
        self._init_common(global_id, self.root)
        if os.path.exists(self.config_path):
            self.load(global_id, self.root)
            return self
        self.config = {
            'sub_pkgs': []
        }
        self.sub_pkgs = []
        self.env_path = f'{self.config_dir}/env.yaml'
        if self.env is None:
            self.env = {}
        os.makedirs(self.config_dir, exist_ok=True)
        if self.shared_dir is not None:
            os.makedirs(self.shared_dir, exist_ok=True)
        self._init()
        return self

    def load(self, global_id=None, root=None, with_config=True):
        """
        Load the configuration of a pkg from the filesystem. Will
        create if it doesn't already exist.

        :param global_id: A dot-separated, globally unique identifier for
        this pkg. Indicates where configuration data is stored.
        :param root: The parent package
        :param with_config: Whether to load pkg configurations
        :return: self
        """
        self._init_common(global_id, root)
        if self.env_path is not None and os.path.exists(self.env_path):
            self.env = YamlFile(self.env_path).load()
        elif self.root is not None:
            self.env = self.root.env
        if not os.path.exists(self.config_path):
            return self.create(global_id)
        if not with_config:
            return self
        self.config = YamlFile(self.config_path).load()
        for sub_pkg_type, sub_pkg_id in self.config['sub_pkgs']:
            sub_pkg = self.jarvis.construct_pkg(sub_pkg_type)
            if sub_pkg is None:
                self.log(f'Could not find pkg: {sub_pkg_type}. Skipping.',
                         Color.RED)
                continue
            sub_pkg.load(f'{self.global_id}.{sub_pkg_id}', self.root)
            self.sub_pkgs.append(sub_pkg)
            self.sub_pkgs_dict[sub_pkg.pkg_id] = sub_pkg
        self._init()
        return self

    def save(self):
        """
        Save a pkg and its sub-pkgs
        :return: Self
        """
        self.config['pkg_type'] = self.pkg_type
        YamlFile(self.config_path).save(self.config)
        if self.env_path is not None:
            YamlFile(self.env_path).save(self.env)
        for pkg in self.sub_pkgs:
            pkg.save()
        return self

    def set_config_env_vars(self, cur_iter_temp=None):
        if cur_iter_temp is not None:
            os.environ['ITER_DIR'] = cur_iter_temp
        os.environ['SHARED_DIR'] = self.shared_dir
        os.environ['PRIVATE_DIR'] = self.private_dir
        os.environ['CONFIG_DIR'] = self.config_dir

    def clear(self):
        """
        Destroy a pipeline's sub-pkgs

        :return: self
        """
        self.reset()
        return self

    def reset(self):
        """
        Destroy a pipeline's sub-pkgs

        :return: self
        """
        try:
            for dir_name in os.listdir(self.config_dir):
                path = os.path.join(self.config_dir, dir_name)
                if os.path.isdir(path):
                    shutil.rmtree(path)
            os.remove(self.config_path)
            self.create(self.global_id)
        except FileNotFoundError:
            pass
        return self

    def get_path(self, config=False, shared=False, private=False, pkg=False):
        if shared:
            return self.shared_dir
        if private:
            return self.private_dir
        if config:
            return self.config_dir
        raise Exception('Config, shared, and private were all false')

    def destroy(self):
        """
        Destroy a pipeline and its sub-pkgs

        :return: None
        """
        for pkg in self.sub_pkgs:
            if pkg is not None:
                pkg.destroy()
        try:
            shutil.rmtree(self.config_dir)
        except FileNotFoundError:
            pass

    def insert(self, at_id, pkg_type, pkg_id=None, do_configure=True, **kwargs):
        """
        Create and append a pkg to the pipeline

        :param at_id: The id of the pkg to insert at
        :param pkg_type: The type of pkg to create (e.g., OrangeFS)
        :param pkg_id: Semantic name of the pkg to create
        :param do_configure: Whether to configure while appending
        :param kwargs: Any parameters the user want to configure in the pkg
        :return: self
        """
        if pkg_id is None:
            pkg_id = self._make_unique_name(pkg_type)
        off = 0
        if at_id is None or len(self.config['sub_pkgs']) == 0:
            self.config['sub_pkgs'].append([pkg_type, pkg_id])
            off = len(self.config['sub_pkgs'])
        else:
            if isinstance(at_id, int):
                off = at_id
            else:
                for sub_pkg_id in self.config['sub_pkgs']:
                    if sub_pkg_id == at_id:
                        break
                    off += 1
            self.config['sub_pkgs'].insert(off, [pkg_type, pkg_id])
        pkg = self.jarvis.construct_pkg(pkg_type)
        if pkg is None:
            raise Exception(f'Could not find pkg: {pkg_type}')
        global_id = f'{self.global_id}.{pkg_id}'
        pkg.create(global_id)
        if do_configure:
            pkg.update_env(self.env)
            pkg.configure(**kwargs)
        self.sub_pkgs.insert(off, pkg)
        self.sub_pkgs_dict[pkg.pkg_id] = pkg
        return self

    def append(self, pkg_type, pkg_id=None, do_configure=True, **kwargs):
        """
        Create and append a pkg to the pipeline

        :param pkg_type: The type of pkg to create (e.g., OrangeFS)
        :param pkg_id: Semantic name of the pkg to create
        :param do_configure: Whether to configure while appending
        :param kwargs: Any parameters the user want to configure in the pkg
        :return: self
        """
        return self.insert(None, pkg_type, pkg_id, do_configure, **kwargs)

    def prepend(self, pkg_type, pkg_id=None, do_configure=True, **kwargs):
        """
        Create and append a pkg to the pipeline

        :param pkg_type: The type of pkg to create (e.g., OrangeFS)
        :param pkg_id: Semantic name of the pkg to create
        :param do_configure: Whether to configure while appending
        :param kwargs: Any parameters the user want to configure in the pkg
        :return: self
        """
        return self.insert(0, pkg_type, pkg_id, do_configure, **kwargs)

    def _make_unique_name(self, pkg_type):
        if self.get_pkg(pkg_type) is None:
            return pkg_type
        count = 1
        while True:
            new_name = f'{pkg_type}{count}'
            if self.get_pkg(new_name) is not None:
                count += 1
            return new_name

    def remove(self, pkg_id):
        """
        Remove a pkg from the pipeline & delete its contents

        :param pkg_id: The name of the pkg to remove
        :return: self
        """
        pkg = self.get_pkg(pkg_id)
        if pkg:
            pkg.destroy()
        self.unlink(pkg_id)
        return self

    def unlink(self, pkg_id):
        """
        Remove a pkg from the pipeline, but keep its contents in case
        it gets added back.

        :param pkg_id: The name of the pkg to remove
        :return: self
        """
        self.sub_pkgs = [test_pkg for test_pkg in self.sub_pkgs
                          if test_pkg.pkg_id != pkg_id]
        self.config['sub_pkgs'] = [
            [test_pkg_type, test_pkg_id]
            for test_pkg_type, test_pkg_id in self.config['sub_pkgs']
            if test_pkg_id != pkg_id]
        return self

    def get_pkg(self, pkg_id):
        """
        Get a pkg in the pipeline.

        :param pkg_id: The pkg id to find
        :return: A pkg
        """
        matches = [pkg for pkg in self.sub_pkgs if pkg.pkg_id == pkg_id]
        if len(matches) == 0:
            return None
        else:
            return matches[0]

    def view_pkgs(self):
        print(self.to_string_pretty())

    def env_show(self):
        print(yaml.dump(self.env))

    def update_env(self, env, mod_env=None):
        """
        Update the current environment for this program

        :param env: The environment dict
        :param mod_env: The modified environment dict
        :return:
        """
        env.update(self.env)
        self.env = env
        self.mod_env = mod_env

    @staticmethod
    def _track_env(env, env_track_dict=None):
        """
        Add and remove cached environment variables.

        :param env_track_dict: a dict of booleans or strings. Boolean indicates
        whether to track the environment variable, which are the keys
        of the dict. String indicates track the variable and set to this value.
        :return: None
        """
        if env_track_dict is None:
            return env
        for key, val in env_track_dict.items():
            if isinstance(val, str):
                env[key] = val
                continue
            if val:
                if key in os.environ:
                    env[key] = os.getenv(key)
                else:
                    env[key] = ''
            else:
                if key in env:
                    del env[key]
        return env

    def track_env(self, env_track_dict=None):
        """
        Add and remove cached environment variables.

        :param env_track_dict: a dict of booleans or strings. Boolean indicates
        whether to track the environment variable, which are the keys
        of the dict. String indicates track the variable and set to this value.
        :return: self
        """
        self.env = self._track_env(self.env, env_track_dict)
        return self

    def scan_env(self, rescan_list=None):
        """
        Re-scan environment variables.

        :param rescan_list: a list of keys to re-scan.
        :return: self
        """
        if rescan_list is None:
            rescan_list = list(self.env.keys())
        for key in rescan_list:
            self.env[key] = os.getenv(key)
        return self

    def prepend_env(self, env_var, path):
        """
        Prepend a path to the an environment variable, such as LD_PRELOAD.

        :param env_var: The name of the environment variable
        :param path: The path to prepend
        :return:
        """
        if env_var == 'LD_PRELOAD':
            env = self.mod_env
        else:
            env = self.env
        if env_var in env:
            cur_env = env[env_var]
        else:
            cur_env = os.getenv(env_var)

        if cur_env is None or len(cur_env) == 0:
            env[env_var] = path
        else:
            env[env_var] = f'{path}:{cur_env}'

    def append_env(self, env_var, path):
        """
        Append a path to the an environment variable, such as LD_PRELOAD.

        :param env_var: The name of the environment variable
        :param path: The path to prepend
        :return:
        """
        if env_var == 'LD_PRELOAD':
            env = self.mod_env
        else:
            env = self.env
        if env_var in env:
            cur_env = env[env_var]
        else:
            cur_env = os.getenv(env_var)

        if cur_env is None or len(cur_env) == 0:
            env[env_var] = path
        else:
            env[env_var] = f'{cur_env}:{path}'

    def setenv(self, env_var, val):
        """
        Set the Jarvis environment variable

        :param env_var: The environment variable
        :param val: The value of the environment variable
        :return:
        """
        self.env[env_var] = val

    def find_library(self, lib_name, env_vars=None):
        """
        Find the location of a shared object automatically using environment
        variables. If None, will search LD_LIBRARY_PATH.

        :param lib_name: The library to search for. We will search for
        any file matching lib{lib_name}.so and {lib_name}.so.
        :param env_vars: A list of environment variables to search for or
        a string for a single variable.
        :return: string or None
        """
        name_opts = [
            f'{lib_name}.so',
            f'lib{lib_name}.so',
        ]
        for name in name_opts:
            exe = Exec(f'cc -print-file-name={name}',
                        LocalExecInfo(env=self.env,
                                      hide_output=True,
                                      collect_output=True))
            res = exe.stdout['localhost'].strip()
            if len(res) and res != name:
                return res
        if env_vars is None:
            env_vars = ['LD_LIBRARY_PATH']

        for env_var in env_vars:
            if env_var not in self.env:
                continue
            paths = self.env[env_var].split(':')
            for path in paths:
                if not os.path.exists(path):
                    continue
                filenames = os.listdir(path)
                for name_opt in name_opts:
                    if name_opt in filenames:
                        return f'{path}/{name_opt}'
        return None

    def __str__(self):
        return self.to_string_pretty()

    def __repr__(self):
        return self.to_string_pretty()

    def to_string_pretty(self):
        return '\n'.join(self.to_string_list_pretty())

    def to_string_list_pretty(self, depth=0):
        space = ' ' * depth
        info = [f'{space}{self.pkg_type} with name {self.pkg_id}']
        for key, val in self.config.items():
            if key == 'sub_pkgs':
                continue
            info.append(f'{space}  {key}={val}')
        for sub_pkg in self.sub_pkgs:
            info += sub_pkg.to_string_list_pretty(depth + 2)
        return info

    @abstractmethod
    def _init(self):
        """
        Initialize variables global to the project.
        Called after load() and create()

        :return:
        """
        pass


class SimplePkg(Pkg):
    """
    A SimplePkg represents a single program. A pipeline is not a SimplePkg
    because it represents a combination of multiple programs.
    """

    def configure_menu(self):
        """
        Add some common configuration options used across all CLI menus.

        :return:
        """
        menu = self._configure_menu()
        menu += [
            {
                'name': 'sleep',
                'msg': 'How much time to sleep during start (seconds)',
                'type': int,
                'default': 0,
            },
            {
                'name': 'reinit',
                'msg': 'Destroy previous configuration and rebuild',
                'type': bool,
                'default': False
            },
            {
                'name': 'do_dbg',
                'msg': 'Enable or disable debugging',
                'type': bool,
                'default': False
            },
            {
                'name': 'dbg_port',
                'msg': 'The port to use for debugging',
                'type': int,
                'default': 4000
            },
            {
                'name': 'stdout',
                'msg': 'The file to use for holding output. Use stderr to'
                       'pipe to the same file as stderr.',
                'type': str,
                'default': None
            },
            {
                'name': 'stderr',
                'msg': 'The file to use for holding error output. Use stdout '
                       'to pipe to the same file as stdout.',
                'type': str,
                'default': None
            },
            {
                'name': 'hide_output',
                'msg': 'Hide output of the runtime.',
                'type': bool,
                'default': False
            },
        ]
        return menu

    @abstractmethod
    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return []

    def configure(self, **kwargs):
        if 'reinit' not in kwargs:
            kwargs['reinit'] = False
        if 'stdout' not in kwargs:
            kwargs['stdout'] = None
        if 'stderr' not in kwargs:
            kwargs['stderr'] = None
        if kwargs['stdout'] == 'stderr':
            kwargs['stdout'] = kwargs['stderr']
        if kwargs['stderr'] == 'stdout':
            kwargs['stderr'] = kwargs['stdout']
        self.update_config(kwargs, rebuild=kwargs['reinit'])
        self._configure(**kwargs)

    @abstractmethod
    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: The human-readable jarvis YAML configuration for the
        application.
        :return: None
        """
        pass

    def update_config(self, kwargs, rebuild=False):
        """
        The kwargs to pack with default values

        :param kwargs: the key-word arguments to fill default values for
        :param rebuild: whether to reinitialize self.config
        from self.conifgure_menu
        :return:
        """
        Mkdir(self.private_dir,
              PsshExecInfo(hostfile=self.jarvis.hostfile))
        menu = self.configure_menu()
        menu_keys = {m['name']: True for m in menu}
        args = []
        # Convert kwargs into a list of CLI strings
        for key, val in kwargs.items():
            if val is not None:
                args.append(f'{key}={val}')
            else:
                args.append(f'{key}=')
        parser = PkgArgParse(args=args, menu=menu)
        if rebuild:
            # This will overwrite the entire configuration
            # Any parameters unspecified in the input kwargs dict
            # will be set to their default value
            self.config.update(parser.kwargs)
        else:
            # This will update the config with only the
            # parameters specified in the input kwargs dict.
            self.config.update(parser.real_kwargs)
            # If a pipeline existed before an update was made to this
            # pkg changing the parameter sets, this will ensure
            # that the config is updated with the new parameters.
            for key in parser.kwargs.keys():
                if key not in self.config:
                    self.config[key] = parser.kwargs[key]
        # This will ensure the kwargs dict contains all
        # CLI-configurable values for this pkg. The config
        # contains many parameters that may be set internally
        # by the application.
        for key, val in self.config.items():
            if key not in menu_keys:
                continue
            kwargs[key] = val

    @staticmethod
    def copy_template_file(src, dst, replacements=None):
        """
        Copy and configure an application template file
        Template files makr constants using the notation
        ##CONST_NAME##

        :param src: Path to the template
        :param dst: Destination of the template
        :param replacements: A list of 2-tuples or dict. First entry is the name
        of the constant to replace, right is the value to replace it with.
        :return: None
        """
        with open(src, 'r', encoding='utf-8') as fp:
            text = fp.read()
        if replacements is not None:
            if isinstance(replacements, list):
                for const_name, replace in replacements:
                    text = text.replace(f'##{const_name}##', str(replace))
            elif isinstance(replacements, dict):
                for const_name, replace in replacements.items():
                    text = text.replace(f'##{const_name}##', str(replace))
        with open(dst, 'w', encoding='utf-8') as fp:
            fp.write(text)


class Interceptor(SimplePkg):
    """
    An interceptor is a library which routes function calls to a custom
    function. This typically requires modifications to various environment
    variables, including LD_PRELOAD.
    """

    @abstractmethod
    def modify_env(self):
        """
        Modify the jarvis environment.

        :return: None
        """
        pass


class Service(SimplePkg):
    """
    A long-running service.
    """
    @abstractmethod
    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        pass

    @abstractmethod
    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return:
        """
        pass

    @abstractmethod
    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass

    @abstractmethod
    def status(self):
        """
        Check whether or not an application is running. E.g., are OrangeFS
        servers running?

        :return: True or false
        """
        pass


class Application(Service):
    """
    An application is a process which will terminate on its own eventually.
    This can be a benchmark program, such as IOR, for example.
    """

    def status(self):
        return True


class Pipeline(Pkg):
    """
    A pipeline connects the different pkg types together in a chain.
    """
    def _init(self):
        pass

    def configure(self, pkg_id, **kwargs):
        """
        Configure a pkg in the pipeline

        :param pkg_id: The semantic name of the pkg to configure
        :param config: Configuration parameters
        :return:
        """
        pkg = self.get_pkg(pkg_id)
        if pkg is None:
            raise Exception(f'Could not find pkg: {pkg_id}')
        pkg.update_env(self.env)
        pkg.configure(**kwargs)

    def build_env(self, env_track_dict=None):
        """
        Build the environment variable cache for this pkg.

        :param env_track_dict: a dict of booleans. Boolean indicates whether
        to track the environment variable, which are the keys of the dict.
        :return: self
        """
        exec_info = LocalExecInfo()
        self.env = exec_info.basic_env
        self.track_env(env_track_dict)
        self.update()
        return self

    def build_static_env(self, env_name, env_track_dict=None):
        """
        Build a global environment cache that can be re-used across pipelines

        :param env_name: The name of the environment to create
        :param env_track_dict: a dict of booleans. Boolean indicates whether
        to track the environment variable, which are the keys of the dict.
        :return: self
        """
        exec_info = LocalExecInfo()
        self.env = exec_info.basic_env
        self.track_env(env_track_dict)
        static_env_path = os.path.join(self.jarvis.env_dir, f'{env_name}.yaml')
        YamlFile(static_env_path).save(self.env)
        return self

    def from_yaml(self, path, do_configure=True):
        """
        Create a pipeline from a YAML file

        :param path:
        :param do_configure: Whether to append and configure
        :return: self
        """
        config = YamlFile(path).load()
        if 'loop' in config:
            return self.from_yaml_iter_dict(config, path, do_configure)
        else:
            return self.from_yaml_dict(config, path, do_configure)

    def from_yaml_dict(self, config, path=None, do_configure=True):
        """
        Create a pipeline from a YAML dict

        :param path:
        :param do_configure: Whether to append and configure
        :return: self
        """
        pipeline_id = config['name']
        self.create(pipeline_id)
        self.reset()
        if path:
            self.config['JARVIS_YAML_PATH'] = path
        if 'env' in config:
            self.copy_static_env(config['env'])
        for sub_pkg in config['pkgs']:
            pkg_type = sub_pkg['pkg_type']
            pkg_name = sub_pkg['pkg_name']
            del sub_pkg['pkg_type']
            del sub_pkg['pkg_name']
            self.append(pkg_type, pkg_name,
                        do_configure, **sub_pkg)
        return self

    def from_yaml_iter_dict(self, config, path=None, do_configure=True):
        """
        Create a pipeline + iterator from a YAML file
        YAML format:
        config:
          name: pipeline_name
          pkgs:
            - pkg_type: OrangeFS
              pkg_name: orangefs
              num_servers: 2
              num_clients: 4
        vars:
            pkg_id:
              - var1: [val1, val2, val3]
              - var2: [val1, val2, val3]
              - var3: [hello]
        loop:
            - [pkg_name.var1, pkg_name.var2]
            - [pkg_name.var3]
        output: my_dir

        :param path:
        :param do_configure: Whether to append and configure
        :return: self
        """
        self.from_yaml_dict(config['config'], path, do_configure)
        self.config['iterator'] = {}
        self.config['iterator']['vars'] = config['vars']
        self.config['iterator']['loop'] = config['loop']
        self.config['iterator']['output'] = config['output']
        self.config['iterator']['repeat'] = config['repeat']
        if 'norerun' in config:
            self.config['iterator']['norerun'] = config['norerun']
        return self

    def get_static_env_path(self, env_name):
        """
        Get the path to the static environment

        :param env_name: The name of the environment
        :return: str
        """
        return os.path.join(self.jarvis.env_dir, f'{env_name}.yaml')

    def copy_static_env(self, env_name, env_track_dict=None):
        """
        Copy a cached environment to this pipeline

        :param env_name: The name of the environment to create
        :param env_track_dict: a dict of booleans. Boolean indicates whether
        to track the environment variable, which are the keys of the dict.
        :return: self
        """
        static_env_path = self.get_static_env_path(env_name)
        self.env = YamlFile(static_env_path).load()
        self.track_env(env_track_dict)
        self.update()
        return self

    def static_env_show(self, env_name):
        """
        View the contents of the static environment

        :param env_name:  The name of the environment to show
        :return: self
        """
        static_env_path = self.get_static_env_path(env_name)
        env = YamlFile(static_env_path).load()
        print(yaml.dump(env))
        return self

    def destroy_static_env(self, env_name):
        """
        Destroy a static environment file

        :param env_name: The name of the environment to create
        :return: self
        """
        static_env_path = self.get_static_env_path(env_name)
        os.remove(static_env_path)
        return self

    def list_static_env(self):
        """
        Destroy a static environment file

        :param env_name: The name of the environment to create
        """
        envs = os.listdir(self.jarvis.env_dir)
        for env in envs:
            print(env)
        return self

    def update_yaml(self):
        """
        Reload the pipeline from the stored yaml file
        """
        if 'JARVIS_YAML_PATH' in self.config:
            self.from_yaml(self.config['JARVIS_YAML_PATH'])
        else:
            self.update()
        return self

    def update(self):
        """
        Re-run configure on all sub-pkgs.

        :return: self
        """
        for pkg in self.sub_pkgs:
            pkg.env = self.env
            pkg.configure()
        return self

    def run_iter(self, resume=False):
        """
        Run the pipeline repeatedly with new configurations
        """
        if resume:
            self.log('[ITER] resume=True')
        self.iterator = PipelineIterator(self)
        conf_dict = self.iterator.begin()
        while conf_dict is not None:
            self.clean(with_iter_out=False)
            for i in range(self.iterator.repeat):
                cur_iter_tmp = os.path.join(
                    self.iterator.iter_out,
                    f'{self.iterator.iter_count}-{i}')
                self.set_config_env_vars(cur_iter_tmp)
                self.log(f'[ITER] Iteration'
                         f'[(param) {self.iterator.iter_count + 1}/ \
                         {self.iterator.max_iter_count}]'
                         f'[(rep) {i + 1}/{self.iterator.repeat}]: '
                         f'{self.iterator.linear_conf_dict}', Color.BRIGHT_BLUE)
                self.iterator.config_pkgs(conf_dict)
                self.run(kill=True)
                self.iterator.save_run(conf_dict)
                self.clean(with_iter_out=False)
            conf_dict = self.iterator.next()
        self.log('[ITER] Beginning analysis', Color.BRIGHT_BLUE)
        self.iterator.analysis()
        self.log('[ITER] Finished analysis', Color.BRIGHT_BLUE)
        self.log(f'[ITER] Stored results in: {self.iterator.stats_path}',
                 Color.BRIGHT_BLUE)

    def run(self, kill=False):
        """
        Start and stop the pipeline

        :param kill: Whether to kill the pipeline
        :return: None
        """
        self.start()
        if kill:
            self.kill()
        else:
            self.stop()

    def start(self):
        """
        Start the pipeline.

        NOTE: Start CAN hang for pipelines which spawn
        daemonized processes. This is because input/output is
        too useful to ignore. Python will attempt to close all
        file descriptors when the process exits, so the file descriptor
        used for piping output will be open for as long as the daemon.
        If using start directly, you should launch as background process.

        :return: None
        """
        self.mod_env = self.env.copy()
        for pkg in self.sub_pkgs:
            if pkg.skip_run:
                self.log(f'[RUN] (skipping) {pkg.pkg_id}: Start',
                         color=Color.YELLOW)
            else:
                self.log(f'[RUN] {pkg.pkg_id}: Start', color=Color.GREEN)

            start = time.time()
            if isinstance(pkg, Service):
                pkg.update_env(self.env, self.mod_env)
                pkg.start()
            if isinstance(pkg, Interceptor):
                pkg.update_env(self.env, self.mod_env)
                pkg.modify_env()
                self.mod_env.update(self.env)
            self.exit_code += pkg.exit_code
            end = time.time()
            pkg.start_time = end - start
            self.log(f'[RUN] {pkg.pkg_id}: '
                     f'Start finished in {pkg.start_time} seconds',
                     color=Color.GREEN)

    def stop(self):
        """
        Stop the pipeline

        :return: None
        """
        for pkg in reversed(self.sub_pkgs):
            self.log(f'[RUN] {pkg.pkg_id}: Stop', color=Color.GREEN)
            start = time.time()
            if isinstance(pkg, Service):
                pkg.update_env(self.env, self.mod_env)
                pkg.stop()
            end = time.time()
            pkg.stop_time = end - start
            self.log(f'[RUN] {pkg.pkg_id}: '
                     f'Stop finished in {pkg.stop_time} seconds',
                     color=Color.GREEN)

    def kill(self):
        """
        Stop the pipeline

        :return: None
        """
        for pkg in reversed(self.sub_pkgs):
            self.log(f'[RUN] {pkg.pkg_id}: Killing', color=Color.GREEN)
            if isinstance(pkg, Service):
                pkg.update_env(self.env, self.mod_env)
                if hasattr(pkg, 'kill'):
                    pkg.kill()
                else:
                    pkg.stop()
            self.log(f'[RUN] {pkg.pkg_id}: Finished killing', color=Color.GREEN)

    def clean(self, with_iter_out=True):
        """
        Clean the pipeline

        with_iter_out: Clean the iteration output
        :return: None
        """
        for pkg in reversed(self.sub_pkgs):
            if pkg.skip_run:
                self.log(f'[RUN] (skipping) {pkg.pkg_id}: Cleaning',
                         color=Color.YELLOW)
            else:
                self.log(f'[RUN] {pkg.pkg_id}: Cleaning', color=Color.GREEN)
            if isinstance(pkg, Service):
                pkg.update_env(self.env, self.mod_env)
                pkg.clean()
            self.log(f'[RUN] {pkg.pkg_id}: Finished cleaning',
                     color=Color.GREEN)
        if with_iter_out and 'iterator' in self.config:
            self.iterator = PipelineIterator(self)
            Rm(self.iterator.iter_out)

    def status(self):
        """
        Get the status of the pipeline

        :return: None
        """
        statuses = []
        for pkg in reversed(self.sub_pkgs):
            self.log(f'[RUN] {pkg.pkg_id}: Getting status', color=Color.GREEN)
            status = None
            if isinstance(pkg, Service):
                pkg.update_env(self.env, self.mod_env)
                status = pkg.status()
                statuses.append(status)
            self.log(f'[RUN] {pkg.pkg_id}: Status was {status}',
                     color=Color.GREEN)
        return math.prod(statuses)


class PipelineIndex:
    """
    Manage pipeline indexes for Jarvis
    """
    def __init__(self, index_query):
        self.jarvis = JarvisManager.get_instance()
        self.inex_query = index_query
        self.index_path = self.to_path(index_query)

    def to_path(self, index_query):
        """
        Converts an index query to pipeline index
        """
        split_query = index_query.split('.')
        repo_name = split_query[0]
        repo = self.jarvis.get_repo(repo_name)
        if repo is None:
            print(f'Could not find repo {repo_name}')
            return
        repo_path = repo['path']
        root_index_path = os.path.join(repo_path, 'pipelines')
        base_index_path = os.path.join(root_index_path, *split_query[1:])
        if not os.path.exists(root_index_path):
            print(f'repo {repo_name} has no pipeline indexes')
            return
        index_path = self._find_ext(base_index_path)
        if not os.path.exists(index_path):
            print(f'Could not find index {index_query} ({index_path})')
            return
        return index_path

    def _find_ext(self, base_path):
        for ext in ['', '.yaml', '.yml']:
            path = f'{base_path}{ext}'
            if os.path.exists(path):
                return path
        return None

    def show(self):
        """
        Print all pipeline indexes

        :return: None
        """
        if self.index_path is None:
            return self
        yamls = []
        dirs = []
        for pipeline in os.listdir(self.index_path):
            if pipeline.endswith('.yaml'):
                yamls.append(pipeline.replace('.yaml', ''))
            elif os.path.isdir(os.path.join(self.index_path, pipeline)):
                dirs.append(pipeline)

        print('SCRIPTS:')
        for script in yamls:
            print(f'  |- {script}')

        print('SUB INDEXES:')
        for subrepo in dirs:
            print(f'  |- {subrepo}')
        return self

    def copy(self, output_path):
        if self.index_path is None:
            return self
        if output_path is None:
            output_path = os.getcwd()
        shutil.copy2(self.index_path, output_path)
        return self

    def load_script(self):
        if self.index_path is None:
            return self
        pipeline = Pipeline().from_yaml(self.index_path).save()
        # try:
        #     pipeline = Pipeline().from_yaml(self.index_path).save()
        # except:
        #     print(f'Could not load pipeline {self.index_path}')
        #     return self
        self.jarvis.cd(pipeline.global_id)
        return self

    def save(self):
        self.jarvis.save()
        return self
```

### `jarvis_cd/template/__init__.py`

```python

```

### `jarvis_cd/template/app_templ.py`

```python
"""
This module provides classes and methods to launch the MyPkg application.
MyPkg is ....
"""

from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class MyPkg(Application):
    """
    This class provides methods to launch the MyPkg application.
    """

    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                "name": None,  # The name of the parameter
                "msg": "",  # Describe this parameter
                "type": str,  # What is the parameter type?
                "default": None,  # What is the default value if not required?
                # Does this parameter have specific valid inputs?
                "choices": [],
                # When type is list, what do the entries of the list mean?
                # A list of dicts just like this one.
                "args": [],
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        pass

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def kill(self):
        """
        Forcibly a running application. E.g., OrangeFS will terminate the
        servers, clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass

    def _get_stat(self, stat_dict):
        """
        Get statistics from the application.

        :param stat_dict: A dictionary of statistics.
        :return: None
        """
        stat_dict[f'{self.pkg_id}.runtime'] = self.start_time
```

### `jarvis_cd/template/interceptor_templ.py`

```python
"""
This module provides classes and methods to inject the MyPkg interceptor.
MyPkg is ....
"""
from jarvis_cd.basic.pkg import Interceptor
from jarvis_util import *


class MyPkg(Interceptor):
    """
    This class provides methods to inject the MyPkg interceptor.
    """
    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': None,  # The name of the parameter
                'msg': '',  # Describe this parameter
                'type': str,  # What is the parameter type?
                'default': None,  # What is the default value if not required?
                # Does this parameter have specific valid inputs?
                'choices': [],
                # When type is list, what do the entries of the list mean?
                # A list of dicts just like this one.
                'args': [],
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def modify_env(self):
        """
        Modify the jarvis environment.

        :return: None
        """
        pass
```

### `jarvis_cd/template/service_templ.py`

```python
"""
This module provides classes and methods to launch the MyPkg service.
MyPkg is ....
"""

from jarvis_cd.basic.pkg import Service
from jarvis_util import *


class MyPkg(Service):
    """
    This class provides methods to launch the MyPkg service.
    """

    def _init(self):
        """
        Initialize paths
        """
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                "name": None,  # The name of the parameter
                "msg": "",  # Describe this parameter
                "type": str,  # What is the parameter type?
                "default": None,  # What is the default value if not required?
                # Does this parameter have specific valid inputs?
                "choices": [],
                # When type is list, what do the entries of the list mean?
                # A list of dicts just like this one.
                "args": [],
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param kwargs: Configuration parameters for this pkg.
        :return: None
        """
        pass

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        pass

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        pass

    def kill(self):
        """
        Forcibly a running application. E.g., OrangeFS will terminate the
        servers, clients, and metadata services.

        :return: None
        """
        pass

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        pass

    def status(self):
        """
        Check whether or not an application is running. E.g., are OrangeFS
        servers running?

        :return: True or false
        """
        return True
```

### `logg.txt`

```
Hello World
```

### `meta.yaml`

```yaml
package:
  name: jarvis_cd
  version: 0.0.0

source:
  git_url: https://github.com/iowarp/platform-plugins-interface
  git_depth: 1

requirements:
  build:
    - python
    - setuptools
  run:
    - python
    - iowarp::jarvis_util    

files:
  - README.md

test:
  requires:
    - pyaml
    - pandas
    - iowarp::jarvis_util
  imports:
    - jarvis_cd


about:
  home: https://grc.iit.edu/research/projects/iowarp/
  license: BSD
  summary: IOWarp Jarvis CD Conda Package
```

### `pr.sh`

```bash
#!/bin/bash
# git remote add iowarp https://github.com/iowarp/platform-plugins-interface.git
# git remote add grc https://github.com/grc-iit/jarvis-cd.git
gh pr create --title $1 --body "" --repo=grc-iit/jarvis-cd
gh pr create --title $1 --body "" --repo=iowarp/platform-plugins-interface
```

### `test/__init__.py`

```python

```

### `test/unit/__init__.py`

```python

```

### `test/unit/pipeline.yaml`

```yaml
name: test_ppl
env: mega_mmap
pkgs:
  - pkg_type: hermes_run
    pkg_name: hermes_run
    sleep: 6
    include: ${HOME}/mm_data
    pqdepth: 8
    qdepth: 64
    ram: 24g
    do_dbg: true
    dbg_port: 4000
  - pkg_type: ior
    pkg_name: ior
```

### `test/unit/pipeline_iter.yaml`

```yaml
config:
  name: test_ppl
  env: mega_mmap
  pkgs:
    - pkg_type: first
      pkg_name: first
    - pkg_type: second
      pkg_name: second
    - pkg_type: third
      pkg_name: third
vars:
  first.port: [1, 2, 3]
  second.port: [4, 5, 6]
  third.port: [7, 8, 9]
loop:
  - [first.port, second.port]
  - [third.port]
repeat: 3
output: "$SHARED_DIR/output"
```

### `test/unit/test_cli.py`

```python
"""
Test CLI unit test class
"""
from jarvis_util.shell.local_exec import LocalExecInfo
from jarvis_util.shell.exec import Exec
from jarvis_cd.basic.jarvis_manager import JarvisManager
from jarvis_cd.basic.pkg import Pipeline
from unittest import TestCase
import os
import yaml


class TestCli(TestCase):
    """
    Test jarvis CLI
    """
    def add_test_repo(self):
        self.jarvis = JarvisManager.get_instance()
        path = f'{self.jarvis.jarvis_root}/test/unit/test_repo'
        Exec(f'jarvis repo add {path}')
        self.jarvis.load()

    def rm_test_repo(self):
        self.jarvis = JarvisManager.get_instance()
        Exec('jarvis repo remove test_repo')
        self.jarvis.load()

    def test_jarvis_repo(self):
        # Add repo
        self.jarvis = JarvisManager.get_instance()
        self.add_test_repo()
        repo = self.jarvis.get_repo('test_repo')
        self.assertEqual(repo['name'], 'test_repo')

        # Promote repo
        self.assertEqual(self.jarvis.repos[0]['name'], 'test_repo')
        Exec('jarvis repo promote builtin')
        self.jarvis.load()
        self.assertEqual(self.jarvis.repos[0]['name'], 'builtin')

        # Remove repo
        self.rm_test_repo()
        repo = self.jarvis.get_repo('test_repo')
        self.assertTrue(repo is None)

    def test_jarvis_create_cd_rm(self):
        self.jarvis = JarvisManager.get_instance()
        # Create pipelines
        Exec('jarvis pipeline create test_pipeline')
        Exec('jarvis pipeline create test_pipeline2')
        self.assertTrue(os.path.exists(
            f'{self.jarvis.config_dir}/test_pipeline'))
        self.assertTrue(os.path.exists(
            f'{self.jarvis.config_dir}/test_pipeline/test_pipeline.yaml'))
        self.jarvis.load()

        # Cd into test_pipeline
        self.assertEqual(self.jarvis.cur_pipeline, 'test_pipeline2')
        Exec('jarvis cd test_pipeline')
        self.jarvis.load()
        self.assertEqual(self.jarvis.cur_pipeline, 'test_pipeline')

        # Get path to the pipeline
        pkg = Exec('jarvis path test_pipeline',
                    LocalExecInfo(collect_output=True))
        path = pkg.stdout['localhost'].strip()
        self.assertEqual(path, f'{self.jarvis.config_dir}/test_pipeline')

        # Delete the pipelines
        Exec('jarvis pipeline destroy test_pipeline')
        Exec('jarvis pipeline destroy test_pipeline2')
        self.assertFalse(
            os.path.exists(f'{self.jarvis.config_dir}/test_pipeline'))
        self.assertFalse(
            os.path.exists(f'{self.jarvis.config_dir}/test_pipeline2'))

    def test_jarvis_append(self):
        self.jarvis = JarvisManager.get_instance()

        # Remove the pipeline
        Exec('jarvis pipeline destroy test_pipeline')
        self.assertTrue(
            not os.path.exists(f'{self.jarvis.config_dir}/test_pipeline'))
        self.rm_test_repo()

        # Create the pipeline
        self.add_test_repo()
        Exec('jarvis pipeline create test_pipeline')
        self.assertTrue(
            os.path.exists(f'{self.jarvis.config_dir}/test_pipeline'))
        exec_pkg = Exec('jarvis pipeline append first '
                         '--port=22 --devices=[[nvme,1]]',
                         LocalExecInfo(collect_output=True))
        self.assertTrue(
            os.path.exists(f'{self.jarvis.config_dir}/test_pipeline/first'))
        config_dict = yaml.safe_load(exec_pkg.stdout['localhost'])
        self.assertTrue(config_dict['port'] == 22)
        self.assertTrue(config_dict['devices'] == [['nvme', 1]])
        Exec('jarvis pipeline append second')
        self.assertTrue(
            os.path.exists(f'{self.jarvis.config_dir}/test_pipeline/second'))
        Exec('jarvis pipeline append third')
        self.assertTrue(
            os.path.exists(f'{self.jarvis.config_dir}/test_pipeline/third'))

        # Start the pipeline
        exec_pkg = Exec('jarvis pipeline start',
                         LocalExecInfo(collect_output=True))
        expected_lines = ['first start',
                          'second modify_env',
                          'third start']
        self.verify_pipeline(exec_pkg.stdout, expected_lines)

        # Stop the pipeline
        exec_pkg = Exec('jarvis pipeline stop',
                         LocalExecInfo(collect_output=True))
        expected_lines = ['third stop',
                          'first stop']
        self.verify_pipeline(exec_pkg.stdout, expected_lines)

        # Clean the pipeline
        exec_pkg = Exec('jarvis pipeline clean',
                         LocalExecInfo(collect_output=True))
        expected_lines = ['third clean',
                          'first clean']
        self.verify_pipeline(exec_pkg.stdout, expected_lines)

        # Status the pipeline
        exec_pkg = Exec('jarvis pipeline status',
                         LocalExecInfo(collect_output=True))
        expected_lines = ['first status']
        self.verify_pipeline(exec_pkg.stdout, expected_lines)

        # Remove the pipeline
        Exec('jarvis pipeline destroy test_pipeline')
        self.assertTrue(
            not os.path.exists(f'{self.jarvis.config_dir}/test_pipeline'))
        self.rm_test_repo()

    def test_jarvis_load_yaml(self):
        self.jarvis = JarvisManager.get_instance()
        path = f'{self.jarvis.jarvis_root}/test/unit/pipeline.yaml'
        pipeline = Pipeline().from_yaml(path).save()
        self.jarvis.cd(pipeline.global_id)
        self.jarvis.save()

    def verify_pipeline(self, stdout, expected_lines):
        lines = stdout['localhost'].strip().splitlines()
        for line, expected_line in zip(lines, expected_lines):
            self.assertEqual(line, expected_line)
```

### `test/unit/test_repo/__init__.py`

```python

```

### `test/unit/test_repo/test_repo/__init__.py`

```python

```

### `test/unit/test_repo/test_repo/first/__init__.py`

```python

```

### `test/unit/test_repo/test_repo/first/pkg.py`

```python
"""
First pkg example
"""
from jarvis_cd.basic.pkg import Service
from jarvis_util import *


class First(Service):
    """
    Service example
    """
    def _init(self):
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'walkthrough',
                'msg': 'Use a terminal walkthrough to modify resource graph',
                'type': bool,
                'default': False,
            },
            {
                'name': 'devices',
                'msg': 'Search for a number of devices to include',
                'type': list,
                'default': None,
                'args': [
                    {
                        'name': 'type',
                        'msg': 'The type of the device being queried',
                        'type': str
                    },
                    {
                        'name': 'count',
                        'msg': 'The number of devices being',
                        'type': int
                    }
                ]
            },
            {
                'name': 'port',
                'msg': 'The port to listen for data on',
                'type': int
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param config: The human-readable jarvis YAML configuration for the
        application.
        :return: None
        """
        print(f'{kwargs}')

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        print('first start')

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        print('first stop')

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        print('first clean')

    def status(self):
        """
        Check whether or not an application is running. E.g., are OrangeFS
        servers running?

        :return: True or false
        """
        print('first status')
        return True
```

### `test/unit/test_repo/test_repo/second/__init__.py`

```python

```

### `test/unit/test_repo/test_repo/second/pkg.py`

```python
"""
Second pkg example
"""
from jarvis_cd.basic.pkg import Interceptor
from jarvis_util import *


class Second(Interceptor):
    """
    Interceptor example
    """
    def _init(self):
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'port',
                'msg': 'The port to listen for data on',
                'type': int
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param config: The human-readable jarvis YAML configuration for the
        application.
        :return: None
        """
        print(f'{kwargs}')

    def _get_stat(self, stat_dict):
        """
        Get statistics from the application.

        :param stat_dict: A dictionary of statistics.
        :return: None
        """
        stat_dict[f'{self.pkg_id}.runtime'] = self.start_time

    def modify_env(self):
        """
        Modify the jarvis environment.

        :return: None
        """
        print('second modify_env')
```

### `test/unit/test_repo/test_repo/third/__init__.py`

```python

```

### `test/unit/test_repo/test_repo/third/pkg.py`

```python
"""
Third pkg example
"""
from jarvis_cd.basic.pkg import Application
from jarvis_util import *


class Third(Application):
    """
    Application example
    """
    def _init(self):
        pass

    def _configure_menu(self):
        """
        Create a CLI menu for the configurator method.
        For thorough documentation of these parameters, view:
        https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing

        :return: List(dict)
        """
        return [
            {
                'name': 'port',
                'msg': 'The port to listen for data on',
                'type': int
            },
        ]

    def _configure(self, **kwargs):
        """
        Converts the Jarvis configuration to application-specific configuration.
        E.g., OrangeFS produces an orangefs.xml file.

        :param config: The human-readable jarvis YAML configuration for the
        application.
        :return: None
        """
        print(f'{kwargs}')

    def start(self):
        """
        Launch an application. E.g., OrangeFS will launch the servers, clients,
        and metadata services on all necessary pkgs.

        :return: None
        """
        print('third start')

    def stop(self):
        """
        Stop a running application. E.g., OrangeFS will terminate the servers,
        clients, and metadata services.

        :return: None
        """
        print('third stop')

    def clean(self):
        """
        Destroy all data for an application. E.g., OrangeFS will delete all
        metadata and data directories in addition to the orangefs.xml file.

        :return: None
        """
        print('third clean')
```
