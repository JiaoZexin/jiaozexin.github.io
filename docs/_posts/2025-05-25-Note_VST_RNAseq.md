---
layout: post
title:  "Note_VST_RNAseq"
date:   2025-05-25 00:34:00 +0000
categories: Note
---


[查看 PDF 文件 deseq2](../../pdf/20250525_RNA_seq_deseq2.pdf)

[查看 PDF 文件 normalization](../../pdf/20250525_RNA_seq_normalization.pdf)

**Variance Stabilizing Transformation (VST)** 是一种用于 **RNA-seq 数据预处理** 的方法，主要用于 **稳定不同表达水平下的方差**，从而更好地进行下游分析（如 PCA、聚类、可视化等）。它通常由 DESeq2 包中的 `vst()` 函数实现。

---

### 🧬 什么是 VST？

RNA-seq 数据通常以原始的 read counts 形式表示。由于 count 数据是离散的并呈 **负二项分布**，其方差随着基因表达水平增加而变大，即 **方差依赖于均值**（mean-dependent variance）。这种特性会影响下游分析的表现，例如主成分分析（PCA）和聚类，因为这些分析假设数据的方差是均一的。

**VST 的目标是通过数学变换消除这种依赖关系，使得基因在不同表达水平下的方差趋于稳定。**

---

### 🔧 实现方法（DESeq2 中的做法）

在 `DESeq2` 中，使用 `vst()` 或 `varianceStabilizingTransformation()` 函数对原始 count 矩阵进行变换。示例代码如下：

```r
library(DESeq2)
dds <- DESeqDataSetFromMatrix(countData = count_matrix,
                              colData = sample_info,
                              design = ~ condition)

dds <- estimateSizeFactors(dds)
vsd <- vst(dds, blind = TRUE)  # blind=TRUE 表示不考虑分组信息进行变换
```

变换后的数据保存在 `assay(vsd)` 中，可以直接用于：

* 主成分分析（PCA）
* 聚类分析（heatmap）
* 可视化（如 ggplot）

---

### ✅ VST 的特点

| 特性        | 说明                                 |
| --------- | ---------------------------------- |
| 方差稳定      | 减少高表达基因的主导效应                       |
| 更接近正态分布   | 使得数据更适合 PCA 和距离度量                  |
| 不适合差异表达分析 | 差异表达分析应使用原始 count 或通过 `DESeq()` 分析 |

---

### 🆚 与 log2 转换的区别

虽然 log2(count + 1) 转换也可用于稳定变异，但它对于低表达基因的表现较差，且在 count 接近 0 时非常敏感。

| 方法              | 稳定性 | 处理低表达 |
| --------------- | --- | ----- |
| log2(count + 1) | 一般  | 差     |
| VST / rlog      | 更稳定 | 更好    |

---

### 总结一句话

**VST 是一种将 count 数据标准化并稳定其方差的变换方法，有助于后续的无监督分析（如 PCA 和聚类），但不应用于差异表达统计分析。**



----

在 RNA-seq 分析中，**TPM（Transcripts Per Million）** 是一种常用的基因表达量标准化方法，用于解决不同基因长度和测序深度对表达量估计的影响。

---

### 🧬 什么是 TPM？

**TPM（每百万转录本中的转录本数）** 是一种将原始 read count 数据归一化后得到的相对表达量单位。其目的是使得**不同基因之间、不同样本之间**的表达量可以直接进行比较。

---

### 🔢 TPM 的计算流程

TPM 的计算包括两个主要步骤：

#### **1. 先根据基因长度标准化：**

对于每个基因，先计算 RPK（Reads Per Kilobase）：

$$
\text{RPK}_i = \frac{\text{Raw counts}_i}{\text{Gene length}_i \, (\text{in kilobases})}
$$

#### **2. 然后按每百万归一化：**

$$
\text{TPM}_i = \frac{\text{RPK}_i}{\sum_j \text{RPK}_j} \times 10^6
$$

与 FPKM/RPKM 不同，TPM 在进行长度标准化后，会将所有基因的 RPK 加总再标准化，因此：

* **TPM 总和为一百万**，使得不同样本之间可直接比较；
* **TPM 比 FPKM 更具可比性**。

---

### ✅ TPM 的优点

| 优点      | 说明                    |
| ------- | --------------------- |
| 跨样本可比性好 | 总和固定为 1,000,000       |
| 考虑基因长度  | 准确反映实际表达水平            |
| 易于可视化   | 特别适合用于 heatmap、表达分布图等 |

---

### 🧭 什么时候用 TPM？

TPM 常用于以下情境：

* 可视化表达水平（如热图、条形图）
* 比较不同样本之间某个基因的表达差异
* 构建共表达网络或表达谱聚类分析

⚠️ 注意：**TPM 不适合用于差异表达分析**（如 DESeq2 或 edgeR），因为它是归一化后的连续数值，不保留 count 的离散性。

---

### 🆚 TPM vs FPKM vs Raw Counts

| 方法         | 是否考虑基因长度 | 是否可用于差异表达分析      | 是否样本间可比    |
| ---------- | -------- | ---------------- | ---------- |
| Raw Counts | ❌        | ✅（DESeq2, edgeR） | ❌          |
| FPKM       | ✅        | ❌                | ❌（归一化顺序不同） |
| TPM        | ✅        | ❌                | ✅（总和固定）    |

---

### 示例：TPM 计算伪代码

```r
# 读取原始 counts 和基因长度（单位：bp）
counts <- read.table("counts.txt")
gene_length_kb <- gene_length_bp / 1000

# Step 1: 计算 RPK
rpk <- counts / gene_length_kb

# Step 2: 计算每个样本的 RPK 总和
rpk_sum <- colSums(rpk)

# Step 3: 计算 TPM
tpm <- t( t(rpk) / rpk_sum ) * 1e6
```

---

### 总结一句话：

**TPM 是一种经过基因长度和测序深度标准化的 RNA-seq 表达量度量方式，适合样本间和基因间的表达量可视化和比较，但不适合用于差异表达分析。**

