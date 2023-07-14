Title: Katana

The UNSW on-premise HPC, Katana, is encouraged for Nextflow users and is a good entrypoint for HPC in general. That being said, NCI Gadi also has [official documentation](https://opus.nci.org.au/display/DAE/Nextflow) for running Nextflow, and supports Nextflow Tower using the `Agent` method.

## Why HPC?

Once you have covered the basics of Nextflow, it is trivial to run workflows using the `local` executor. This is especially true with prokaryotic genomes. In fact, aside from genome indexing, only a few steps in RNA-Seq consistently require over 16GB RAM for human reads. If you are new to HPC, we still think it's worth learning the basics so that:

1. You can use the same documentation for **any organism**
2. Runtime is no longer dependant on **number of samples**
3. It's much easier to receive technical **support**

## Getting Started

Refer to the [official documentation](https://docs.restech.unsw.edu.au/using_katana/accessing_katana/) for account creation. The following will be a subset of the official site, intended for biologists.

### Logging In

Whether you connect via a file browser or a terminal, there are two addresses to remember: the login nodes, used to start jobs/monitor jobs, and the Katana data mover - **<zid\>@katana.unsw.edu.au** and **<zid\>@kdm.restech.unsw.edu.au** respectively.

If you login via SSH to Katana, remaining space in your available [storage locations](https://docs.restech.unsw.edu.au/storage/storage_locations/#storage-summary) will be listed. You may notice by default, your largest available folder is "user scratch" (/srv/scratch/<zid\>) at 128GB. If your group has a shared scratch folder (often many terabytes in size), they can [contact us](https://docs.restech.unsw.edu.au/#contact-the-research-technology-services-team) for your account be granted access.

### Moving Data

The most pertinent step in bioinformatics is copy e.g. .fastq.gz read files to Katana and copy the results back out. Consider downloading directly from the source when possible, as Katana's internet connection is likely many times faster than moving it through your own machine.

To get started, you can connect [FileZilla](https://docs.restech.unsw.edu.au/storage/kdm/#filezilla) directly to the Katana data mover and access all your files described in [storage locations](https://docs.restech.unsw.edu.au/storage/storage_locations/#storage-summary).

### Katana OnDemand

You can run various GUI applications such as RStudio directly from your browser using [Katana OnDemand](https://docs.restech.unsw.edu.au/using_katana/ondemand/). This includes RStudio and the Genomic Workflow Utility.



