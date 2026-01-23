![Adaptable IO System Delivers the Data](https://www.olcf.ornl.gov/wp-content/uploads/ADIOS-banner.v2-scaled.jpg)
# Adaptable IO System Delivers the Data
By [Coury Turczyn](https://www.olcf.ornl.gov/author/turczyncz/ "Posts by Coury Turczyn")April 29, 2024July 17th, 2024[Technology](https://www.olcf.ornl.gov/category/technology/)11 min read
### From its roots as a faster input/output solution, ADIOS has evolved into an essential data-management tool for HPC simulations
Amid the challenges that the Department of Energy’s Oak Ridge Leadership Computing Facility faced in [assembling and launching](https://www.olcf.ornl.gov/2024/01/04/watch-the-journey-to-frontier-mini-doc/) the world’s first exascale-class (more than a quintillion calculations per second) supercomputer, Frontier, one key component was hitch-free.
Integral to Frontier’s functionality is its ability to store the vast amounts of data it produces onto its file system, [Orion](https://www.olcf.ornl.gov/2023/01/17/forging-a-file-system/). But even more important to the computational scientists running simulations on Frontier is their capability to quickly write and read to Orion along with effectively analyzing all that data. And that’s where the Adaptable IO System, or ADIOS, comes in.
At its core, ADIOS is an input/output, or I/O, framework that provides a simple and flexible way for scientists to describe the data in their code that may need to be written, read or processed while running a simulation. This makes it considerably easier for researchers to analyze the huge volumes of data they produce on Frontier. Since its initial development in 2008 at DOE’s Oak Ridge National Laboratory, the [open-source ADIOS](https://github.com/ornladios) framework has become an essential tool for high-performance computing, or HPC, simulations around the world with an ever-evolving array of features and users.
“ADIOS always delivers,” said Bronson Messer, OLCF’s director of science. “With Frontier, we switched to a new parallel file system, and ADIOS ensured that things just kept plugging along. ADIOS just works without issues on high-performance computers, so major infrastructure changes like a new file system don’t impact our leadership projects.”
At leadership computing facilities such as the OLCF, a DOE Office of Science user facility located at ORNL, ADIOS helps computational scientists parse the large volumes of data their projects produce, even before they’re completely written, allowing the scientists to get an early understanding of their results even as they’re still running their simulations.
“A simulation produces all this data, but that doesn’t mean everything has to get written,” said Scott Klasky, who heads ADIOS development and leads the Workflow Systems group in ORNL’s Computer Science and Mathematics Division.
“If you want to get some pieces, then you can get it — you can get it to storage or you can just get it from memory and then process it. That’s the beauty of ADIOS — it allows for those modalities. It was the first technology that allowed scientists to work in a unified way with data in motion and data at rest, and it’s still the fastest technology even today.”
### ADIOS’s evolution
Klasky first started thinking about the need for middleware like ADIOS as a doctoral student in physics at the University of Texas at Austin working on a code for simulating black holes, and then later as an R&D scientist at the Princeton Plasma Physics Laboratory using the Gyrokinetic Toroidal Code for understanding turbulent transport in a fusion reactor.
“I was trying to do a simple thing using the most state-of-the-art, self-describing, parallel I/O system out there at the time: write out a terabyte of data in one day,” Klasky said. “A terabyte now sounds like nothing to some people — but in 1999, we were running across a thousand processors on the IBM RS/6000 SP supercomputer at the National Energy Research Scientific Computing Center. In order to do that with the state of the art, 50% of the compute time was spent in I/O.”
It wasn’t until after Klasky arrived at ORNL in 2005 that he began earnestly pursuing what would become ADIOS. He assembled a team to develop the framework while also enlisting researchers from Georgia Tech and Rutgers University, among other institutions. The project got a big boost from computer scientist Norbert Podhorszki, who was hired at ORNL in 2008 and started working on ADIOS 1.0, which aimed to increase I/O speed tenfold for the largest applications running on the OLCF’s Jaguar supercomputer.
“Long before ADIOS, there was always a need to have self-describing data to make life easier for computational scientists,” Podhorszki said. “They didn’t deliver performance, however, because their bottlenecks in design caused a rapid decline in overall throughput when scaling the application up to thousands of processes.
“Everyone who was working in HPC, especially here at Oak Ridge on these big computers, was forced to work with bytes, trying to forge their own homemade data solutions from the basics. You were producing the output and reading back the data in byte levels. It was very painful. So, we said, ‘Ah, maybe we can do better.’”
However, after 14 major releases by 2015, ADIOS’s patchwork of codes was becoming difficult to manage and needed a revamp. DOE’s Exascale Computing Project, or ECP — launched in 2016 to prepare software applications and technology for upcoming exascale systems like Frontier — arrived on the scene with funding to hire software engineers to develop a new ADIOS.
“ADIOS 2.0 was born in 2016 from scratch — zero lines from ADIOS 1.0,” Podhorszki said. “We went from the C to C++ 11 programming language, which completely changed the whole thing. Our main goals were twofold: first, redesign and reimplement the product for file system support for the incoming exascale computers, and second, make staging — now, after so many years of research — also production quality that can be used by applications daily.”
ADIOS 2.9, released at the end of the ECP project, allows the flagship applications of the Frontier supercomputer to produce and consume multiple terabytes of data per second using its Orion file system.
Architects of the Adaptable IO System, seen here with Frontier’s Orion file system: Scott Klasky, left, heads the ADIOS project and leads ORNL’s Workflow Systems group, and Norbert Podhorszki, an ORNL computer scientist, oversees ADIOS’s continuing development. Credit: Genevieve Martin/ORNL, U.S. Dept. of Energy
### ADIOS for science
ADIOS continues to make a lasting impact in computational science with its widespread adoption by the teams developing or using important simulation codes, such as the ECP-supported Exascale Atomistic Capability for Accuracy, Length, and Time, or EXAALTa molecular dynamics simulation software stack for identifying the best materials for constructing fission and fusion reactors.
Some codes using ADIOS include recent winners of one of the most prestigious awards in computing: the Association for Computing Machinery’s Gordon Bell Prize. In 2023, the Energy Exascale Earth System Model’s 19-member team from across the national laboratory complex [won the first ACM Gordon Bell Prize for Climate Modeling](https://www.olcf.ornl.gov/2023/11/16/cloud-simulations-on-frontier-awarded-gordon-bell-special-prize-for-climate-modeling/) with its Simple Cloud Resolving E3SM Atmosphere project. A year earlier, a 16-member team from Lawrence Berkeley National Laboratory, Lawrence Livermore National Laboratory and the French Alternative Energies and Atomic Energy Commission [won the main 2022 Gordon Bell Prize](https://www.olcf.ornl.gov/2022/11/17/plasma-simulation-code-wins-2022-acm-gordon-bell-prize/) for its kinetic-plasma simulation code, WarpX. Both of those winners also ran their projects on Frontier.
“What’s the point of a machine like Frontier — to compute faster?” Klasky said. “I would say that’s probably a bad answer. Anyone can compute, but it’s how the data from that computation is used for scientific discovery that really matters.
“If you can generate data very efficiently, or even process it in situ without slowing down the computation significantly, then we add much more value to these big machines. That’s why we partner closely with many application teams around the world. This is the essential ingredient of our success: deep partnerships.”
Many of these partnerships arise from DOE’s [Scientific Discovery through Advanced Computing](https://www.scidac.gov/), or SciDAC, program. It was created to bring together many of the nation’s top researchers to develop new computational methods for tackling some of the most challenging scientific problems. As part of DOE’s [Advanced Scientific Computing Research](https://www.energy.gov/science/ascr/advanced-scientific-computing-research), or ASCR, program, it connects with other DOE offices and institutes to provide funding for the development of cutting-edge scientific software.
**“** In addition to what’s being worked on here at ORNL, a lot of the applications we work with come from SciDAC,” Klasky said. “We work together through ASCR. Some of the fundamental research we conduct — like data reduction or querying — are ASCR research proposals. And as we discover things that work with certain apps, we then say, ‘Can we now get those things into ADIOS and then use them on even more apps?’”
### ADIOS for industry
ADIOS’s ability to enable researchers to write self-describing data — to and from storage, quickly at large scales — also holds great appeal for computational scientists at industrial companies that conduct simulations. Consequently, the ADIOS team has often helped companies speed up the I/O in their codes, such as German software company NUMECA’s FINE/Turbo computational fluid dynamics suite for turbomachinery or property insurer FM Global’s use of OpenFOAM for [warehouse fire modeling](https://www.olcf.ornl.gov/2016/08/16/fm-global-researchers-say-adios-to-bottlenecks-at-openfoam-conference/).
“Collaborating with industry on applications is one of the fun parts of this work,” Podhorszki said. “It forces us to put together all the stuff that we developed but never had the time to integrate into the whole thing because we’re always focusing on the research, which has different priorities. Here, the priority is to make it work smoothly. So, it’s very useful to have these contracts over the years and raise the quality of the entire software.”
General Electric Aviation’s ongoing research at the OLCF investigates turbulence and turbine designs using its homegrown Finite Element simulations. It got a huge speed boost with the help of Podhorszki and ADIOS. GE wanted to write 100 terabytes of data in a day, but the cost would have been too great without a considerably faster I/O. Podhorszki aimed for a 100 times speedup — and delivered 500 times.
“Now GE can write even more data than they ever expected,” Klasky said. “And they don’t have to change the application — they just use ADIOS to go further. And I think that’s its strength.”
### What’s next?
With over 1 exaflop of computing power, Frontier’s ability to churn out data is considerable — around 10 petabytes a day. But with that volume of data comes new data-management challenges.
“You may produce 10 petabytes of data on Frontier every day, but you can’t effectively process that much data, so the problem has changed for the future,” Podhorszki said. “Now we need to focus on the next problem: We have too much data. What do we do with it? How do we support processing and finding the science in it?”
Klasky has in mind a solution that’s comparable to how the thousands of photos you take using your smart phone are made browsable. Most of the photos are not actually stored on your phone — they wind up on a cloud service. But the photo app on your phone offers representations of those photos so you can see what they look like and select them for downloading or sharing.
“Can we provide that sort of experience with huge data? How do you work with some of the largest datasets now on, say, your laptop? On your cluster?” Klasky said. “I don’t think everyone has to have Frontier to just get a glimpse of what’s in their data. So that’s a big push of where we’ve been going — how do we do that?”
_UT-Battelle manages ORNL for DOE’s Office of Science, the single largest supporter of basic research in the physical sciences in the United States. DOE’s Office of Science is working to address some of the most pressing challenges of our time. For more information, visit[energy.gov/science](https://energy.gov/science)._
#### Tags:
[ADIOS](https://www.olcf.ornl.gov/tag/adios/)[Advanced Technologies](https://www.olcf.ornl.gov/tag/advanced-technologies/)[Computer Science](https://www.olcf.ornl.gov/tag/computer-science/)[data analysis](https://www.olcf.ornl.gov/tag/data-analysis/)[I/O](https://www.olcf.ornl.gov/tag/io/)[Orion](https://www.olcf.ornl.gov/tag/orion/)[Systems](https://www.olcf.ornl.gov/tag/systems/)
![Coury Turczyn](https://www.olcf.ornl.gov/wp-content/uploads/coury_turczyn_profile_picture_194-100x100.jpeg)
###  [Coury Turczyn](https://www.olcf.ornl.gov/author/turczyncz/)
Coury Turczyn writes communications content for the Oak Ridge Leadership Computing Facility (OLCF). He has worked in different communications fields over the years, though much of his career has been devoted to local journalism. In between his journalism stints, Coury worked as a web content editor for CNET.com, the G4 cable TV network, and HGTV.com.
### You May Also Like
[![Arx2 ORNL](https://www.olcf.ornl.gov/wp-content/uploads/2025-P27751-600x403.jpg)](https://www.olcf.ornl.gov/2025/12/18/arx2-storage-system-gets-a-powerful-upgrade/) [Featured](https://www.olcf.ornl.gov/category/featured/)[Technology](https://www.olcf.ornl.gov/category/technology/)
### Arx2 Storage System Gets a Powerful Upgrade
The Department of Energy’s Oak Ridge National Laboratory recently upgraded its Scalable Protected Infrastructure (SPI) for CITADEL — the framework of security protocols that protects sensitive data on systems at the Oak Ridge Leadership Computing Facility (OLCF) — by expanding the facility’s Arx2 file storage system. Arx2 was originally installed…
[![](https://www.olcf.ornl.gov/wp-content/uploads/2022-P00865-600x403.jpg)](https://www.olcf.ornl.gov/2025/12/09/hpc-course-showcased-at-usrse25-to-train-future-supercomputing-experts/) [Featured](https://www.olcf.ornl.gov/category/featured/)[Technology](https://www.olcf.ornl.gov/category/technology/)
### HPC Course Showcased at USRSE25 to Train Future Supercomputing Experts
A paper introducing a hands-on course that puts students at the helm of high-performance computing clusters was presented at the annual User and System Administrator Research Software Event (USRSE) earlier this fall, highlighting a growing need for practical skills to meet rising supercomputing demands. Fernando Posada, who leads the National…
[![](https://www.olcf.ornl.gov/wp-content/uploads/OLCF_QuantumManyBodyGB-600x403.png)](https://www.olcf.ornl.gov/2025/11/17/frontier-simulations-spin-up-new-details-for-quantum-understanding/) [Featured](https://www.olcf.ornl.gov/category/featured/)[Industry](https://www.olcf.ornl.gov/category/industry/)[Science](https://www.olcf.ornl.gov/category/science/)[Technology](https://www.olcf.ornl.gov/category/technology/)
### Frontier Simulations Spin Up New Details for Quantum Understanding
Researchers used the world’s fastest supercomputer for open science to uncover new insights that could pave the way for the next generation of quantum computing, sensing and communications technologies through more efficient control of quantum materials and their properties. The study conducted on the Frontier supercomputer at the Department of…
![](https://www.olcf.ornl.gov/wp-content/uploads/DOE_300.png)
Oak Ridge National Laboratory is managed by UT-Battelle for the US Department of Energy.
  * [DOE Office of Science](https://www.energy.gov/science/office-science/)
  * [ORNL.GOV](https://www.ornl.gov/)
  * [Battelle.org](https://www.ut-battelle.org/)


#### Contact Us
Oak Ridge Leadership Computing Facility  
One Bethel Valley Rd  
P.O. Box 2008 Oak Ridge, TN 37831
Support Email: help@olcf.ornl.gov
#### Quick Links
  * [MyOLCF](https://users.nccs.gov/)
  * [User Documentation](https://docs.olcf.ornl.gov/index.html)
  * [Resource Guides](https://docs.olcf.ornl.gov/systems/index.html)
  * [Documents & Forms](https://www.olcf.ornl.gov/for-users/documents-forms/)
  * [Accounts & Projects](https://docs.olcf.ornl.gov/accounts/index.html)
  * [Training Calendar](https://www.olcf.ornl.gov/calendar-category/training/)
  * [Contact & Support](https://docs.olcf.ornl.gov/support/index.html)
  * [Careers](https://www.olcf.ornl.gov/community/careers/)


#### Connect with OLCF
  * [](https://www.facebook.com/oakridgeleadershipcomputingfacility)
  * [](https://twitter.com/OLCFGOV)
  * [](https://www.linkedin.com/showcase/computing-at-ornl/)
  * [](https://vimeo.com/olcf)
  * [](https://www.instagram.com/olcfgov)
  * [](https://www.flickr.com/photos/olcf/)


© 2026 Oak Ridge Leadership Computing Facility. [Accessibility](https://www.ornl.gov/content/accessibility) | [Privacy](https://www.ornl.gov/ornl/contact-us/Security--Privacy-Notice) | [Feedback](https://www.olcf.ornl.gov/feedback)
[ ](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
[Oak Ridge National Laboratory](https://www.ornl.gov)
  * [About OLCF](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
    * [ Back ](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
    * [Overview](https://www.olcf.ornl.gov/about-olcf/overview/)
    * [Our History](https://www.olcf.ornl.gov/about-olcf/our-history/)
    * [Leadership Team](https://www.olcf.ornl.gov/about-olcf/leadership-team/)
    * [Staff Sections & Groups](https://www.olcf.ornl.gov/about-olcf/staff-sections/)
      * [ Back ](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
      * [Advanced Technologies](https://www.olcf.ornl.gov/about-olcf/staff-sections/advanced-technologies/)
      * [HPC Operations](https://www.olcf.ornl.gov/about-olcf/staff-sections/operations/)
      * [Science Engagement](https://www.olcf.ornl.gov/about-olcf/staff-sections/science-engagement/)
      * [HPC Systems](https://www.olcf.ornl.gov/about-olcf/staff-sections/systems/)
    * [Staff Directory](https://www.olcf.ornl.gov/directory/)
    * [Industry Partnership Program](https://www.olcf.ornl.gov/about-olcf/accel/)
    * [Exascale Computing Roundtable](https://www.olcf.ornl.gov/ecr/)
    * [Center Reports](https://www.olcf.ornl.gov/about-olcf/center-reports/)
    * [Media Assets](https://www.olcf.ornl.gov/about-olcf/media-assets/)
  * [OLCF Resources](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
    * [ Back ](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
    * [Compute Resources](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
      * [ Back ](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
      * [Introducing Discovery](https://www.olcf.ornl.gov/olcf-resources/compute-systems/discovery/)
      * [Frontier](https://www.olcf.ornl.gov/olcf-resources/compute-systems/frontier/)
      * [Summit](https://www.olcf.ornl.gov/olcf-resources/compute-systems/summit/)
      * [Andes](https://www.olcf.ornl.gov/olcf-resources/compute-systems/andes/)
      * [Quantum (QCUP)](https://www.olcf.ornl.gov/olcf-resources/compute-systems/quantum-computing-user-program/)
      * [Testbeds](https://www.olcf.ornl.gov/olcf-resources/compute-systems/wombat/)
    * [Data & Visualization Resources](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
      * [ Back ](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
      * [Visualization Gallery](https://www.olcf.ornl.gov/olcf-resources/data-visualization-resources/visualization-gallery/)
      * [Orion](https://www.olcf.ornl.gov/olcf-resources/data-visualization-resources/orion/)
      * [EVEREST](https://www.olcf.ornl.gov/olcf-resources/data-visualization-resources/everest/)
      * [HPSS](https://www.olcf.ornl.gov/olcf-resources/data-visualization-resources/hpss/)
      * [Constellation](https://doi.ccs.ornl.gov/)
  * [Science at OLCF](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
    * [ Back ](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
    * [Biology](https://www.olcf.ornl.gov/leadership-science/biology/)
    * [Chemistry](https://www.olcf.ornl.gov/leadership-science/chemistry/)
    * [Computer Science](https://www.olcf.ornl.gov/leadership-science/computer-science/)
    * [Earth Science](https://www.olcf.ornl.gov/leadership-science/earth-science/)
    * [Engineering](https://www.olcf.ornl.gov/leadership-science/engineering/)
    * [Fusion](https://www.olcf.ornl.gov/leadership-science/fusion/)
    * [Materials Science](https://www.olcf.ornl.gov/leadership-science/materials/)
    * [Nuclear Energy](https://www.olcf.ornl.gov/leadership-science/nuclear-energy/)
    * [Physics](https://www.olcf.ornl.gov/leadership-science/physics/)
    * [Quantum](https://www.olcf.ornl.gov/leadership-science/quantum/)
  * [Community](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
    * [ Back ](https://www.olcf.ornl.gov/2024/04/29/adaptable-io-system-delivers-the-data/)
    * [Careers](https://www.olcf.ornl.gov/community/careers/)
    * [Event Calendar](https://www.olcf.ornl.gov/event-calendar/)
    * [Pathways to Supercomputing](https://www.olcf.ornl.gov/community/pathways-to-supercomputing/)
    * [Monthly User Conference Calls](https://www.olcf.ornl.gov/community/monthly-user-conference-calls/)
    * [OLCF User Group](https://www.olcf.ornl.gov/community/oug/)
    * [Visiting & Tours](https://www.olcf.ornl.gov/community/visitor-information-tours/)
  * [News](https://www.olcf.ornl.gov/olcf-news/)
  * [User Support](https://docs.olcf.ornl.gov/)


  * [Event Calendar](https://www.olcf.ornl.gov/event-calendar/)
  * [Staff Directory](https://www.olcf.ornl.gov/directory/)
  * [MyOLCF](https://my.olcf.ornl.gov/login)
  * [Center Status](https://my.olcf.ornl.gov/login)


  * [](https://twitter.com/OLCFGOV)
  * [](https://www.facebook.com/oakridgeleadershipcomputingfacility)
  * [](https://www.linkedin.com/showcase/computing-at-ornl)
  * [](https://www.instagram.com/olcfgov)


