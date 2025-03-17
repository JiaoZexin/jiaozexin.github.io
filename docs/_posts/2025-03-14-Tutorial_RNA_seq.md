---
layout: post
title:  "Tutorial_RNA_seq"
date:   2025-03-14 20:45:00 +0000
categories: Tutorial
---


### **RNA-Seq（RNA测序）简介**  

#### **1. 什么是 RNA-Seq？**  
**RNA-Seq（RNA sequencing，RNA测序）** 是一种基于**高通量测序技术**的实验方法，用于分析**细胞或组织中所有转录本（转录组）**的组成、丰度和变化。RNA-Seq 可以揭示基因表达水平、可变剪切（alternative splicing）、基因融合事件、非编码RNA（如lncRNA、miRNA）以及单核苷酸变异（SNVs）等信息。

---

#### **2. RNA-Seq 的基本原理**
RNA-Seq 主要包括以下几个步骤：
1. **RNA 提取**：从细胞或组织中提取总 RNA 或特定 RNA（如 mRNA）。
2. **RNA 片段化**：将 RNA 打断成小片段，便于后续测序。
3. **cDNA 合成**：利用**逆转录（reverse transcription）**将 RNA 转录成 cDNA，并进行文库构建。
4. **文库构建**：添加接头（adapters），进行 PCR 扩增，构建适合高通量测序的 cDNA 文库。
5. **高通量测序**：使用**Illumina、PacBio 或 Nanopore** 等平台进行测序。
6. **数据分析**：
   - 质量控制（QC）
   - 比对到参考基因组或转录组（alignment）
   - 基因表达定量（differential expression analysis）
   - 变异检测（如可变剪切、融合基因、SNPs）
   - 富集分析（如 GO、KEGG 通路分析）

---

#### **3. RNA-Seq 的主要类型**
1. **mRNA-Seq（mRNA 测序）**  
   - 研究蛋白编码基因的表达水平和变化。
   - 适用于分析不同组织、发育阶段、疾病状态下的基因表达模式。

2. **Total RNA-Seq（总 RNA 测序）**  
   - 包括 mRNA 和非编码 RNA（如 rRNA、tRNA、lncRNA）。
   - 适用于全面解析转录组。

3. **Small RNA-Seq（小 RNA 测序）**  
   - 研究 miRNA、piRNA、siRNA 等小 RNA 分子。
   - 适用于研究基因调控网络。

4. **Strand-specific RNA-Seq（链特异性 RNA 测序）**  
   - 能区分正义链和反义链转录本，提高基因结构注释的准确性。

5. **Single-cell RNA-Seq（单细胞 RNA 测序, scRNA-Seq）**  
   - 研究单细胞水平的基因表达变化，揭示细胞异质性。
   - 适用于**肿瘤、免疫细胞、干细胞研究**。

6. **Ribo-Seq（核糖体 RNA 测序）**  
   - 研究**转录后调控**和**翻译动态**，揭示真实的蛋白合成情况。

---

#### **4. RNA-Seq 的优势**
✅ **高灵敏度**：可检测低丰度基因，动态范围比微阵列更广。  
✅ **无参考基因组要求**：适用于**非模式生物**或新物种研究。  
✅ **全面的转录组分析**：可研究**基因表达、可变剪切、基因融合、非编码 RNA** 等。  
✅ **可扩展性强**：适用于**单细胞测序、多组织测序、临床样本**等多种研究场景。  

---

#### **5. RNA-Seq 的应用**
🔬 **基因表达分析**：对不同组织、生长阶段、环境条件或疾病状态下的基因表达进行量化分析。  
🧬 **疾病研究**：用于癌症、神经退行性疾病、免疫疾病等的机制研究。  
🌱 **植物与动物育种**：筛选影响生长性状、抗逆性的关键基因。  
💊 **药物开发**：分析药物对基因表达的影响，筛选靶点基因。  
🦠 **微生物与病毒研究**：研究微生物群落、病毒感染机制和宿主响应。  

---

#### **6. RNA-Seq 与其他技术的对比**
| 方法 | 原理 | 适用场景 | 优势 | 劣势 |
|------|------|---------|------|------|
| **RNA-Seq** | 高通量测序 | 基因表达、可变剪切、新转录本 | 灵敏度高，全面 | 价格较高，数据分析复杂 |
| **qPCR** | 荧光定量PCR | 验证特定基因表达 | 灵敏度高，成本低 | 不能检测全转录组 |
| **微阵列** | 探针杂交 | 基因表达分析 | 成本低，成熟技术 | 需参考序列，检测范围有限 |

---

#### **7. 结论**
RNA-Seq 是目前最先进的转录组分析技术之一，广泛应用于**基因表达、疾病机制研究、生物育种和个体化医疗**等领域。随着**长读长测序（PacBio、Nanopore）**和**单细胞测序（scRNA-Seq）**技术的发展，RNA-Seq 将进一步提升我们对基因调控和细胞功能的理解。

-------


### **RNA-Seq 常见分析流程及软件/Pipeline 介绍**  

RNA-Seq 数据分析通常包括以下关键步骤，每个步骤都有相应的软件或 pipeline 可以使用。  

---

## **1. 原始数据质量控制（Quality Control, QC）**
### **目的**：检查测序数据质量，去除低质量 reads，提高后续分析准确性。  
### **常用软件**：
- **FastQC**（质量评估）：生成数据质量报告，查看碱基质量分布、GC 含量、接头污染等。  
- **Trimmomatic / Cutadapt**（去接头和低质量 reads）：去除测序接头、低质量 reads，提高比对效率。  
- **Fastp**（一体化 QC 工具）：自动完成去接头、低质量过滤，并提供可视化报告。  

**示例命令**（使用 FastQC 和 Trimmomatic）：  
```bash
fastqc raw_reads.fastq.gz -o qc_reports/
trimmomatic PE -phred33 input_R1.fastq.gz input_R2.fastq.gz \
output_R1_paired.fastq.gz output_R1_unpaired.fastq.gz \
output_R2_paired.fastq.gz output_R2_unpaired.fastq.gz \
ILLUMINACLIP:adapters.fa:2:30:10 LEADING:3 TRAILING:3 SLIDINGWINDOW:4:15 MINLEN:36
```

---

## **2. 比对（Mapping/Alignment）**
### **目的**：将 reads 比对到参考基因组，计算每个基因的表达量。  
### **常用软件**：
- **HISAT2**（基于 BWT 索引的快速比对工具，适用于人类、模式生物等基因组）。  
- **STAR**（使用基于 **Spliced Alignment** 的方法，比对速度快，适用于可变剪切研究）。  
- **Salmon / Kallisto**（基于伪比对的定量工具，速度快，不需要显式比对）。  

**示例命令**（使用 HISAT2）：  
```bash
hisat2 -p 8 -x genome_index -1 reads_R1.fastq.gz -2 reads_R2.fastq.gz -S output.sam
```

**示例命令**（使用 STAR）：  
```bash
STAR --runThreadN 8 --genomeDir genome_index \
--readFilesIn reads_R1.fastq.gz reads_R2.fastq.gz --readFilesCommand zcat \
--outSAMtype BAM SortedByCoordinate --outFileNamePrefix star_output
```

---

## **3. 转录本组装和基因表达定量**
### **目的**：计算每个基因的表达量，或进行转录本拼装。  
### **常用软件**：
- **FeatureCounts**（推荐用于基因表达定量）：从比对结果中提取 reads 计数。  
- **HTSeq-Count**（用于基因表达计数，适用于差异表达分析）。  
- **StringTie**（基因组转录本组装工具，适用于新转录本发现）。  
- **Salmon / Kallisto**（无比对定量工具，快速计算 FPKM/TPM）。  

**示例命令**（使用 FeatureCounts 进行基因表达定量）：  
```bash
featureCounts -T 8 -a annotation.gtf -o counts.txt aligned_reads.bam
```

**示例命令**（使用 Salmon 进行无比对定量）：  
```bash
salmon quant -i transcriptome_index -l A -1 reads_R1.fastq.gz -2 reads_R2.fastq.gz -o quant_output
```

---

## **4. 差异表达分析（Differential Expression Analysis, DEA）**
### **目的**：鉴定在不同条件下（如疾病 vs. 正常）的差异表达基因（DEGs）。  
### **常用 R 包/Pipeline**：
- **DESeq2**（基于负二项分布的标准化方法，适用于 RNA-Seq 数据差异表达分析）。  
- **EdgeR**（适用于小样本数据的差异表达分析）。  
- **limma-voom**（适用于 FPKM/TPM 数据的差异表达分析）。  

**示例 R 代码**（使用 DESeq2 进行差异表达分析）：  
```r
library(DESeq2)
countData <- read.table("counts.txt", header=TRUE, row.names=1)
colData <- data.frame(condition=c("Control", "Treatment"))
dds <- DESeqDataSetFromMatrix(countData, colData, design=~condition)
dds <- DESeq(dds)
res <- results(dds)
write.csv(res, "differential_expression_results.csv")
```

---

## **5. 功能富集分析（GO/KEGG Pathway Enrichment）**
### **目的**：分析差异表达基因（DEGs）涉及的生物学功能和信号通路。  
### **常用 R 包**：
- **ClusterProfiler**（GO 和 KEGG 通路富集分析）。  
- **GSEA（Gene Set Enrichment Analysis）**（基因集富集分析）。  

**示例 R 代码**（使用 ClusterProfiler 进行 GO 富集分析）：  
```r
library(clusterProfiler)
ego <- enrichGO(gene = DEG_list, OrgDb = org.Hs.eg.db, keyType = "SYMBOL", ont = "BP")
dotplot(ego, showCategory = 20)
```

---

## **6. 可变剪切分析（Alternative Splicing Analysis）**
### **目的**：检测不同条件下的可变剪切事件（如外显子跳跃、可变起始位点等）。  
### **常用软件**：
- **rMATS（RNA-Seq Multivariate Analysis of Transcript Splicing）**（检测可变剪切事件）。  
- **SUPPA**（计算转录本 isoform 使用情况）。  

**示例命令**（使用 rMATS 进行可变剪切分析）：  
```bash
rmats.py --b1 control.bam --b2 treatment.bam --gtf annotation.gtf -t paired --od output --tmp tmp
```

---

## **7. 基因融合检测（Fusion Gene Analysis）**
### **目的**：检测基因组重排导致的基因融合事件。  
### **常用软件**：
- **STAR-Fusion**（基于 STAR 比对的基因融合检测工具）。  
- **FusionCatcher**（高灵敏度检测基因融合）。  

**示例命令**（使用 STAR-Fusion）：  
```bash
STAR-Fusion --genome_lib_dir genome_lib --left_fq reads_R1.fastq.gz --right_fq reads_R2.fastq.gz --output_dir fusion_output
```

---

## **8. 单细胞 RNA-Seq 分析（Single-cell RNA-Seq, scRNA-Seq）**
### **目的**：解析单细胞水平的基因表达，研究细胞异质性。  
### **常用 R 包/Pipeline**：
- **Seurat**（用于 scRNA-Seq 数据分析和可视化）。  
- **Scanpy**（基于 Python 的单细胞分析工具）。  
- **Monocle**（用于单细胞发育轨迹分析）。  

**示例 R 代码**（使用 Seurat 进行 scRNA-Seq 分析）：  
```r
library(Seurat)
seurat_obj <- CreateSeuratObject(counts = data)
seurat_obj <- NormalizeData(seurat_obj)
seurat_obj <- FindVariableFeatures(seurat_obj)
seurat_obj <- RunPCA(seurat_obj)
DimPlot(seurat_obj, reduction = "pca")
```

---

## **总结**
RNA-Seq 数据分析涉及多个步骤，每个步骤都有不同的软件和 R 包可选。根据实验设计和研究目标，可以选择适合的工具。例如：
- **比对推荐 STAR 或 HISAT2**，无比对推荐 **Salmon/Kallisto**。
- **差异表达分析推荐 DESeq2 或 EdgeR**。
- **功能富集分析使用 ClusterProfiler**。
- **单细胞 RNA-Seq 可用 Seurat**。

这些软件和 pipeline 组成了一套完整的 RNA-Seq 数据分析流程，可用于**基础研究、疾病机制研究、育种及精准医疗**等方向。

---


## **有参转录组 vs. 无参转录组分析的区别**  

### **1. 概念介绍**
- **有参转录组（Reference-based RNA-Seq Analysis）**：将 RNA-Seq 数据比对到已知的参考基因组或参考转录组上，进行基因表达定量、差异表达分析和基因功能注释。  
- **无参转录组（De novo RNA-Seq Analysis）**：不依赖参考基因组，直接对 RNA-Seq 数据进行**组装（assembly）**，构建转录组序列，再进行基因表达分析。适用于**无基因组信息的非模式生物**。  

---

### **2. 工作流程**
| 步骤 | **有参转录组** | **无参转录组** |
|------|--------------|--------------|
| **数据质控** | 过滤低质量 reads，去除接头序列 | 过滤低质量 reads，去除接头序列 |
| **比对/组装** | 使用比对工具（如 HISAT2、STAR）将 reads 比对到参考基因组 | 使用**转录组组装工具**（如 Trinity、SPAdes）拼装转录本 |
| **基因表达定量** | 采用 FeatureCounts、HTSeq 统计 reads 覆盖度 | 采用 RSEM、Salmon 进行定量 |
| **差异表达分析** | 采用 DESeq2、EdgeR 进行差异表达分析 | 采用 DESeq2、EdgeR 进行差异表达分析 |
| **功能注释** | 参考已有数据库（GO、KEGG）进行注释 | 需用 BLAST 进行序列比对，再进行功能注释 |
| **可变剪切分析** | 参考已知外显子-内含子结构进行分析 | 不能直接进行，需要额外预测外显子结构 |
| **基因融合分析** | 可基于参考基因组分析基因融合事件 | 无基因组信息，无法直接分析基因融合 |
| **新基因发现** | 受限于参考基因组，难以发现新基因 | 适用于新物种研究，可发现新基因 |

---

### **3. 主要分析工具**
| **步骤** | **有参转录组工具** | **无参转录组工具** |
|----------|----------------|----------------|
| **比对** | HISAT2、STAR、Salmon | Trinity、SPAdes |
| **基因表达定量** | FeatureCounts、HTSeq、Salmon | RSEM、Salmon |
| **差异表达分析** | DESeq2、EdgeR | DESeq2、EdgeR |
| **功能注释** | Blast, KEGG, GO | Blast, KEGG, GO |
| **可变剪切分析** | rMATS, SUPPA2 | 需预测外显子结构 |

---

### **4. 适用场景**
✅ **有参转录组** 适用于：
- **模式生物（如人类、小鼠、水稻等）**，已有完整的参考基因组。  
- 需要**高精度基因表达定量**，如**药物研究、癌症基因分析**。  
- **可变剪切、基因融合、等位基因表达分析**，需要准确的外显子-内含子信息。  

✅ **无参转录组** 适用于：
- **非模式生物（无参考基因组）**，如**野生鱼类、新发现植物、微生物等**。  
- 需要**探索新基因、新转录本**，研究物种的**进化、适应性**等。  
- **新基因组研究的初步阶段**，在没有参考基因组时构建转录组参考数据。  

---

### **5. 优缺点对比**
| **分析方法** | **优点** | **缺点** |
|-------------|---------|---------|
| **有参转录组** | 计算速度快，结果准确，适合大规模样本分析 | 依赖参考基因组，可能忽略新基因 |
| **无参转录组** | 可用于**未知物种**，可发现新基因 | 计算量大，结果受组装质量影响，功能注释困难 |

---

### **6. 总结**
| **对比项** | **有参转录组** | **无参转录组** |
|------------|--------------|--------------|
| **适用物种** | 有完整基因组的物种 | 无基因组的非模式物种 |
| **分析速度** | 快，直接比对 | 慢，需要组装 |
| **新基因发现** | 受限于参考基因组 | 可发现新基因 |
| **计算复杂度** | 低 | 高，计算量大 |
| **基因表达定量** | 直接映射，结果精准 | 依赖组装质量，误差较大 |
| **功能注释** | 参考已有数据库 | 需要额外比对（BLAST） |

在**有参考基因组的情况下，推荐使用有参转录组**，分析精度更高；**对于无基因组的物种，建议使用无参转录组**，可发现新的基因信息。