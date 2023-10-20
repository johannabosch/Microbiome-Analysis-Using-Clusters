## **Comparative *16S* Amplicon Analysis Using QIIME2 on a Computing Cluster: Tutorial and Resources**

This is a public repo that can be used to learn how to conduct a comparative 16S amplicon analysis via QIIME2's microbiome analysis suite[^1] on a computing cluster hosted by the Digital Research Alliance of Canada's (Graham cluster) [^2]. With access to the internet, you can access the cluster from any desktop or laptop computer to run this analysis. 

The tutorial is written in Bookdown format and covers each command and tool used step-by-step to run these commands in the cluster, and export your data afterwards for further downstream analysis. The analysis methods are formally reviewed in Bosch et al. [^3], and outline each plug-in that is used, their associated references and the results of the study - methods are outlined in Chapter 3. 

### 🧬 **A brief review of the data used in this analysis:**

  The data used in this analysis was taken from a thesis project that focuses on the transfer of seabird nutrients from a seabird nesting colony in Cape St. Mary’s Ecological Reserve (Newfoundland, Canada) [^3]. Review this graphical abstract to understand the ecological processes taking place here:

![image](https://github.com/johannabosch/QIIME2_for_Graham/assets/126937348/9ec5fe4e-161f-4e4c-9c4b-d93eb391cef2)
>  <sup> **Figure:** Seabird nutrient transfer from Bird Rock, in Cape St. Mary’s Ecological Reserve (Newfoundland) to a pond 240 m away from the seabird colony. Seen in the illustration are northern gannets (*Morus bassanus*) and black-legged kittiwakes (*Rissa tridactyla*), which both nest within the Reserve on an annual basis. [^3] <sup>                                                          

Using targeted *16S* amplicon sequencing, we assessed how the transfer of nutrients by seabirds in Cape St. Mary's impacts the bacterial composition of sediments taken from ponds nearby a colony. We used QIIME2, a next-generation microbiome bioinformatics suite that offers a free, user-friendly, and open source platform for both advanced and beginner researchers [^1].

___

### **Resources:**

This analysis uses various software and tools which are mostly available through the Graham cluster. Here is a list of some of the coding languages, tools and softwares we used in this analysis: 

> **[R/RStudio](https://www.r-project.org/)** is used for generating plots using the QIIME2R and Phyloseq packages. R is a statistical programming language widely employed in data analysis and visualization, while RStudio provides an integrated development environment (IDE) for working with R [^4].

> **[Python](https://www.python.org/)** is utilized during the quality checking stage through the MultiQC tool. Python is a versatile programming language known for its simplicity and extensive libraries, making it suitable for a variety of data processing tasks [^5].

> **[FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)** is a quality control tool used to assess the quality of sequencing data [^6].

> **[MultiQC](https://multiqc.info/)** is a tool that aggregates results from multiple bioinformatics analyses into a single, comprehensive report to evaluate and summarize quality control metrics [^7]. 

> **[QIIME2](https://qiime2.org/)** is a powerful microbiome analysis platform used extensively in this analysis. It provides a comprehensive suite of tools for processing, analyzing, and visualizing microbiome data [^1].

Near the end of this analysis, we export the final files from the cluster to a local compter (your computer) and use two different R packages locally to run a few other analyses and plot a taxonomic heatmap and barplot. While QIIME2 does offer heatmap/barplot capabilities, the aesthetic features are more limited than QIIME2R and Phyloseq. To use QIIME2R and Phyloseq on your local computer, make sure you have [R and RStudio](https://rstudio-education.github.io/hopr/starting.html) installed.

> [**QIIME2R**](https://github.com/jbisanz/qiime2R): QIIME2R is an R package that enables integration between QIIME2 and R. It allows importing QIIME2 artifacts and visualizing data within the R environment, and offers further data exploration beyond what QIIME2 currently offers [^8].

> [**Phyloseq**](https://joey711.github.io/phyloseq/): Phyloseq is an R package that works seamlessly with QIIME2 data and provides a flexible framework for modifying and visualizing data [^9].

___


### 💻 **Using the Graham cluster for data analysis:**

  The first portion of this tutorial reviews using the Graham cluster for this analysis. Graham is a heterogeneous cluster, suitable for a variety of workloads, and located at the University of Waterloo [^2]. Using a computing cluster enables:
- efficient processing of large datasets
- parallel computing for faster results (covered in my (Metagenomics  tutorial)[LINK])
- access to a collaborative community of researchers
- the flexibility of accessing files from any computer with internet access.

To read more about getting started with the Graham cluster visit their documentation: (https://docs.alliancecan.ca/wiki/Getting_started_with_the_new_national_systems)

  The cluster is useful for running jobs that are intensive; jobs are run as a simple text file that contains information about which allocation to run the job on, and let's you specify how many compute nodes the job needs, how much memory the job needs, and how long the job will take to run. Running job scripts in the Graham cluster is covered in this analysis.

___


### 💬**Technical support at the Alliance:**
  E-mail CCDB if you have trouble with your account or even if you have questions about your job scripts or commands while running an analysis. They have a helpful team of individuals who will reply to your e-mails promptly and point you in the right direction.

E-mail|Purpose|
|----|-----|
accounts@tech.alliancecan.ca | For questions about accounts | 
renewals@tech.alliancecan.ca | For questions about account renewals |
globus@tech.alliancecan.ca | For questions about Globus file transfer services |
cloud@tech.alliancecan.ca | For questions about using Cloud resources |
support@tech.alliancecan.ca | For any other questions, including questions related to your bioinformatics analysis |

> **NOTE:** If you are going to contact support, make sure to read this technical support page first to know what to include in your message: (https://docs.alliancecan.ca/wiki/Technical_support)

___

### 📝 **Acknowledgments**
  I would like to acknowledge the *Amplicon analysis tutorial using QIIME2* by Comeau et al. [^10] that was used as a reference guide while I conducted my own analysis, as well as the support team at the Alliance for troubleshooting issues I encountered while carrying out this project.
___
___

### 📚 **References:**

[^1]: Bolyen E, Rideout JR, Dillon MR, Bokulich NA, Abnet CC, Al-Ghalith GA, et al. 2019 Reproducible, interactive, scalable and extensible microbiome data science using QIIME 2. Nature Biotechnology 37: 852–857. (https://doi.org/10.1038/s41587-019-0209-9](https://www.nature.com/articles/s41587-019-0209-9)

[^2]: CCDB 2023. Graham. CCDB Docs. URL: (https://docs.alliancecan.ca/wiki/Graham)

[^3]: Bosch, J. 2023 From Seabirds to Sediments: The ecological footprint of seabirds at a prominent North Atlantic breeding colony tracked using a multi-proxy paleolimnological approach. Memorial University of Newfoundland [unpubl. thesis]

[^4]: R Core Team. 2021 R: A language and environment for statistical computing. R Foundation for Statistical Computing, Vienna, Austria. URL: (https://www.R-project.org/)

[^5]: Van Rossum G, Drake Jr FL. 1995 Python reference manual. Centrum voor Wiskunde en Informatica Amsterdam.

[^6]: Andrews S. 2010 FastQC: a quality control tool for high throughput sequence data. URL: (http://www.bioinformatics.babraham.ac.uk/projects/fastqc)

[^7]: Ewels P, Magnusson M, Lundin S, Käller M. 2016 MultiQC: summarize analysis results for multiple tools and samples in a single report. Bioinformatics. 32(19):3047-8. URL: (https://academic.oup.com/bioinformatics/article/32/19/3047/2196507)

[^8]: Jordan E Bisanz. 2018 qiime2R: Importing QIIME2 artifacts and associated data into R sessions [Internet].  URL: https://github.com/jbisanz/qiime2R.

[^9]: McMurdie PJ, Holmes S. 2013 phyloseq: an R package for reproducible interactive analysis and graphics of microbiome census data. PloS one. 8(4):e61217. URL: (https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0061217)

[^10]: Comeau AM, Douglas GM, Langille M. 2017 Microbiome Helper: A custom and 
