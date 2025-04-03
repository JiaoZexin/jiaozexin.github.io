---
layout: post
title:  "Note_Admixture_LD"
date:   2025-04-03 21:55:00 +0000
categories: Note
---

The spatial scale of dispersal revealed by admixture tracts [Doi](https://doi.org/10.1111/eva.12829)

The contribution of ancient admixture to reproductive isolation between European sea bass lineages[Doi](https://doi.org/10.1002/evl3.169)

**Nucleotide diversity（核苷酸多样性）** 是一种常用的 **衡量种群遗传多样性** 的指标，反映的是一个种群中任意两个个体在某一段DNA序列上的平均差异程度。

---

### 一、定义

用数学表达是这样的：

\[
\pi = \sum_{i=1}^{n} \sum_{j=i+1}^{n} \frac{d_{ij}}{\binom{n}{2}}
\]

其中：
- \( n \) 是样本个体数，
- \( d_{ij} \) 是第 \( i \) 个和第 \( j \) 个个体在该序列上碱基的差异数，
- \( \binom{n}{2} \) 是所有可能的两两组合数。

简单来说，就是 **所有样本的两两组合之间 DNA 序列的平均差异（单位一般是每个碱基位点）**。

---

### 二、通俗理解

假设你有 5 条染色体上的某段序列，然后把它们两两比对，统计差异位点的个数，最后算个平均值，这个值就是 nucleotide diversity（通常记作 π）。

它高意味着：
- 这个种群 **遗传多样性高**，
- 可能经历了长期的有效群体数量较大或基因流频繁。

它低可能说明：
- 群体经历了瓶颈、近交、选择清除等事件。

---

### 三、与其它指标对比

| 指标 | 含义 | 适用情况 |
|------|------|---------|
| π（nucleotide diversity） | 任意两条序列的平均差异 | 关注序列变异强度 |
| θ（Watterson’s estimator） | 基于SNP数目的估计 | 关注变异数量 |
| Tajima’s D | 比较 π 和 θ 的差异 | 检测选择或人口历史事件 |

---

### 四、举个例子

如果在某鱼类种群的一段基因区域中，π = 0.003，意味着每1000个碱基平均有3个差异位点。

---

### 五、在你的研究中

如果你在研究不同鱼类（如罗非鱼、加州鲈等）之间的群体结构或选择信号，nucleotide diversity 可以帮你：
- 判断某区域是否经历了选择（如选择会降低多样性）；
- 比较不同群体之间的遗传差异；
- 和SV密度或功能变异做整合分析，看是否存在功能区域多样性降低等现象。

---

要不要我给你一段代码来计算它，比如用VCF文件和 `vcftools` 或 `popgen` 包？