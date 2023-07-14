Title: Bulk RNA-Seq

Bulk RNA-seq involves sequencing the RNA extracted from a population of cells or tissues as a whole for the purpose of counting, while attempting to maintain proportionality with e.g. actual transcript expression. This is complicated by the need to convert to cDNA for sequancing, various biases and in in eukaryotes - isoforms.

In this guide, we will use the best-practices Nextflow workflow, *nf-core/rnaseq* [(view official docs)](https://nf-co.re/rnaseq){target=”_blank”}. You can review alternate ways to run this guide (including command-line, Tower) in the general [Nextflow](../nextflow.md) section - the focus of this page will be on general steps and biological parameters.

1. Download your data