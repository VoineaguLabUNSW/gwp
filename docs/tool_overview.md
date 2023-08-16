# Tool Overview

## Motivation

Bioinformatics is an umbrella term that *could* be loosly categorized into two main types of workflows - unique explorative research, performed in R or Jupyter Notebook, and the routine alignment/mapping/QC that often precedes it. The following is concerned with this latter category, since it is shared by multiple labs. 

![Image title](./assets/gwp-comparison.png#only-light)
![Image title](./assets/gwp-comparison-dark.png#only-dark)

The [nf-core](https://nf-co.re/) community workflows are highly maintained, and Nextflow itself is a good transferrable skill to have for your own workflows. They are now runnable entirely from graphical interfaces without compromising command line usability. This approach is not a replacement for [Galaxy](https://usegalaxy.org.au/), since the tool operations and orders cannot be arbitrarily modified using an interface.

## Different Ways to Run One Workflow

For a practical overview of each method, see the [launching comparison](./Guides/nextflow.md#launching-comparison)

|| Genomic Workflow Utility | Nextflow Tower | Command-line |
| -- | -- | -- | -- |
| Fast access of reads generated at Ramaciotti | :material-check-bold: | :octicons-x-16: | :octicons-x-16: |
| Parameter input | UI | UI | nf-params.json |
| Remote monitoring | Intermediate | Advanced | :octicons-x-16: |
| Initial configuration | None | Difficult, use Genomic Workflow Utility sidebar | Load module |