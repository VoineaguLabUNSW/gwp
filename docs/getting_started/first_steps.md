# First Steps

To get started with the UNSW Workflow Platform, you will need the following:

### 1. Katana Account
You will need an account on the Katana servers and some basic ability to use Katana.
####  Obtaining a Katana Account
To apply for an account you can send an email to the UNSW IT Service Centre giving your zID, your role within UNSW and the name of your supervisor.

If your lab/group has a dedicated scratch space, they can contact us to grant you access to this shared space. This can be useful if your data and results files exceed you personal account space.

#### Using Katana Servers

See [New to Katana?](#new-to-katana) for a summary of what's needed to get started, or the full [official documentation](https://docs.restech.unsw.edu.au).

### 2. Sequencing Data
Sequencing data can be specified as either:

- **A path to a directory on Katana** (eg. /srv/scratch/zID/myProject/Data).
- **A link provided by the Ramaciotti Centre** 
    If your sequencing data has been generated at the Ramaciotti Centre, you will receive a url for downloading the data, such as: 
    https://mydata.ramaciotti.unsw.edu.au/s/PiE96tn58FZAZbs/download/ProjectID.tar. You can provide this link in the nf-core pipeline, without downloading the data. 
    
    You will need to provide the path to an existing directory on Katana, where the pipeline should download the data, eg. /srv/scratch/zID/myProject/Data.

- **An NCBI SRA number**
    If your would like to analyze publicly available data from NCBI/SRA, you can provide the SRA project ID, such as SRPXXXX without downloading the data. Note that GEO Id (GSEXXX) numbers are not supported. 

    You will need to provide the path to an existing directory on Katana, where the pipeline should download the data, eg. /srv/scratch/zID/myProject/Data.

### 4. Understand the pipeline
This includes understanding each of the software tools included in the pipeline, the parameters of each tool, and the expected output files. nf-core pipelines include extensive documentation (eg. nf-core RNA-seq). In addition, we strongly encourage you to spend some time reading the documentation of each software tool included in the pipeline.

## New to Katana?
The UNSW on-premise HPC, Katana, is encouraged for Nextflow users and is a good entry-point for HPC in general. That being said, NCI Gadi also has [official documentation](https://opus.nci.org.au/display/DAE/Nextflow) for running Nextflow, and supports Nextflow Tower using the `Agent` method.

Once you have covered the basics of Nextflow, it is trivial to run workflows using the `local` executor. This is especially true with prokaryotic genomes. In fact, aside from genome indexing, only a few steps in RNA-Seq consistently require over 16GB RAM for human reads. If you are new to HPC, we still think it's worth learning the basics so that:

1. You can use the same documentation for **any genome**
2. Runtime is not as dependent on **number of samples**
3. It's much easier to receive technical **support**

The following will be a subset of the official documentation, intended for biologists.

### Logging In

Whether you connect via a file browser or a terminal, there are two addresses to remember: the login nodes, used to start jobs/monitor jobs, and the Katana data mover - **<zid\>@katana.unsw.edu.au** and **<zid\>@kdm.restech.unsw.edu.au** respectively.

If you login via SSH to Katana, remaining space in your available [storage locations](https://docs.restech.unsw.edu.au/storage/storage_locations/#storage-summary) will be listed. You may notice by default, your largest available folder is "user scratch" (/srv/scratch/<zid\>) at 128GB. If your group has a shared scratch folder (often many terabytes in size), they can [contact us](https://docs.restech.unsw.edu.au/#contact-the-research-technology-services-team) for your account be granted access.

### Moving Data

The most pertinent step in bioinformatics is copy e.g. .fastq.gz read files to Katana and copy the results back out. Consider downloading directly from the source when possible, as Katana's internet connection is likely many times faster than moving it through your own machine.

To get started, you can connect [FileZilla](https://docs.restech.unsw.edu.au/storage/kdm/#filezilla) directly to the Katana data mover and access all your files described in [storage locations](https://docs.restech.unsw.edu.au/storage/storage_locations/#storage-summary).

### Checking Available Space
While knowledge of storage location quotas is good when you don't have any existing files, it's important to continuously check remaining space when running large biological workflows that produce a lot of output. Relocating a failed Nextflow run to a different (larger) scratch is easy, but it will re-run every subtask unless a lot of care is taken. 

It is straightforward to use [FileZilla](https://docs.restech.unsw.edu.au/storage/kdm/#filezilla) to check available space. When you login via command-line, the first message will overview current usage (accurate to ~10 minutes) or you can run `df -H`.

### Katana OnDemand

You can run various GUI applications such as RStudio directly from your browser using [Katana OnDemand](https://docs.restech.unsw.edu.au/using_katana/ondemand/). This includes RStudio and the Genomic Workflow Utility.
