---
layout: post
title:  "Note_NextFlow"
date:   2025-02-26 16:26:57 +0000
categories: Note
---


#### Website Summary

[Nextflow](https://www.nextflow.io/docs/latest/index.html) is a flexible and scalable workflow management system designed for reproducible and portable data analysis, enabling seamless execution across local, cloud, and HPC environments.  
[Nextflow Example](https://www.nextflow.io/example1.html)  
[nf-core](https://nf-co.re/docs/usage/getting_started/introduction) is a community-driven framework for creating, sharing, and maintaining high-quality, scalable, and reproducible Nextflow pipelines for bioinformatics workflows.  
[Roslin-nf-core](https://www.wiki.ed.ac.uk/display/RosBio/Nextflow+and+nf-core)  
[Sarek](https://github.com/nf-core/sarek) is a workflow designed to detect variants on whole genome or targeted sequencing data. Initially designed for Human, and Mouse, it can work on any species with a reference genome. Sarek can also handle tumour / normal pairs and could include additional relapses.  
[VScode](https://code.visualstudio.com/docs) is a free, open-source, cross-platform code editor by Microsoft, offering robust features like IntelliSense, debugging, Git integration, and a vast extension library to streamline development across diverse programming languages.  
[Docker](https://docs.docker.com/desktop/setup/install/mac-install/) is a platform that automates the deployment, scaling, and management of applications inside lightweight, portable containers, ensuring consistency across different environments.   
[HomeBrew](https://docs.brew.sh/Manpage) is a package manager for macOS and Linux that simplifies the installation and management of software and libraries from the command line. 



#### Example Nextflow
```
#!/usr/bin/env nextflow

params.in = "$baseDir/data/sample.fa"

/*
 * Split a fasta file into multiple files
 */
process splitSequences {

    input:
    path 'input.fa'

    output:
    path 'seq_*'

    """
    awk '/^>/{f="seq_"++d} {print > f}' < input.fa
    """
}

/*
 * Reverse the sequences
 */
process reverse {

    input:
    path x

    output:
    stdout

    """
    cat $x | rev
    """
}

/*
 * Define the workflow
 */
workflow {
    splitSequences(params.in) \
      | reverse \
      | view
}
```
