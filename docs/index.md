---
title: Overview
template: home.html
hide:
  - toc
  - path
---
The analysis of next-generation sequencing (NGS) data, regardless of its type, has two main stages: (i) alignment of sequencing reads to the reference genome, feature quantification, and quality control assessments and  (ii) extracting biological information from the quantified features by differential expression analyses or co-expression networks (RNA-seq), differential accessibility (ATAC-seq), identification of differentially methylated regions (BS-seq) etc.

<figure markdown>
![Image title](./assets/gwp-overview.svg#only-light){ width="800" }
![Image title](./assets/gwp-overview-dark.svg#only-dark){ width="800" }
<figcaption>Seq-Flow is implemented as both a <span style="background-color:#45a9bf55">Web User Interface</span> and a <span style="background-color:#d1ad5255">Command Line Interface</span> using the workflow manager Nextflow.</figcaption>
</figure>


**The Seq-flow Platform is focused on implementing pipelines for the first stage of NGS data analysis which is computationally intensive, requires larger storage space and more advanced coding skills, and can be easily automated.** It is not focused on the second stage, which requires fine-tuning of data analysis in a project-specific manner and can often be carried out on a personal laptop with basic bioinformatics skills (eg. R/Bioconductor). We do however suggest good options for some common downstream analyses for students with limited coding experience.


