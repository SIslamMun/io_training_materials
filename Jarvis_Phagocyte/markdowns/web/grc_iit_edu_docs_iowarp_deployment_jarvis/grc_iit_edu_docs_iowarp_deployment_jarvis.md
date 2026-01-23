  * [](https://grc.iit.edu/)
  * [IOWarp](https://grc.iit.edu/docs/category/iowarp)
  * Deployment
  * Jarvis-CD


On this page
# Jarvis-CD
Jarvis-CD is a unified platform for deploying various applications, including storage systems and benchmarks. Many applications have complex configuration spaces and are difficult to deploy across different machines.
We provide a builtin repo which contains various applications to deploy. We refer to applications as "jarivs pkgs" which can be connected to form "deployment pipelines".
## Installation[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#installation "Direct link to Installation")
  * IoWarp
  * Spack
  * Pip


If you installed iowarp already, Jarvis-CD is a dependency. No need to install anything further. Go to the next section.
### Install Spack[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#install-spack "Direct link to Install Spack")
```
cd ${HOME}  
git clone https://github.com/spack/spack.git  
cd spack  
git checkout tags/v0.22.2  
echo ". ${PWD}/share/spack/setup-env.sh" >> ~/.bashrc  
source ~/.bashrc  

```

### Clone the IOWarp Spack Repo[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#clone-the-iowarp-spack-repo "Direct link to Clone the IOWarp Spack Repo")
```
cd ${HOME}  
git clone https://github.com/iowarp/iowarp-install.git  
spack repo add iowarp-install/iowarp-spack  

```

### Install[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#install "Direct link to Install")
```
spack external find python  
spack install py-ppi-jarvis-cd  

```

Spack packages must be loaded to use them. You'll have to do this for each new terminal.
```
spack load py-ppi-jarvis-cd  

```

### Jarvis-Util[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#jarvis-util "Direct link to Jarvis-Util")
Jarvis-CD depends on jarvis-util. jarvis-util contains functions to execute binaries in python and collect their output.
```
git clone https://github.com/grc-iit/jarvis-util.git  
cd jarvis-util  
python3 -m pip install -r requirements.txt  
python3 -m pip install -e .  

```

### Jarvis-CD[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#jarvis-cd-1 "Direct link to Jarvis-CD")
```
cd /path/to/jarvis-cd  
python3 -m pip install -r requirements.txt  
python3 -m pip install -e .  

```

### Net Test[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#net-test "Direct link to Net Test")
Network test tool for identifying valid networks.
```
spack install ppi-chi-nettest  

```

## Building the Jarvis Configuration[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#building-the-jarvis-configuration "Direct link to Building the Jarvis Configuration")
Jarvis packages provide 3 ways to configure Hermes:
  * Single Machine
  * Existing Machine
  * New Configuration


### Bootstrapping for a single-node machine[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#bootstrapping-for-a-single-node-machine "Direct link to Bootstrapping for a single-node machine")
For testing on a single node, use:
```
jarvis bootstrap from local  

```

### Bootstrapping from a specific machine[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#bootstrapping-from-a-specific-machine "Direct link to Bootstrapping from a specific machine")
Jarvis has been pre-configured on some machines. This includes machines at IIT, Sandia, and Argonne.
To bootstrap on one of them, run the following:
```
jarvis bootstrap from [machine-name]  

```

See available machines with:
```
jarvis bootstrap list  

```

NOTE: If you are unsure which machine is yours, you probably should read the New Configuration tab instead. Don't bootstrap from a random machine -- it will break your deployments.
### Initialize jarvis configuration[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#initialize-jarvis-configuration "Direct link to Initialize jarvis configuration")
A configuration can be generated as follows:
```
jarvis init [CONFIG_DIR] [PRIVATE_DIR] [SHARED_DIR]  

```

  * **CONFIG_DIR:** A directory where jarvis metadata for pkgs and pipelines are stored. This directory can be anywhere that the current user can access.
  * **PRIVATE_DIR:** A directory which is common across all machines, but stores data locally to the machine. Some jarvis pkgs require certain data to be stored per-machine. OrangeFS is an example.
  * **SHARED_DIR:** A directory which is common across all machines, where each machine has the same view of data in the directory.


For a personal machine, these directories can be the same directory.
## Set or Change the active Hostfile[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#set-or-change-the-active-hostfile "Direct link to Set or Change the active Hostfile")
The hostfile contains the set of nodes that the pipeline will run over. This is structured the same way as a traditional MPI hostfile.
An example hostfile:
```
ares-comp-20  
ares-comp-[21-25]  

```

To set the active hostfile, run:
```
jarvis hostfile set /path/to/hostfile  

```

Note that every time you change the hostfile, you will need to update the pipeline. Jarvis does not automatically detect changes to this file.
```
jarvis ppl update  

```

## Building a Resource Graph[​](https://grc.iit.edu/docs/iowarp/deployment/jarvis/#building-a-resource-graph "Direct link to Building a Resource Graph")
NOTE: This step only needs to be run if you did `jarvis bootstrap from local` or `jarvis init`. If you bootstrap from a specific machine, then skip this section.
The resource graph is a snapshot of your systems network and storage. Many packages depend on it for their configurations. The Hermes I/O system, for example, uses this to identify valid networks and buffering locations.
```
jarvis rg build  

```

This command only needs to be run once for the duration of Jarvis (or whenever your resources change). For example, if you get a new hard drive, you should re-run this command.
NOTE: Make sure the hostfile contains a representative set of nodes. General rules:
  1. If you are trying to do multi-node deployments, make sure the hostfile contains at least two nodes before running this command. This will allow us to introspect valid networks between hosts.
  2. In addition, make sure that the nodes are representative of the machine. For example, if you plan to do multi-node deployments, the master node probably should not even be introspected.


[Previous Deployment Overview](https://grc.iit.edu/docs/iowarp/deployment/index)[Next Deploy Hermes Alone](https://grc.iit.edu/docs/iowarp/deployment/deploy-hermes-solo)
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
