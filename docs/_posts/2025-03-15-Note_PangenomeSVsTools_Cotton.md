---
layout: post
title:  "Note_PangenomeSVsTools_Cotton"
date:   2025-03-15 09:50:00 +0000
categories: Note
---


Structural variation (SV)-based pan-genome and GWAS reveal the impacts of SVs on the speciation and diversification of allotetraploid cottons [cotton Pangenome 2023](https://doi.org/10.1016/j.molp.2023.02.004)


### **Tools and Software Used in the Study**  

This study utilizes various bioinformatics tools and software for **genome assembly, structural variation (SV) detection, GWAS analysis, and population genetics**. Below is a list of the key tools and a brief description of their functions:

#### **Genome Assembly and Annotation**
1. **SuperNova (v2.1.1)** – Used for genome assembly from 10X Genomics linked-reads.  
2. **SOAPdenovo** – Another assembly tool used for de novo genome assembly.  
3. **LACHESIS** – Used for Hi-C based genome scaffolding.  
4. **HiC-Pro** – A pipeline for processing Hi-C sequencing data to create chromatin interaction maps.  
5. **RepeatMasker** – Used for identifying and masking repetitive sequences in the genome.  
6. **LTR_FINDER, RepeatScout, RepeatModeler** – Tools for de novo repeat annotation in genome sequences.  

#### **Structural Variation Detection and Pangenome Construction**
7. **MUMmer (v4.0.0)** – Used for whole-genome alignment and SV identification.  
8. **SyRI** – A tool for detecting structural rearrangements and SVs in genome alignments.  
9. **SURVIVOR (v1.0.7)** – Merges SV calls from different sources into a unified dataset.  
10. **vg (v1.32.0 "Sedlo")** – Used for constructing the pan-genome graph.  
11. **Giraffe (vg toolkit)** – A method for mapping sequencing reads to graph-based pan-genomes.  

#### **Genotyping and Variant Analysis**
12. **Bowtie2** – Used for aligning sequencing reads to a reference genome.  
13. **SAMtools (v1.9)** – Used for sorting, indexing, and processing alignment files.  
14. **BCFtools (v1.11)** – Used for variant filtering and manipulation of VCF/BCF files.  
15. **VCFtools (v0.1.12b)** – Used for variant statistics and filtering.  
16. **GATK (v4.1.2.0)** – Used for SNP calling and variant annotation.  
17. **ANNOVAR** – A tool for functional annotation of genetic variants.  

#### **Population Genetics and GWAS**
18. **VCF2Dis (v1.46)** – Used for calculating genetic distances and constructing phylogenetic trees.  
19. **iTOL** – A visualization tool for phylogenetic trees.  
20. **Genome-wide complex trait analysis (v1.91.4beta3)** – Used for PCA in population structure analysis.  
21. **Efficient mixed-model association expedited (EMMAX)** – Used for GWAS analysis.  
22. **CMplot** – A visualization tool for GWAS Manhattan plots.  

#### **Transcriptomic and Functional Analysis**
23. **HISAT2 (v2.2.1)** – Used for RNA-seq read alignment.  
24. **StringTie (v1.3.5)** – Used for transcript assembly and quantification.  
25. **QTLseqr (R package)** – Used for bulk segregant analysis (BSA-seq).  
26. **Integrative Genomics Viewer (IGV)** – Used for visualizing structural variations in genomic data.  

#### **Genetic Mapping and QTL Analysis**
27. **IciMapping (v4.1.0.0)** – Used for QTL mapping and genetic linkage analysis.  
28. **ALLMAPS** – Used for genetic and physical map collinearity visualization.  

#### **Other Bioinformatics Tools**
29. **Fastp (v0.20.1)** – A tool for quality control and trimming of sequencing reads.  
30. **Picard** – Used for processing alignment files and removing duplicates.  
31. **BSA-seq (Bulked Segregant Analysis)** – Used for identifying candidate genomic regions associated with specific traits.  

These tools enabled the researchers to **assemble a high-quality cotton genome, construct a pan-genome, detect SVs, and conduct association studies to identify trait-related genetic variations**.