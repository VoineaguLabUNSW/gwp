Title: Introduction to the Genomics Workflow Platform (GWP) 

## 
The goal of the Genomics Workflow Platform is to implement commonly used pipelines for the analysis of next-generation sequencing data on the UNSW High-Performance Computing (HPC) Infrastructure. 
“Genomics” is used here in a broad sense, including transcriptomics and epigenomics.

## What is a workflow and why should you use it?
Workflows are data analysis pipelines implemented using a workflow manager. In general, workflow managers simplify the use of complex pipelines composed of multiple software tools by handling software installation and versions and optimizing the use of computing resources. Implementing pipelines as workflows on the UNSW HPC has the following advantages:
1.	**Shareability.** Pipelines implemented as workflows are easy to share and use by any UNSW research group since the software installation and version management are handled by the workflow manager.
2.	**Reproducibility.** Workflow managers were developed to address the challenge of reproducibility in bioinformatics. Analyzing data in a consistent manner with a standardized well documented pipeline. 
3.	**Productivity.** Increased productivity is achieved by linking the data analysis pipelines to the Ramaciotti Centre data production. In addition, the bioinformatics community is increasingly producing best-practice data analysis pipelines that are easy to adopt in a workflow format, facilitating working with new data types.

For more details on the goals and advantages of bioinformatics workflows see: [Wratten et al. Reproducible, scalable, and shareable analysis pipelines with bioinformatics workflow managers. Nature Methods 2021.](https://www.nature.com/articles/s41592-021-01254-9)
 
The workflow manager employed by UNSW GWP is **NextFlow**. Its main advantage is the fact that it has been broadly adopted by the bioinformatics community with bioinformatics protocols often published as NextFlow workflows, and an active community developing open-source bioinformatics pipelines that aim to implement the best practice in the field, called **Next Flow Core (nf-core)**.
For more details on nf-core pipelines see [Ewels et al. The nf-core framework for community-curated bioinformatics pipelines. Nature Biotechnology 2022.] (https://www.nature.com/articles/s41587-020-0439-x)  





There are over 75 nf-core community workflows, below are some that we have manually tested on Katana. View the full list [here](https://nf-co.re/pipelines) - note [nf-core/proteinfold](https://nf-co.re/proteinfold) is not currently supported, as there are better ways of doing this at UNSW.

<figure markdown>
![Image title](./assets/kod_genomic_workflows.png){ width="400" }
<figcaption>via Katana OnDemand</figcaption>
</figure>

### Frequently Used
| Workflow 	| Summary 	| Expected Space* 	| Expected Time* 	| Guide 	|
|---	|---	|---	|---	|---	|
| [nf-core/rnaseq](https://nf-co.re/rnaseq){target=”_blank”}	| Turns .fastq files and annotated genome into trimmed and aligned .bam files, detailed multiqc and gene count matrix. You can then perform differential expression in e.g. R. Typically takes around 4 hours and 1-2TB of space for human data. Note [for prokaryotes]( https://nf-co.re/rnaseq/3.12.0/usage#prokaryotic-genome-annotations ). 	| 1-2TB 	| 4hr 	| [Bulk Rna-Seq](./Guides/RNA-Seq/bulk.md) 	|
| [nf-core/scrnaseq](https://nf-co.re/scrnaseq){target=”_blank”} 	| RNA-Seq for 10x single cell data, supporting Alevin, STARSolo, Kallisto, Cellranger, UniverSC. 	| 2TB 	| 6hr 	|  [Single-Cell Rna-Seq](./Guides/RNA-Seq/single_cell.md)	|
| [nf-core/circrna](https://nf-co.re/circrna){target=”_blank”} 	| Still under development/unfinished - [our fork](https://github.com/WalshKieran/circrna/tree/dev) fixes some minor ongoing issues, but should not be relied upon. Long duration is specificlly due to CIRI2.	| 4TB 	| 48hr 	| [Circular Rna-Seq](./Guides/RNA-Seq/circular.md)	|

(*) These metrics obviously depend greatly on sequencing depth, genome size and (in the case of space) number of samples. The current estimates are based on multiple human datasets.

## Reproducibility

Nextflow on Katana is configured to use Singularity containers. This means that when you specify an exact version of a pipeline that utilises containers, identical builds of each software will be used.

