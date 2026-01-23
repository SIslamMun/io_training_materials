  * [ ](https://www.kitware.com/)
  * [ News ](https://www.kitware.com/in-situ-in-transit-hybrid-analysis-using-catalyst-adios2-and-paraview/)
  * [ Blog ](https://www.kitware.com/blog)
  * [ post ](https://www.kitware.com/in-situ-in-transit-hybrid-analysis-using-catalyst-adios2-and-paraview/)


# In Situ – In Transit Hybrid Analysis using Catalyst-ADIOS2 and ParaView
[Louis Gombert](https://www.kitware.com/author/louis-gombert/ "Posts by Louis Gombert"), [Lucas Givord](https://www.kitware.com/author/lucas-givord/ "Posts by Lucas Givord"), [Francois Mazen](https://www.kitware.com/author/francois-mazen/ "Posts by Francois Mazen"), [Charles Gueunet](https://www.kitware.com/author/charles-gueunet/ "Posts by Charles Gueunet") and [Sonia Ayme](https://www.kitware.com/author/sonia-ayme/ "Posts by Sonia Ayme")
![](https://www.kitware.com/main/wp-content/uploads/2024/08/slice7.gif)
Last year, [we introduced Catalyst-ADIOS2](https://www.kitware.com/catalyst-adios2-a-new-catalyst2-implementation-for-in-transit-analysis/), a new Catalyst implementation capable to process simulation data on the fly on a dedicated visualization cluster. If you haven’t read it already, we suggest reading that initial blog post before diving into this one. Catalyst-ADIOS2 enables new in situ workflows (named “**in transit** ”) that process simulation outputs without blocking the simulation itself. However, industrial usage of this technology has raised questions of scalability of data transfer between the simulation and visualization clusters: when the simulation output data is too large, it takes longer to send it to the visualization cluster than to process it directly! This blog post introduces an**in situ** – **in transit** hybrid approach addressing this concern using a new step of reduction before dataset transfer between clusters. Let’s dive in together!
## Catalyst2: In situ workflows
To understand the motivation behind our hybrid approach, let’s go back to where it all started. **In situ** visualization comes from the idea of generating visualizations (“extracts”) from a long-running simulation after each time step has been computed, instead of waiting for the whole simulation to finish. This early feedback can be valuable for research scientists in a HPC context to analyze early results and ensure that the simulation is running as intended.
Recently, [Catalyst 2.0.0 has been released](https://www.kitware.com/catalyst-2-0-0-release/). It provides a stable ABI to give simulations with in situ capabilities with only small code changes. Catalyst 2 uses the [Conduit blueprint](https://llnl-conduit.readthedocs.io/en/latest/blueprint_mesh.html) mesh protocol that defines the data structure to be sent to the Catalyst 2 implementation. One notable Catalyst 2 implementation is Catalyst-ParaView, which de-serializes Conduit meshes to VTK data structures and applies post-processing filters, executed in parallel, to generate extracted images or data files, using all the capabilities of ParaView’s Python API. This in situ processing happens synchronously on the simulation nodes after the simulation time step has finished and will be referred to as **in line** in the following. 
![](https://www.kitware.com/main/wp-content/uploads/2024/08/InSitu-1.svg)[fig 1] In line visualization pipeline execution timeline
## Catalyst-ADIOS2 in transit
In the situation explained in the previous section, this Catalyst 2 in situ visualization pipeline needs to complete synchronously when triggered after each (or every N) time step. This constraint can significantly increase the total simulation runtime. To avoid this pitfall, a new Catalyst implementation was created, [named Catalyst-ADIOS2](https://www.kitware.com/catalyst-adios2-a-new-catalyst2-implementation-for-in-transit-analysis/). Instead of processing data in line with the simulation, Catalyst-ADIOS2 delegates the visualization pipeline execution to different computation nodes. This way, the simulation can resume once the data transfer is complete, and the visualization workload is executed asynchronously. This type of **in situ** analysis where the visualization work is performed on separate nodes is referred to as **in transit** , as opposed to **in line**. This is particularly useful for more complex visualization pipelines that can take advantage of GPU compute units for rendering, that may be available in nodes dedicated to visualization but not necessarily in simulation ones. From a technical perspective, this time, the visualization pipeline cannot simply use memory shared with the simulation running on the same machine, and needs to be sent through the network. This task is delegated to the ADIOS2 library, which is able to handle multiple distributed readers and writers. The drawback of this approach is that the output data is yet again transferred, defeating the original purpose of in-situ, which was relying on data already in memory, avoiding any costly copy.
![](https://www.kitware.com/main/wp-content/uploads/2024/08/InTransit.svg)[fig 2] In transit execution timeline
## Catalyst-ADIOS2 hybrid
In-transit processing introduced in the previous section helped accelerate workflows where a larger asynchronous visualization pipeline execution time compensated for synchronous data transfer times between both compute clusters. However, for workflows where data size is very large, as is it often the case in HPC, full data transfer over the network is simply not a faster option than doing all the visualization work in situ. I/O can quickly become the bottleneck when using **in transit** , which defeats the main idea of **in situ** by introducing the need for data movement. With this in mind, we had to find a way to reduce the amount of data transferred, in order to keep the transfer time low.
We realized that many visualization workflows only use part of the total data for rendering: common reduction methods involve clipping, surface extraction, slicing, down-sampling or selecting an area of interest. Our new “hybrid” approach involves a first reduction step done **in line** on the simulation nodes, before sending the data **in transit** to the visualization nodes for rendering. This way, we decrease the amount of data sent over the network, while still delegating most of the visualization work to the dedicated visualization nodes. We call it a “hybrid” between in line and **in transit** (first and second section), because we first reduce data **in line** on the computation nodes, and then send this reduced data just like we did in the **in transit** mode. See the timeline depicted figure 3 for a comprehensive view of our hybrid processing.
![](https://www.kitware.com/main/wp-content/uploads/2024/08/Hybrid.svg)[fig 3] Hybrid in situ **In transit** execution timeline
We have implemented this idea in the [Catalyst-ADIOS2 implementation](https://gitlab.kitware.com/paraview/adioscatalyst) of Catalyst2. The user provides two ParaView Python scripts to the simulation which is instrumented using Catalyst. Catalyst-ADIOS2 runs the first script in line on the simulation nodes, applying reduction filters and “extracting” the reduced data, which is then sent to the Visualization nodes using ADIOS2. From there, the simulation resumes on the computation nodes, and the visualization nodes can do the rest of the visualization at the same time using the second ParaView-Python script, generating images of the reduced data for instance. You can view an example of this [on the Catalyst-ADIOS2 repository](https://gitlab.kitware.com/paraview/adioscatalyst/-/tree/main/Examples/Hybrid?ref_type=heads).
## Conclusion
These new developments create exciting new opportunities to apply**in transit** workflow on a larger scale. All the work described in this article is [available publicly](https://gitlab.kitware.com/paraview/adioscatalyst), under a permissive open-source license. There is always room for improvement and experimentation with this new technology, including AI-driven data reduction, which has yet to be tried.
This work led to a paper presented by Kitware at the [8th International Workshop on In Situ Visualization](https://woiv.gitlab.io/woiv24/), held in conjunction with ISC High Performance 2024, in May 2024. You can read the pre-print version [here](https://arxiv.org/abs/2406.18112).
Tags:
[Catalyst](https://www.kitware.com/tag/catalyst/)[ParaView](https://www.kitware.com/tag/paraview/)
##  1 comment to In Situ – In Transit Hybrid Analysis using Catalyst-ADIOS2 and ParaView 
  1. **Sean Ahern** says:
[October 11, 2024 at 4:00 pm](https://www.kitware.com/in-situ-in-transit-hybrid-analysis-using-catalyst-adios2-and-paraview/#comment-2079)
You might rephrase the sentence “We recommend reading this first blog post before this one if you have not already”. Your meaning might be conveyed better as “If you haven’t read it already, we suggest reading that initial blog post before diving into this one.”
[Reply](https://www.kitware.com/in-situ-in-transit-hybrid-analysis-using-catalyst-adios2-and-paraview/?replytocom=2079#respond)


### Leave a Reply[Cancel reply](https://www.kitware.com/in-situ-in-transit-hybrid-analysis-using-catalyst-adios2-and-paraview/#respond)
![](https://www.kitware.com/main/wp-content/uploads/2024/08/slice7.gif)
  * [Home](https://www.kitware.com)
  * [EU](http://www.kitware.eu)
  * [Careers](https://www.kitware.com/careers/)
  * [Contact Us](https://www.kitware.com/contact/)


  * [About](https://www.kitware.com/about/)
    * [Our Expertise](https://www.kitware.com/expertise/)
    * [Our Open Philosophy](https://www.kitware.com/open-philosophy/)
    * [Meet our Team](https://www.kitware.com/meet-the-team/)
    * [Our Publications](https://www.kitware.com/kitware-publications/)


  * [Solutions](https://www.kitware.com/solutions)
    * [Government](https://www.kitware.com/government/)
      * [Defense](https://www.kitware.com/government/defense/)
      * [Intelligence](https://www.kitware.com/government/intelligence/)
      * [Energy](https://www.kitware.com/government/energy/)
      * [Healthcare](https://www.kitware.com/government/healthcare/)
      * [Other](https://www.kitware.com/government/other/)
    * [Industry Solutions](https://www.kitware.com/industry/)
      * [Support](https://www.kitware.com/support/)
      * [Training](https://www.kitware.com/training/)
      * [Applied Research & Engineering](https://www.kitware.com/industry/applied-research-prototype-engineering/)
      * [Development and Deployment](https://www.kitware.com/industry/development-and-deployment/)
      * [Product Enhancement and Evolution](https://www.kitware.com/industry/product-enhancement-and-evolution/)
    * [Open Source Technologies](https://www.kitware.com/open-source/)


  * [News](https://www.kitware.com/media/)
    * [Blog](https://www.kitware.com/blog/)
    * [Press Room](https://www.kitware.com/press-room/)
    * [Events](https://www.kitware.com/events-directory/)
    * [Software Releases](https://www.kitware.com/software-releases/)


  * [©2025 Kitware, Inc](https://www.kitware.com)
  * [](https://twitter.com/Kitware)
  * [](https://www.linkedin.com/company/kitware-inc-)
  * [](https://www.facebook.com/kitware)
  * [](https://vimeo.com/kitware)


  * [Privacy Statement](https://www.kitware.com/privacy/)
  * [Policy Information](https://www.kitware.com/policy/)
  * [Conference Archives](https://www.kitware.com/conference-archives/)


![](https://pixel.wp.com/g.gif?v=ext&blog=200605823&post=73825&tz=-5&srv=www.kitware.com&j=1%3A15.4&host=www.kitware.com&ref=&fcp=0&rand=0.6819686646745626)
