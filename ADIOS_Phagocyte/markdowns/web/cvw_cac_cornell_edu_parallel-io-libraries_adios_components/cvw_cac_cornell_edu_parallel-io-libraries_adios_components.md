[![Cornell University](https://cvw.cac.cornell.edu/icons/cornell-reduced-red.svg)](https://cvw.cac.cornell.edu/parallel-io-libraries/adios/components)
Cornell Virtual Workshop 
|  | [×](javascript:void\(0\) "Clear search box")  
---|---  
search |   
Custom Search
|  Sort by: Relevance Relevance Date  
---|---  
Cornell Virtual Workshop 
  * [Home](https://cvw.cac.cornell.edu/index)
  * [Topics](https://cvw.cac.cornell.edu/topics)
  * [Roadmaps](https://cvw.cac.cornell.edu/roadmaps)
  * [Notebook](https://cvw.cac.cornell.edu/notebook)
  * [Glossary](https://cvw.cac.cornell.edu/glossary)
  * [Contact](https://cvw.cac.cornell.edu/contact)
  * [Login](https://cvw.cac.cornell.edu/oauth2/index.php?from=parallel-io-libraries/adios/components)


###### [**Parallel I/O Libraries**](https://cvw.cac.cornell.edu/parallel-io-libraries)
[Structured Data](https://cvw.cac.cornell.edu/parallel-io-libraries/structured-data/index)
[PnetCDF](https://cvw.cac.cornell.edu/parallel-io-libraries/pnetcdf/index)
[PHDF5](https://cvw.cac.cornell.edu/parallel-io-libraries/phdf5/index)
[**ADIOS**](https://cvw.cac.cornell.edu/parallel-io-libraries/adios/index)
  * [Basic Design of ADIOS](https://cvw.cac.cornell.edu/parallel-io-libraries/adios/design)
  * [ADIOS Components](https://cvw.cac.cornell.edu/parallel-io-libraries/adios/components)


### ADIOS Components
[Parallel I/O Libraries](https://cvw.cac.cornell.edu/parallel-io-libraries) > [ADIOS](https://cvw.cac.cornell.edu/parallel-io-libraries/adios/index) > [ADIOS Components](https://cvw.cac.cornell.edu/parallel-io-libraries/adios/components)
The following figure illustrates the different kinds of low-level API components present in ADIOS2. The top-level ADIOS component is the only one "owned" by the application. Since ADIOS uses a factory pattern, all other components, such as IO, variables, and operators, refer to elements inside an ADIOS factory container. These subsidiary elements can interact with system resources through one of the available "engines", such as HDF5 or the native engine based on BP3/BP4. 
![Detailed ADIOS 2 architecture, as described and explained in the main text](https://cvw.cac.cornell.edu/parallel-io-libraries/adios/adios2-2.jpg) Detailed ADIOS architecture. Image source: [Godoy et. al.](https://doi.org/10.1016/j.softx.2020.100561)
The above figures are taken from the [open access paper](https://creativecommons.org/licenses/by/4.0/) by Godoy, Podhorszki, et al., "[ADIOS 2: The Adaptable Input Output System. A framework for high-performance data management](https://doi.org/10.1016/j.softx.2020.100561)", which explains the philosophy of the system. 
######  To learn more about this evolving project: 
  * Detailed information about the kinds of applications making use of ADIOS2 may be found in the presentation "[ADIOS: Storage and in situ I/O](https://www.exascaleproject.org/event/adios/)" from the Exascale Computing Project All-Hands Meeting, 2021 (online). 
  * [Full documentation](https://adios2.readthedocs.io/en/latest/introduction/introduction.html) is available at Read the Docs.
  * [ADIOS2 source code](https://github.com/ornladios/ADIOS2) can be obtained from GitHub.


[Back](https://cvw.cac.cornell.edu/parallel-io-libraries/adios/design)
© [Cornell University](https://www.cornell.edu) | [Center for Advanced Computing](https://www.cac.cornell.edu/) | [Copyright Statement](https://www.cac.cornell.edu/copyright.aspx) | [Access Statement](https://cvw.cac.cornell.edu/AccessStatement)   
CVW material development is supported by NSF OAC awards 1854828, 2321040, 2323116 (UT Austin) and 2005506 (Indiana University) 
|   
---|---
