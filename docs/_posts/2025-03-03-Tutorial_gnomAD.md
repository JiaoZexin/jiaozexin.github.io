---
layout: post
title:  "Tutorial_gnomAD"
date:   2025-03-03 13:45:00 +0000
categories: Tutorial
---

[SV in gnomAD](https://gnomad.broadinstitute.org/news/2019-03-structural-variants-in-gnomad/)

### **gnomAD（Genome Aggregation Database）简介**

#### **1. 什么是 gnomAD？**
**gnomAD（Genome Aggregation Database）** 是一个**全球最大的人类基因组变异数据库**，用于存储和分析来自不同人群的大规模基因组数据。该数据库由**Broad Institute** 领导，旨在提供高质量的**单核苷酸变异（SNPs）** 和 **结构变异（SVs）** 数据，以支持人类遗传学、群体遗传学、临床遗传学和疾病研究。

---

#### **2. gnomAD 的发展历程**
gnomAD 继承并扩展了**ExAC（Exome Aggregation Consortium）**：
- **ExAC（2014-2016）**：
  - 仅包含**外显子组数据**（exome sequencing data）。
  - 约 **6 万个个体** 的数据。
- **gnomAD v2（2018）**：
  - 包含 **全基因组（WGS）+ 外显子组（WES）** 数据。
  - 约 **14 万个个体**（12.5 万 WES + 1.5 万 WGS）。
- **gnomAD v3（2020）**：
  - 仅包含**全基因组测序（WGS）** 数据。
  - 约 **7 万个个体**，基于**GRCh38 参考基因组**。

最新版本的 gnomAD 仍在不断更新，并整合了**结构变异（SVs）** 和**等位基因频率（AF）** 以帮助研究罕见和常见遗传变异。

---

#### **3. gnomAD 包含的数据**
gnomAD 提供以下关键数据：
1. **单核苷酸变异（SNPs）和小插入/缺失（Indels）**：
   - 覆盖全基因组和外显子组。
   - 包含**等位基因频率（AF）、等位基因计数（AC）、个体计数（AN）** 等信息。
   
2. **结构变异（SVs）**：
   - gnomAD v2 提供了 **443,000+ 结构变异**，包括**缺失（deletions）、插入（insertions）、重复（duplications）和倒位（inversions）**。
   - 可用于研究基因拷贝数变异（CNVs）等。

3. **群体遗传学数据**：
   - 覆盖多种人群，如欧洲人、非洲人、南亚人、东亚人、美洲印第安人、阿什肯纳兹犹太人等。
   - 提供**人群特异性等位基因频率**，支持疾病研究和 GWAS 研究。

4. **功能影响预测**：
   - 使用**VEP（Variant Effect Predictor）** 进行注释，提供变异的**基因功能影响**（如同义突变、错义突变、无义突变等）。

---

#### **4. gnomAD 的应用**
gnomAD 在多个领域有广泛应用，包括：

### **(1) 罕见病和遗传病研究**
- 研究 **致病性突变的等位基因频率**，帮助识别罕见遗传病变异。
- 临床研究中可用于**过滤普通人群中的变异，以确定可能的致病突变**。

### **(2) GWAS 研究**
- 作为 **背景等位基因频率数据库**，用于筛选 GWAS 研究中的候选变异。
- 研究 **多基因性状（polygenic traits）** 相关变异。

### **(3) 结构变异研究**
- gnomAD-SV 数据集可用于分析不同人群中的**大规模结构变异**，如拷贝数变异（CNVs）。
- 这些数据对于**癌症研究、精神疾病研究、罕见病研究** 具有重要意义。

### **(4) 群体遗传学分析**
- 研究不同人群的基因变异模式、**遗传漂变（genetic drift）** 和**自然选择（natural selection）** 过程。

---

#### **5. 如何使用 gnomAD？**
gnomAD 提供了**网页查询和 API**，方便用户检索和分析数据。

### **(1) 在线查询**
官网：[https://gnomad.broadinstitute.org](https://gnomad.broadinstitute.org)

用户可以通过基因或变异搜索：
- 在搜索框输入 **rsID**（如 rs123456）。
- 输入基因名称（如 BRCA1）。
- 直接搜索染色体位置（如 `chr1:1234567-1234568`）。

### **(2) API 访问**
gnomAD 允许用户通过 Python API 访问数据：
```python
import requests

url = "https://gnomad.broadinstitute.org/api/variant/1-55516888-G-A"
response = requests.get(url)
data = response.json()
print(data)
```
这个 API 查询 **染色体 1 上位置 55516888 的 G>A 变异**，返回其等位基因频率等信息。

### **(3) 下载数据**
gnomAD 还提供**VCF 文件**供本地分析：
- [https://gnomad.broadinstitute.org/downloads](https://gnomad.broadinstitute.org/downloads)

---

#### **6. gnomAD 的局限性**
尽管 gnomAD 是一个极具价值的数据库，但仍存在以下局限：
1. **不包含所有人群**：
   - 尽管数据覆盖多个种群，但某些群体（如非洲以外的少数民族）仍然数据不足。
   
2. **不包含疾病患者数据**：
   - gnomAD 主要用于**健康人群**，并未包含大规模的疾病患者数据，限制了其在疾病突变研究中的直接应用。

3. **低覆盖度的 WGS 数据**：
   - gnomAD v3 仅包含 WGS 数据，但其测序深度较低（~30×），某些低频变异可能无法准确检测。

4. **基因组结构变异仍需进一步完善**：
   - 尽管 gnomAD-SV 版本提供了**结构变异**信息，但相较于 SNP 数据，**结构变异的数据质量和检测能力仍在不断改进**。

---

### **7. 总结**
✅ **gnomAD 是全球最大的人类基因组变异数据库**，用于**研究基因变异的频率、人群分布和功能影响**。  
✅ **广泛应用于罕见病、GWAS、群体遗传学和基因组医学研究**。  
✅ **支持在线查询、API 访问和本地数据分析**，可用于变异筛选和功能注释。  
❌ **不包含所有人群，主要基于健康个体，不适用于直接分析疾病数据**。  
❌ **结构变异（SVs）数据仍需进一步改进**。

如果你正在研究**人类基因组变异或基因组关联研究**，gnomAD 是一个**不可或缺的资源**！

你是否希望获取某个具体基因或变异的信息？我可以帮助你查询 gnomAD 数据！