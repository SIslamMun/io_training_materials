[Skip to main content](https://www.osti.gov/biblio/3002190#main-body)
[](https://www.osti.gov/biblio/3002190) [](https://www.osti.gov/biblio/3002190)
[OSTI.GOV U.S. Department of Energy Office of Scientific and Technical Information](https://www.osti.gov/)
U.S. Department of Energy  
Office of Scientific and Technical Information 
[ Research Results](https://www.osti.gov/submit-sti) [ Tools](https://www.osti.gov/search-tools) [Public Access Policy](https://www.osti.gov/public-access) [s Services & Dev Tools](https://www.osti.gov/persistent-identifier-services-developer-tools) [](https://www.osti.gov/about) [](https://www.osti.gov/faqs) [](https://www.osti.gov/news) [](https://www.osti.gov/login) [Create Account](https://www.osti.gov/createaccount)
[OSTI.GOV](https://www.osti.gov/) Conference: _Streaming Data in HPC Workflows Using ADIOS_
# Streaming Data in HPC Workflows Using ADIOS
Conference · 01 August 2025
DOI:<https://doi.org/10.1145/3725789.3725793>· OSTI ID:3002190 
Podhorszki, Norbert [](https://orcid.org/0000-0001-9647-542X "https://orcid.org/0000-0001-9647-542X")[ ](https://orcid.org/0000-0001-9647-542X "https://orcid.org/0000-0001-9647-542X") [1];  [Eisenhauer, Greg [2]](https://www.osti.gov/search/author:"Eisenhauer,%20Greg");  [Gainaru, Ana [1]](https://www.osti.gov/search/author:"Gainaru,%20Ana");  Klasky, Scott [](https://orcid.org/0000-0003-3559-5772 "https://orcid.org/0000-0003-3559-5772")[ ](https://orcid.org/0000-0003-3559-5772 "https://orcid.org/0000-0003-3559-5772") [1];  Suchyta, Eric [](https://orcid.org/0000-0002-7047-9358 "https://orcid.org/0000-0002-7047-9358")[ ](https://orcid.org/0000-0002-7047-9358 "https://orcid.org/0000-0002-7047-9358") [1]
* * *
  1. ORNL
  2. Georgia Institute of Technology, Atlanta


[ + Show Author Affiliations](https://www.osti.gov/biblio/3002190)
The “IO Wall” problem, in which the gap between computation rate and data access rate grows continuously, poses significant problems to scientific workflows which have traditionally relied upon using the filesystem for intermediate storage between workflow stages. One way to avoid this problem in scientific workflows is to stream data directly from producers to consumers and avoiding storage entirely. However, the manner in which this is accomplished is key to both performance and usability. This paper presents the Sustainable Staging Transport, an approach which allows direct streaming between traditional file writers and readers with few application changes. SST is an ADIOS “engine”, accessible via standard ADIOS APIs, and because ADIOS allows engines to be chosen at run-time, many existing file-oriented ADIOS workflows can utilize SST for direct application-to-application communication without any source code changes. This paper describes the design of SST and presents performance results from various applications that use SST, for feeding model training with simulation data with substantially higher bandwidth than the theoretical limits of Frontier’s file system, for strong coupling of separately developed applications for multiphysics multiscale simulation, or for in situ analysis and visualization of data to complete all data processing shortly after the simulation finishes.  

Research Organization:
    Oak Ridge National Laboratory (ORNL), Oak Ridge, TN (United States) 

Sponsoring Organization:
    USDOE 

DOE Contract Number:
    AC05-00OR22725 

OSTI ID:
    3002190 

Country of Publication:
    United States 

Language:
    English
* * *
## Similar Records
[Transitioning from File-Based HPC Workflows to Streaming Data Pipelines with openPMD and ADIOS2](https://www.osti.gov/biblio/1860584)
Conference · 2022 · OSTI ID:1860584 
* * *
[Accelerating Scientific Workflows on HPC Platforms with In Situ Processing](https://www.osti.gov/biblio/1888792)
Conference · 2021 · OSTI ID:1888792 
* * *
[...And Eat it Too: High Read Performance in Write-Optimized HPC I/O Middleware File Formats](https://www.osti.gov/biblio/982187)
Conference · 2008 · OSTI ID:982187 
## Related Subjects
* * *
![Footer logo](https://www.osti.gov/assets/img/src/DOE_SC_OSTI_2025_Horizonal-IndustrialGray.svg)
  * [/ Important Links](https://www.osti.gov/disclaim)
  * [](https://www.osti.gov/contact)
  * [Vulnerability Disclosure Program](https://www.energy.gov/vulnerability-disclosure-policy)
  * [](https://www.facebook.com/ostigov)
  * [](https://twitter.com/OSTIgov)
  * [](https://www.youtube.com/user/ostigov)


