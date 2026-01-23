  * [](https://grc.iit.edu/)
  * Jarvis
  * jarvis-cd
  * Building a Package


On this page
# Building a Package
This guide documents how to extend the set of applications that Jarvis is able to deploy. We refer to these as packages (pkgs for short).
## AI Bindings[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#ai-bindings "Direct link to AI Bindings")
Our llm info file is located [here](https://github.com/iowarp/ppi-jarvis-cd/blob/main/llm-repo.md). This is used for context for the AI to understand how to build a jarvis package.
At a high-level, you can use the following style of prompt to create a jarvis package. This example is for building a package for top.
```
The jarvis repo is located at `builtin`. Create a new package in this repo named `top`. Make it so I can deploy top on a series of nodes with parallel SSH.  
  
The documentation for jarvis is attached as context.  

```

## Bootstrap a `Pkg`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#bootstrap-a-pkg "Direct link to bootstrap-a-pkg")
You can bootstrap a pkg to the primary repo as follows:
```
jarvis repo create [name] [pkg_class]  

```

`pkg_class` can be one of:
  * service
  * app
  * interceptor


For example:
```
jarvis repo create hermes service  
jarvis repo create hermes_mpiio interceptor  
jarvis repo create gray_scott app  

```

We can then create an example pipeline as follows:
```
jarvis ppl create test  
jarvis ppl append hermes  
jarvis ppl append hermes_mpiio  
jarvis ppl append gray_scott  

```

This is an example of a pipeline which will deploy Hermes, the Hermes MPI-IO interceptor, and Gray Scott, which is an application which performs I/O using MPI.
## The `Pkg` Base Class[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#the-pkg-base-class "Direct link to the-pkg-base-class")
This section will go over the variables and methods common across all Pkg types. These variables will be initialized automatically.
```
class Pkg:  
  def __init__(self):  
    self.pkg_dir = '...'  
    self.shared_dir = '...'  
    self.private_dir = '...'  
    self.env = {}  
    self.mod_env = {}  
    self.config = {}  
    self.global_id = '...'  
    self.pkg_id = '...'  

```

###  `pkg_id` and `global_id`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#pkg_id-and-global_id "Direct link to pkg_id-and-global_id")
The Global ID (global_id) is the globally unique ID of the a package in all of jarvis. It is a dot-separated string. Typically, the format is:
```
{pipeline_id}.{pkg_id}  

```

The Package ID (pkg_id) is the unique ID of the package relative to a pipeline. This is a simple string (no dots).
For example, from section 5.1, we appended 3 packages: hermes, hermes_mpiio, and gray_scott. hermes, hermes_mpiio, and gray_scott are also the pkg_ids. The global_ids would be:
```
test.hermes  
test.hermes_mpiio  
test.gray_scott  

```

Usage:
```
self.global_id  
self.pkg_id  

```

###  `pkg_dir`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#pkg_dir "Direct link to pkg_dir")
The package directory is the location of the class python file on the filesystem. For example, when calling `jarvis repo create hermes`, the directory created by this command will be the pkg_dir.
One use case for the pkg_dir is for creating template configuration files. For example, OrangeFS has a complex XML configuration which would be a pain to repeat in Python. One could include an OrangeFS XML config in their package directory and commit as part of their Jarvis repo.
Usage:
```
self.pkg_dir  

```

###  `shared_dir`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#shared_dir "Direct link to shared_dir")
The shared_dir is a directory stored on a filesystem common across all nodes in the hostfile. Each node has the same view of data in the shared_dir. The shared_dir contains data for the specific pkg to avoid conflicts in a pipeline with multiple pkgs.
For example, when deploying Hermes, we assume that each node has the Hermes configuration file. Each node is expected to have the same configuration file. We store the Hermes config in the shared_dir.
Usage:
```
self.shared_dir  

```

###  `private_dir`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#private_dir "Direct link to private_dir")
This is a directory which is common across all nodes, but nodes do not have the same view of data.
For example, when deploying OrangeFS, it is required that each node has a file called pvfs2tab. It essentially stores the protocol + address that OrangeFS uses for networking. However, the content of this file is different for each node. Storing it in the shared_dir would be incorrect. This is why we need the private_dir.
Usage:
```
self.private_dir  

```

###  `env`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#env "Direct link to env")
Jarvis pipelines store the current environment in a YAML file, which represents a python dictionary. The key is the environment variable name (string) and the value is the intended meaning of the variable. There is a single environment used for the entire pipeline. Each pipeline stores its own environment to avoid conflict.
Usage:
```
self.env['VAR_NAME']  

```

Environments can be modified using various helper functions:
```
self.track_env(env_track_dict)  
self.prepend_env(env_name, val)  
self.setenv(env_name, val)  

```

Viewing the env YAML file for the current pipeline from the CLI
```
cat `jarvis path`/env.yaml  

```

###  `mod_env`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#mod_env "Direct link to mod_env")
a python dictionary. Essentially a copy of `env`. However, `mod_env` also stores the LD_PRELOAD environment variable for interception. This can cause conflict if used irresponsibly. Not every program should be intercepted.
For example, we use this for Hermes to intercept POSIX I/O. However, POSIX is widely-used for I/O so we like to be very specific when it is used.
`mod_env` can be modified using the same functions as `env`.
```
self.track_env(env_track_dict)  
self.prepend_env(env_name, val)  
self.setenv(env_name, val)  

```

###  `config`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#config "Direct link to config")
The Jarvis configuration is stored in `{pkg_dir}/{pkg_id}.yaml`. Unlike the environment dict, this stores variables that are specific to the package. They are not global to the pipeline.
For example, OrangeFS and Hermes need to know the desired port number and RPC protocol. This information is specific to the program, not the entire pipeline.
Usage:
```
self.config['VAR_NAME']  

```

###  `jarvis`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#jarvis "Direct link to jarvis")
The Jarvis CD configuration manager stores various properties global to all of Jarvis. The most important information is the hostfile and resource_graph, discussed in the next sections.
Usage:
```
self.jarvis  

```

###  `hostfile`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#hostfile "Direct link to hostfile")
The hostfile contains the set of all hosts that Jarvis has access to. The hostfile format is documented [here](https://github.com/scs-lab/jarvis-util/wiki/4.-Hostfile).
Usage:
```
self.jarvis.hostfile  

```

###  `resource_graph`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#resource_graph "Direct link to resource_graph")
The resource graph can be queried to get storage and networking information for storing large volumes of data.
```
self.jarvis.resource_graph  

```

## Building a Service or Application[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#building-a-service-or-application "Direct link to Building a Service or Application")
Services and Applications implement the same interface, but are logically slightly different. A service is long-running and would typically require the users to manually stop it. Applications stop automatically when it finishes doing what it's doing. Jarvis can deploy services alongside applications to avoid the manual stop when benchmarking.
###  `_init`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#_init "Direct link to _init")
The Jarvis constructor (`_init`) is used to initialize global variables. Don't assume that self.config is initialized. This is to provide an overview of the parameters of this class. Default values should almost always be None.
```
def _init(self):  
  self.gray_scott_path = None  

```

###  `_configure_menu`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#_configure_menu "Direct link to _configure_menu")
The function defines the set of command line options that the user can set. An example configure menu is below:
```
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
            'type': int,  
            'default': 8080  
        }  
    ]  

```

This function is called whenever configuring a package. For example,
```
jarvis pkg configure hermes --sleep=10 --port=25  

```

This will configure hermes to sleep for 10 seconds after launching to give enough time to fully start Hermes. Sleep is apart of all configure menus by default.
The format of the output dict is documented in more detail [here](https://github.com/scs-lab/jarvis-util/wiki/3.-Argument-Parsing).
###  `configure`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#configure "Direct link to configure")
It takes as input a dictionary. The keys of this dict are determined from _configure_menu function output. It is responsible for updating the self.config variable appropriately and generating the application-specific configuration files.
Below is an example for Hermes. This example takes as input the port option, modifies the hermes_server dict, and then stores the dict in a YAML file in the shared directory.
```
def configure(self, **kwargs):  
    """  
    Converts the Jarvis configuration to application-specific configuration.  
    E.g., OrangeFS produces an orangefs.xml file.  
  
    :param config: The human-readable jarvis YAML configuration for the  
    application.  
    :return: None  
    """  
    self.update_config(kwargs, rebuild=False)  
    hermes_server_conf = {  
      'port': self.config['port']  
    }  
    YamlFile(f'{self.shared_dir}/hermes_server_yaml').save(hermes_server_conf)  

```

This function is called whenever configuring a packge. Specifically, this is called immediately after _configure_menu. For example,
```
jarvis pkg configure hermes --sleep=10 --port=25  

```

will make the kwargs dict be:
```
{  
  'sleep': 10,  
  'port': 25  
}  

```

###  `start`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#start "Direct link to start")
The start function is called during `jarvis ppl run` and `jarvis ppl start`. This function should execute the program itself.
Below is an example for Hermes:
```
def start(self):  
    """  
    Launch an application. E.g., OrangeFS will launch the servers, clients,  
    and metadata services on all necessary pkgs.  
  
    :return: None  
    """  
    self.daemon_pkg = Exec('hermes_daemon',  
                            PsshExecInfo(hostfile=self.jarvis.hostfile,  
                                         env=self.env,  
                                         exec_async=True))  
    time.sleep(self.config['sleep'])  
    print('Done sleeping')  

```

###  `stop`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#stop "Direct link to stop")
The stop function is called during `jarvis ppl run` and `jarvis ppl stop`. This function should terminate the program.
Below is an example for Hermes:
```
def stop(self):  
    """  
    Stop a running application. E.g., OrangeFS will terminate the servers,  
    clients, and metadata services.  
  
    :return: None  
    """  
    Exec('finalize_hermes',  
         PsshExecInfo(hostfile=self.jarvis.hostfile,  
                      env=self.env))  
    if self.daemon_pkg is not None:  
        self.daemon_pkg.wait()  
    Kill('hermes_daemon',  
         PsshExecInfo(hostfile=self.jarvis.hostfile,  
                      env=self.env))  

```

This is not typically implemented for Applications, but it is for Services.
###  `kill`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#kill "Direct link to kill")
This function is called during `jarvis ppl kill`. It should forcibly terminate a program, typically using Kill.
Below is an example for Hermes
```
def kill(self):  
    """  
    Forcibly a running application. E.g., OrangeFS will terminate the  
    servers, clients, and metadata services.  
  
    :return: None  
    """  
    Kill('hermes_daemon',  
         PsshExecInfo(hostfile=self.jarvis.hostfile,  
                      env=self.env))  

```

###  `clean`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#clean "Direct link to clean")
The `clean` function is called during `jarvis ppl clean`. It clears all intermediate data produced by a pipeline.
Below is the prototype
```
def clean(self):  
    """  
    Destroy all data for an application. E.g., OrangeFS will delete all  
    metadata and data directories in addition to the orangefs.xml file.  
  
    :return: None  
    """  
    pass  

```

###  `status`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#status "Direct link to status")
The `status` function is called during `jarvis ppl status` It determines whether or not a service is running. This is not typically implemented for Applications, but it is for Services.
## Building an Interceptor[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#building-an-interceptor "Direct link to Building an Interceptor")
Interceptors are used to modify environment variables to route system and library calls to new functions.
Interceptors have a slightly different interface -- they only have: `_init`, `_configure_menu`, `configure`, and `modify_env`. The only new function here is modify_env. The others were defined in the previous section and behave the exact same way.
###  `configure`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#configure-1 "Direct link to configure-1")
Configuring an interceptor tends to be a little different. The interceptors are not typically responsible for generating configuration files like the applications and services do. These typically are responsible solely for modifying the environment.
Below, we show an example of configure for the Hermes MPI I/O interceptor:
```
def configure(self, **kwargs):  
    """  
    Converts the Jarvis configuration to application-specific configuration.  
    E.g., OrangeFS produces an orangefs.xml file.  
  
    :param kwargs: Configuration parameters for this pkg.  
    :return: None  
    """  
    self.update_config(kwargs, rebuild=False)  
    self.config['HERMES_MPIIO'] = self.find_library('hermes_mpiio')  
    if self.config['HERMES_MPIIO'] is None:  
        raise Exception('Could not find hermes_mpiio')  
    print(f'Found libhermes_mpiio.so at {self.config["HERMES_MPIIO"]}')  

```

Here we use self.find_library() to check if we can find the shared library hermes_mpiio in the system paths. This function introspects LD_LIBRARY_PATH and determines if hermes_mpiio is in the path. It saves the path in the pkg configuration (self.config).
###  `modify_env`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#modify_env "Direct link to modify_env")
Below is an example of the MPI I/O interceptor for Hermes:
```
def modify_env(self):  
    """  
    Modify the jarvis environment.  
  
    :return: None  
    """  
    self.prepend_env('LD_PRELOAD', self.config['HERMES_MPIIO'])  

```

## A Note on `jarvis-util`[​](https://grc.iit.edu/docs/jarvis/jarvis-cd/building-package/#a-note-on-jarvis-util "Direct link to a-note-on-jarvis-util")
`jarvis-cd` aims to provide structure to storing configuration files for simplifying complex benchmarks.
`jarvis-util` is primarily responsible for handling program execution. This includes things like executing MPI and PSSH in Python. This is where the `Exec` and `PsshExecInfo` data structures come from. More information on `jarvis-util` can be found [here](https://github.com/scs-lab/jarvis-util/wiki).
[Previous Custom Repos](https://grc.iit.edu/docs/jarvis/jarvis-cd/custom-repos)[Next Python API](https://grc.iit.edu/docs/jarvis/jarvis-cd/python-api)
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
