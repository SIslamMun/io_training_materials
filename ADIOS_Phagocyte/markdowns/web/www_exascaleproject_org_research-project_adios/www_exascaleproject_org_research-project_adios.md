  * [![ECP](https://www.exascaleproject.org/wp-content/themes/exascale/images/ecp-logo.png)](https://www.exascaleproject.org)


  * [Home](https://www.exascaleproject.org/ "Home")
  * [About ](javascript:void\(0\) "About")
    * [Contact](https://www.exascaleproject.org/contact/ "Contact")
    * [Overview](https://www.exascaleproject.org/about/ "Overview")
    * [Leadership](https://www.exascaleproject.org/contact-us/ "Leadership")
    * [Industry and Agency Council](https://www.exascaleproject.org/industry-and-agency-council/ "Industry and Agency Council")
    * [Broadening Participation Initiative](https://www.exascaleproject.org/hpc-workforce/ "Broadening Participation Initiative")
    * [Laboratory Partners](https://www.exascaleproject.org/collaborators/ "Laboratory Partners")
    * [Fact Sheet](https://www.exascaleproject.org/wp-content/uploads/2024/06/ECP-Impacts-Brochure-2024v4-final-forPrint.pdf "Fact Sheet")
  * [Research ](javascript:void\(0\) "Research")
    * [Overview](https://www.exascaleproject.org/research/ "Overview")
    * [Applications](http://www.exascaleproject.org/research/#application "Applications")
    * [Software](http://www.exascaleproject.org/research/#software "Software")
    * [Hardware & Integration](http://www.exascaleproject.org/research/#hardware "Hardware & Integration")
    * [Reports](https://www.exascaleproject.org/reports/ "Reports")
  * [News ](javascript:void\(0\) "News")
    * [News Highlights](https://www.exascaleproject.org/news-highlights/ "News Highlights")
    * [News Archive](https://www.exascaleproject.org/news-and-content/ "News Archive")
  * [Library](https://www.exascaleproject.org/library/ "Library")


# ADIOS
[ Data and Visualization ](https://www.exascaleproject.org/research-group/data-and-visualization/)
Exascale architectures will have complex, heterogeneous memory hierarchies—ranging from node-level caches and main memory to persistent storage via the file system—that applications need to effectively achieve their science goals. At the same time, exascale applications are becoming more complex in their data flows, from multiscale and multiphysics simulations that must exchange data between separate codes to simulations that invoke data analysis and visualization services to extract information and render it to storing simulation output to the file system for later analysis. The Adaptable I/O Systems (ADIOS) project delivers a highly optimized coupling infrastructure that enables efficient synchronous and asynchronous data exchanges to move data between multiple codes running concurrently and to the different layers of the storage system.
## Summary
### The Motivation
The Adaptable I/O System (ADIOS) in the Exascale Computing Project (ECP)’s Data and Visualization portfolio, addresses data management and in situ analysis concerns for industrial, academic, and exascale applications. The ADIOS team successfully optimized I/O on exascale architectures according to modern software practices, which means the software is scalable, maintainable, sustainable, and extensible while ensuring performance.
The developers describe ADIOS as [ a framework that puts computation in the proper place at the proper time in a data-rich environment](https://www.exascaleproject.org/adios-providing-a-framework-for-scientific-data-on-exascale-systems/). The framework was designed to enable scientists and engineers to describe their data and how they would like to use it without being distracted by details of the underlying storage technology and file formats.
### The Solution
To provide a very simple way to realize extreme-performance I/O, the project focused on transforming the existing ADIOS 1.x software (which has been used successfully on petascale resources), into a community framework that can efficiently utilize exascale hardware. This effort required refactoring to create a generalized software ecosystem (rather than [a point solution](https://www.mendix.com/glossary/point-solution/)) that can be customized and shared among a variety of users, exascale applications, and hardware technologies. Software modularity, flexibility, and extensibility were all achieved by using C++ and extending, tuning, and hardening the core services such as I/O and staging to support applications, architectures, and technologies up to and including exascale systems. The result is a sustainable, maintainable, and more approachable all-scale framework that can be used by a wide community of users and developers.
### The Impact
The ECP team adopted a project approach that focused on doing deep dives of software needs with scientists, end users, and developers to ensure that the software development process led to specific, verifiable results that positively impact their customers. This approach meant working directly with select US Department of Energy (DOE) and other ECP application developers to understand their requirements for scalable and high-performance I/O, staging, or [code coupling solutions](https://en.wikipedia.org/wiki/Coupling_\(computer_programming\)#:~:text=In%20software%20engineering%2C%20coupling%20is,of%20the%20relationships%20between%20modules.) to avoid any I/O bottlenecks in their production runs. Notable projects include the following:
  * [GEM](http://www.gemgyrokinetic.org/): a kinetic code used to model the central core plasma in a tokamak reactor
  * X-point Gyrokinetic Code ([XGC](https://theory.pppl.gov/research/research.php?rid=10)): a code used to model the edge of the plasma in a tokamak that includes some of the more complex features of the magnetic field
  * [WarpX](https://ecp-warpx.github.io/): an exascale application for plasma accelerators that enables the exploration of outstanding questions in the physics of the transport and the acceleration of particle beams in long chains of plasma channels
  * Particle-In-Cell Scalable Application Resource ([PICSAR](https://github.com/ECP-WarpX/picsar)): a high-performance repository intended to help scientists with porting their particle-in-cell codes to the next generation of exascale computers
  * Energy Exascale Earth System Model ([E3SM](https://e3sm.org/)): a cloud-resolving earth system model with the throughput necessary for multidecade, coupled high-resolution climate simulations


### Sustainability
The challenge of supporting hardware portability and runtime performance tuning was addressed by paying special attention to the architecture of the ADIOS code base and adopting state-of-the-art software engineering methodologies to make it easier for the DOE community to use, maintain, and extend the ADIOS framework. The new code base is governed with state-of-the-art software development practices, including a [GitHub workflow of pull requests](https://blog.mergify.com/understanding-the-github-pull-request-workflow/) with reviews, continuous integration that enforces well-tested changes to the code only, and nightly builds to efficiently catch errors on various combinations of architectures and software stacks.
## Technical Discussion
ADIOS is designed to tackle data management challenges posed by large-scale science applications that run on high-performance computers and require, for example, code-to-code coupling for multiphysics and multiscale applications and code-to-service coupling for data analysis and visualization. Notably, ADIOS provides a simple, declarative publish/subscribe I/O interface so that applications can easily describe the data that they produce or consume. ADIOS has multiple optimized solutions to transfer data between codes and to the file system.
The ADIOS team is focused on providing high-quality performant software products to address the data flow requirement of exascale applications on pre-exascale and exascale architectures. Therefore, the team is optimizing and creating new ADIOS microservices to efficiently perform the data transfers needed by applications that can use pre-exascale and exascale architecture features so that the exascale applications can meet their science and performance goals. The framework that the team delivers supports synchronous and asynchronous data exchanges and provides the capabilities necessary for in situ processing and code coupling and efficient data transfers to the file system.
### For More Information and References
  * ADIOS can be installed by using Extreme-Scale Scientific Software Stack binaries or containers or by using custom source code builds via Spack: <https://e4s.io/>.
  * ADIOS is open source and available at <https://github.com/ornladios/ADIOS2/>.
  * The ECP podcast episode “[ADIOS: Providing A Framework for Scientific Data on Exascale Systems](https://www.exascaleproject.org/adios-providing-a-framework-for-scientific-data-on-exascale-systems/)” provides more information about the ADIOS project.


## Principal Investigator(s) 
Scott Klasky, Oak Ridge National Laboratory
## Collaborators 
Oak Ridge National Laboratory, Lawrence Berkeley National Laboratory, Georgia Institute of Technology, Rutgers University, Kitware Inc.
The Exascale Computing Project (ECP) operated between 2016 and 2024 and was responsible for delivering a capable exascale computing ecosystem, including software, applications, and hardware technology, to support the Nation’s exascale computing imperative. The ECP was a joint project (17-SC-20-SC) of the U.S. Department of Energy’s Office of Science and National Nuclear Security Administration.
[![National Nuclear Security Administration logo](https://www.exascaleproject.org/wp-content/themes/exascale/images/nisa-logo.png)](https://nnsa.energy.gov) [![Exascale Computing Project logo small](https://www.exascaleproject.org/wp-content/themes/exascale/images/ecp-logo-black.png)](https://www.exascaleproject.org) [![U.S. Department of Energy Office of Science logo](https://www.exascaleproject.org/wp-content/themes/exascale/images/doe-logo.png)](http://science.energy.gov)
