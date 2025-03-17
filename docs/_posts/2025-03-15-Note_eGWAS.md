---
layout: post
title:  "Note_eGWAS"
date:   2025-03-15 13:15:00 +0000
categories: Note
---

### **eGWAS（Expression Genome-Wide Association Study, 基因表达全基因组关联研究）研究方法详解**

---

## **1. 什么是 eGWAS？**
**基因表达全基因组关联研究（Expression Genome-Wide Association Study, eGWAS）** 是 **结合基因型（Genotype）和转录组（Transcriptome）数据**，在全基因组范围内寻找能够**显著影响基因表达的遗传变异（如 SNPs 或 SVs）**的研究方法。

与 **GWAS（Genome-Wide Association Study, 全基因组关联研究）** 主要寻找与**表型（如疾病、农艺性状）**相关的遗传变异不同，**eGWAS 主要关注基因表达水平**，即：
- **哪些基因变异影响基因表达？**
- **基因表达如何影响复杂性状（如疾病、性状）？**

eGWAS 研究的目标是识别：
- **表达数量性状位点（eQTL, Expression Quantitative Trait Loci）**
- **调控变异（Regulatory Variants）**
- **关键转录因子（Transcription Factors, TFs）**
- **RNA 相关调控机制（如 miRNA, lncRNA）**

---

## **2. eGWAS 研究的基本流程**
### **✅ ① 样本选择与数据获取**
eGWAS 需要同时获取 **基因型（Genotype）和基因表达数据（Transcriptome）**，通常选取 **大规模人群或实验动物** 进行分析。

#### **🔹 样本要求**
- **群体规模**：样本数通常在 **数百到数千个个体**，以确保统计效能。
- **组织类型**：可以是 **特定组织（如脑组织、肝脏）** 或 **单细胞水平（scRNA-seq）**。
- **基因型数据**：
  - **全基因组测序（WGS）**，可检测 **SNPs、InDels 和 SVs**。
  - **SNP 基因分型芯片（Microarray）**，适用于大规模人群研究，但只能检测已知 SNPs。
- **RNA 表达数据**：
  - **RNA-seq（Bulk RNA-seq）**：常用于**整合 GWAS 数据**进行全基因组表达关联分析。
  - **单细胞 RNA-seq（scRNA-seq）**：可用于研究**细胞类型特异性表达调控**。

---

### **✅ ② 质量控制（QC）**
数据质量控制至关重要，包括基因型和 RNA 表达数据的过滤：
- **基因型数据 QC**
  - 去除 **低质量 SNPs/Indels**（缺失率高、测序深度不足）。
  - 进行 **种群结构校正（PCA / LD 剔除）**，防止假阳性。
- **RNA-seq 数据 QC**
  - 去除低表达基因（FPKM < 1）。
  - **批次效应校正（如 ComBat, SVA）**，消除样本间技术偏差。

---

### **✅ ③ eGWAS 关联分析**
eGWAS 的关键在于 **统计分析基因型与基因表达水平的相关性**，可采用 **单变量或多变量模型**。

#### **🔹 1. 线性回归模型（Linear Regression）**
适用于大多数 **SNP/eQTL 分析**：
\[
\text{Gene Expression} \sim \text{SNP} + \text{Covariates}
\]
示例：
```r
lm(expression ~ SNP + age + sex + batch, data)
```

#### **🔹 2. 混合效应模型（Linear Mixed Model, LMM）**
适用于**种群结构复杂的情况**（如 GWAS 队列）：
\[
\text{Gene Expression} \sim \text{SNP} + (1 | \text{Population})
\]
示例：
```r
lme4::lmer(expression ~ SNP + (1|population), data)
```

#### **🔹 3. 贝叶斯方法（Bayesian Methods）**
用于 **精细定位（fine-mapping）** 重要 eQTL 变异：
```r
library(BAYES)
bayes_eqtl(expression ~ SNP, data)
```

---

### **✅ ④ 结果校正（多重假设检验）**
由于 eGWAS 涉及 **全基因组数百万个 SNPs**，必须进行 **p 值校正**：
- **Benjamini-Hochberg（BH）FDR 校正**
  ```r
  p.adjust(pvalues, method = "BH")
  ```
- **Bonferroni 校正**
  ```r
  p.adjust(pvalues, method = "bonferroni")
  ```

---

### **✅ ⑤ 结果可视化**
- **曼哈顿图（Manhattan Plot）**：展示显著的 eQTL 变异：
  ```r
  qqman::manhattan(eGWAS_results)
  ```
- **火山图（Volcano Plot）**：展示显著 eGWAS 信号：
  ```r
  ggplot(data, aes(x=logFC, y=-log10(pvalue))) + geom_point()
  ```
- **染色质互作分析（Hi-C / ATAC-seq）**：结合 **表观基因组数据**，挖掘远端 eQTL（trans-eQTL）。

---

## **3. eGWAS vs. GWAS vs. eQTL 研究**
| **研究类型** | **目标** | **数据类型** | **输出结果** |
|-------------|---------|------------|------------|
| **GWAS** | 发现与 **性状/疾病** 相关的遗传变异 | 基因型 + 表型数据 | **SNP/Indel 关联性状** |
| **eQTL 分析** | 发现影响基因表达的遗传变异 | 基因型 + RNA 表达数据 | **SNP-基因表达 关联** |
| **eGWAS** | 结合 **GWAS + eQTL**，研究 **SNP 如何影响表型通过基因表达** | **基因型 + RNA-seq + 性状数据** | **调控性 SNP、调控通路、关键基因** |

---

## **4. eGWAS 的应用**
🧬 **人类疾病研究**
- 识别影响 **癌症、神经疾病（如阿尔茨海默病）** 的 **调控性遗传变异**。
- 例如，在 **自闭症研究中**，eGWAS 发现 **调控 GABA 受体的 SNPs 影响神经元发育**。

🌾 **作物育种**
- 在 **水稻、小麦等作物**，eGWAS 发现 **影响产量、抗病性、开花时间的调控变异**。
- 例如，在水稻研究中，eGWAS 发现 **OsSPL16 基因的 SNPs 影响籽粒大小**。

🐓 **动物遗传学**
- 研究 **家禽、牲畜** 的 **生长、繁殖和行为性状**。
- 例如，在鸡羽毛啄食行为研究中，eGWAS 发现 **GABA 受体基因的调控 SNPs 影响啄食行为**。

---

## **5. 结论**
**eGWAS（基因表达全基因组关联研究）** 是 **整合基因型、RNA 表达和表型数据** 的重要方法，可解析 **基因表达如何影响性状或疾病**。eGWAS 结合 **GWAS 和 eQTL** 研究，为 **精准医学、农业育种、疾病遗传学** 提供了关键工具，未来结合 **单细胞测序（scRNA-seq）、机器学习** 等技术，将进一步提升解析能力。