# Experimental Design

## Introduction

The downstream analysis of most RNA-Seq studies involves some form of differential expression - as such, it is important to increase statistical power by decreasing variance using biological and technical replicates. There are no parameters for this!

Even if you already have sequenced data and are confident in your design, terminology in bioinformatics is often re-used. This page is intended to be a concise reference for the most common concepts and terms needed to start running a workflow on Katana - see Melbourne Bioinformatic's [terrific guide](https://www.melbournebioinformatics.org.au/tutorials/tutorials/rna_seq_exp_design/rna_seq_experimental_design/) for a more in-depth discussion.

### RNA Amount  
The Ramaciotti Center has [minimum requirements](https://www.ramaciotti.unsw.edu.au/sample-submission/sample-requirements) for this depending on the service. While samples certainly undergo degredation checks, you can verify this yourself using the [nf-core/rnaseq](./bulk.md) optional parameter *--rseqc_modules tin* i.e. TIN (transcript integrity number), analagous to RIN.

### rRNA Depletion
To avoid unwanted ribosomal RNA saturating your results, you must either use poly-A enrichment or specifically deplete rRNA using e.g. a kit. Poly-A enrichment is generally recommended **unless** studying non-coding RNAs (including circular RNAs) or your RNA is quite degraded. A higher amount of RNA is needed for rRNA depletion - furthermore, if using [nf-core/rnaseq](./bulk.md), the *--remove_ribo_rna* parameter can be used to filter out lingering ribosomal rna when using this method.

### Single-Read or Paired-End Sequencing
From a pure informational standpoint, paired-end sequencing is not requried for differential expression, but is needed for transcription structure/splice sites. However, the known distance between read pairs is used by the alignment algorithm to produce a more accurate result. If using [nf-core/rnaseq](./bulk.md), you can define either one or two fastq file paths to implicitly indicate single/paired-end respectively.

### Strandedness
Stranded protocols/kits are not necessary to count known transcripts in a typical RNA-Seq experiment, but are needed for novel transcript discovery. If using [nf-core/rnaseq](./bulk.md), the final column in the samplesheet is used to indicate a sample's strandedness: "unstranded", "forward" or "reverse". In versions >`3.12.0`, an additional option "auto" can be used to automatically infer strandeness using salmon - but it's still best to refer to your sequencing facility's exact kit when possible.

The following table is a tiny excerpt from Griffith Lab's extensive [guide](https://rnabio.org/module-09-appendix/0009/12/01/StrandSettings/) on how strandedness is provided to various tools when running them individually:

<table>
<thead>
  <tr>
    <th>Tool</th>
    <th>RF/fr-firststrand stranded (dUTP)</th>
    <th>FR/fr-secondstrand stranded (Ligation)</th>
    <th>Unstranded</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>check_strandedness (output)</td>
    <td>RF/fr-firststrand</td>
    <td>FR/fr-secondstrand</td>
    <td>unstranded</td>
  </tr>
  <tr>
    <td>HISAT2 (--rna-strandness parameter)</td>
    <td>R/RF</td>
    <td>F/FR</td>
    <td>NONE</td>
  </tr>
  <tr>
    <td>HTSeq (--stranded/-s parameter)</td>
    <td>reverse</td>
    <td>yes</td>
    <td>no</td>
  </tr>
  <tr>
    <td>STAR</td>
    <td>n/a</td>
    <td>n/a<br></td>
    <td>n/a</td>
  </tr>
  <tr>
    <td>Salmon (--libType parameter)</td>
    <td>ISR (assuming paired-end with inward read orientation)</td>
    <td>ISF (assuming paired-end with inward read orientation)<br></td>
    <td>IU (assuming paired-end with inward read orientation)</td>
  </tr>
  <tr>
    <td>Example kits</td>
    <td>dUTP, NSR, NNSR, Illumina TruSeq Strand Specific Total RNA, NEBNext Ultra II Directional</td>
    <td>Ligation, Standard SOLiD, NuGEN Encore, 10X 5’ scRNA data</td>
    <td>Standard Illumina, NuGEN OvationV2, SMARTer universal low input RNA kit (TaKara), GDC normalized TCGA data</td>
  </tr>
</tbody>
</table>

### Multiplexing
Multiplexing can be used to reduce errors, leading to more accurate counts - whether its PCR bias using UMIs, or index hopping using UDIs. The workflow [nf-core/rnaseq](./bulk.md) can be supplied with UMI barcode information if used.

### Spike-in Sequences
Spike-in controls were orignally synthetic RNA sequences added for normalization with varying results. If using [nf-core/rnaseq](./bulk.md), the parameter *--additional_fasta* was introduced for this purpose, but also represents an elegant way to append any custom sequence without keeping track of large locally modified reference genomes.
