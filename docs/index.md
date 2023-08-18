# Overview

The UNSW Workflow Platform implements commonly used pipelines for the analysis of next-generation sequencing data on the UNSW High-Performance Computing (HPC) Infrastructure. 

## What are workflows and why are they useful?
Workflows are data analysis pipelines implemented using a workflow manager. In general, workflow managers simplify the use of complex pipelines composed of multiple software tools by handling software installation and versions and optimizing the use of computing resources. Implementing pipelines as workflows on the UNSW HPC has the following advantages:

1.	**Shareability** Pipelines implemented as workflows are easy to share and use by any UNSW research group since the software installation and version management are handled by the workflow manager.
2.	**Reproducibility** Workflow managers were developed to address the challenge of reproducibility in bioinformatics. Analyzing data in a consistent manner with a standardized well documented pipeline. 
3.	**Productivity** Increased productivity is achieved by linking the data analysis pipelines to the Ramaciotti Centre data production. In addition, the bioinformatics community is increasingly producing best-practice data analysis pipelines that are easy to adopt in a workflow format, facilitating working with new data types.

For more details on the goals and advantages of bioinformatics workflows see: [Wratten et al. Reproducible, scalable, and shareable analysis pipelines with bioinformatics workflow managers. Nature Methods 2021.](https://www.nature.com/articles/s41592-021-01254-9)
 
The workflow manager employed by UNSW WP is **Nextflow**. Its main advantage is the fact that it has been broadly adopted by the bioinformatics community with bioinformatics protocols often published as Nextflow workflows, and an active community developing open-source bioinformatics pipelines that aim to implement the best practice in the field, called **Nextflow Core (nf-core)**.
For more details on **nf-core pipelines** see [Ewels et al. The nf-core framework for community-curated bioinformatics pipelines. Nature Biotechnology 2022.] (https://www.nature.com/articles/s41587-020-0439-x)  

![Image title](./assets/gwp-overview.svg#only-light)
![Image title](./assets/gwp-overview-dark.png#only-dark)
