# Circular RNA-Seq

## Introduction

!!! warning
    Unfortunately, `nf-core/circrna` is still considered under development and has been for some time. At least two labs at UNSW focus on circular RNAs - [contact us](../../support.md) if this is important to you.

One common precursor to robust circular RNA studies is combining multiple detection methods. The community pipleline `nf-core/circrna` currently supports ciriquant, circexplorer2, find_circ, circrna_finder, mapsplice, dcc and segemehl, along with various QC steps. It outputs both separated and combined counts for downstream analysis. Unlike `nf-core/rnaseq`, it can also perform differential expression analysis if you provide Phenotype.csv.

1. Download your data