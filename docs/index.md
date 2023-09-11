---
title: Overview
template: home.html
hide:
  - toc
  - path
---
The UNSW Workflow Platform implements commonly used pipelines for the analysis of next-generation sequencing data on the UNSW High-Performance Computing (HPC) Infrastructure.

??? quote "Overview of Workflows for Sequencing Data Analysis"

    Workflows are data analysis pipelines implemented using a workflow manager. In general, workflow managers simplify the use of complex pipelines composed of multiple software tools by handling software installation and versions and optimizing the use of computing resources. Implementing pipelines as workflows on the UNSW HPC has the following advantages:

    1. **Shareability** Pipelines implemented as workflows are easy to share and use by any UNSW research group since the software installation and version management are handled by the workflow manager.

    2. **Reproducibility** Workflow managers were developed to address the challenge of reproducibility in bioinformatics. Analyzing data in a consistent manner with a standardized well documented pipeline.

    3. **Productivity** Increased productivity is achieved by linking the data analysis pipelines to the Ramaciotti Centre data production. In addition, the bioinformatics community is increasingly producing best-practice data analysis pipelines that are easy to adopt in a workflow format, facilitating working with new data types.

    For more details on the goals and advantages of bioinformatics workflows see:

    <a target="_blank" href="https://www.nature.com/articles/s41592-021-01254-9">Wratten et al. Reproducible, scalable, and shareable analysis pipelines with bioinformatics workflow managers. Nature Methods 2021.</a>
    
## Overview of the UNSW Seq-flow platform

The analysis of next-generation sequencing (NGS) data, regardless of its type, has two main stages: (i) alignment of sequencing reads to the reference genome, feature quantification, and quality control assessments and  (ii) extracting biological information from the quantified features by differential expression analyses or co-expression networks (RNA-seq), differential accessibility (ATAC-seq), identification of differentially methylated regions (BS-seq) etc.

**The Seq-flow Platform is focused on implementing pipelines for the first stage of NGS data analysis which is computationally intensive, requires larger storage space and more advanced coding skills, and can be easily automated.** It is not focused on the second stage, which requires fine-tuning of data analysis in a project-specific manner and can often be carried out on a personal laptop with basic bioinformatics skills (eg. R/Bioconductor). We do however suggest good options for some common downstream analyses for students with limited coding experience.


<figure markdown>
![Image title](./assets/gwp-overview.svg#only-light){ width="800" }
![Image title](./assets/gwp-overview-dark.svg#only-dark){ width="800" }
<figcaption>Seq-flow is implemented as both a <span style="background-color:#45a9bf55">Web User Interface</span> and a <span style="background-color:#d1ad5255">Command Line Interface</span> using the workflow manager Nextflow.</figcaption>
</figure>

Seq-flow supports input sequencing data:

- stored on UNSW Katana servers.
- automatically downloaded on Katana from a Ramaciotti Sequencing run.
- automatically downloaded on Katana from NCBI SRA.

<hr>

Seq-flow allows users to run any of the large collection of Nextflow Core pipelines.

Nextflow Core (nf-core) is an active bioinformatics community developing open-source pipelines based on NextFlow that aim to implement the best practices in the field.  For more details on nf-core pipelines see: 

<a href="https://www.nature.com/articles/s41587-020-0439-x">Ewels et al. The nf-core framework for community-curated bioinformatics pipelines. Nature Biotechnology 2022.</a>

<hr>

The nf-core pipelines fall into two categories in terms of their use in Seq-flow:

1. **Pre-tested pipelines**, which we have extensively tested and documented. These include the bulk RNA-seq pipeline (for any organism) and scRNA-seq.
2. **User-adopted**, which refers to any nf-core pipeline not yet tested by the Seq-flow team. We can offer support for UNSW users interested in using and testing additional nf-core pipelines, to expand the list of pre-tested pipelines.

Users can also deploy custom NextFlow workflows in Seq-flow.

<div class="button-container">
  <a href="./getting_started/choosing_interface" class="md-button md-button--primary">Getting Started</a>
  <a href="./guides/RNA-Seq/bulk" class="md-button md-button--primary">User Guides</a>
  <a href="./support" class="md-button primary md-button--primary">Support</a>
</div>

