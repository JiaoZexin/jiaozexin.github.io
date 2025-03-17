---
layout: post
title:  "Tutorial_KAGE2"
date:   2025-03-03 21:00:00 +0000
categories: Tutorial
---

[KAGE 2: Fast and accurate genotyping of structural variation using pangenomes](https://doi.org/10.1101/2023.12.23.572333)

[KAGE2](https://github.com/kage-genotyper/kage/) 是一种高效的无比对（alignment-free）基因分型工具，专门用于从短基因组读取中分型单核苷酸多态性（SNPs）和小的插入缺失变异（indels）。 citeturn0search0

**主要特性：**

- **结构变异分型**：在 2023 年 12 月发布的 KAGE2 版本中，增加了对结构变异（SV）分型的支持。 citeturn0search0

- **与 GLIMPSE 集成**：KAGE2 现已直接集成了 GLIMPSE，这是一种基因组插补工具。通过这种集成，KAGE2 的分型准确性得到了显著提升，尤其是在处理结构变异时。 citeturn0search0

- **GPU 加速**：从版本 0.1.11 开始，KAGE2 支持 GPU 加速（称为 GKAGE）。在仅有 4 GB 显存的 GPU 上，KAGE2 能够在几分钟内完成对人类样本的分型。 citeturn0search0

**安装与使用：**

KAGE2 需要 Python 3 环境，已在 3.8、3.9 和 3.10 版本上进行了测试。可以通过以下命令安装：


```bash
pip install kage-genotyper
```


安装完成后，可以运行以下命令测试安装是否成功：


```bash
kage test
```


这将对一些示例数据进行分型，并应在没有错误的情况下完成。 citeturn0search0

有关 KAGE2 的更多信息和使用指南，请参阅其 GitHub 仓库。 citeturn0search0 

---

### **Summary of the Paper: "KAGE 2: Fast and Accurate Genotyping of Structural Variation Using Pangenomes"**

Structural variations (SVs) play a crucial role in genetic diversity and disease regulation, yet their accurate detection remains challenging. Traditional short-read sequencing methods often struggle with SV detection due to mapping issues. Long-read sequencing offers a solution but is expensive. The emergence of **pangenomes**, which incorporate genetic variation across populations, presents a cost-effective alternative for genotyping SVs.

**KAGE2** is a novel tool designed for **fast and accurate genotyping of structural variations using pangenomes**. Unlike previous methods that rely on alignment to a linear reference genome, KAGE2 uses a k-mer-based approach, leveraging known SVs in the pangenome. This allows for efficient and reference-bias-free genotyping of SVs using short-read sequencing.

### **Key Contributions:**
1. **Accuracy & Speed**: Benchmarking results show that KAGE2 outperforms existing genotypers like **PanGenie** and **Bayestyper**, achieving higher accuracy across different sequencing depths and genomic regions.
2. **Scalability**: Unlike PanGenie, whose runtime scales quadratically with pangenome size, KAGE2 remains computationally efficient regardless of the pangenome's growth.
3. **Integration with GLIMPSE**: KAGE2 incorporates GLIMPSE for improved variant imputation, significantly enhancing genotyping accuracy, especially at low sequencing coverages.
4. **Performance Across Variant Types**: KAGE2 consistently achieves the highest accuracy for deletions, insertions, and across diverse genomic regions.
5. **Pangenome Size Effect**: Larger pangenomes improve recall but may reduce precision. KAGE2’s design ensures optimal performance as pangenome datasets expand.

### **Conclusion:**
KAGE2 is a **fast, accurate, and scalable** tool for genotyping structural variations using pangenomes. Its ability to efficiently handle growing pangenomes makes it an essential tool for future genomic studies. With the continued expansion of human and non-human pangenomes, KAGE2 provides a robust solution for **cost-effective SV detection using short-read sequencing**.

---

### **Chinese Translation (摘要翻译)**

**KAGE 2：基于泛基因组的快速准确结构变异分型工具**

结构变异（SVs）在基因组多样性和疾病调控中起着重要作用，但其准确检测仍然是一个挑战。传统的短读测序方法由于比对问题，在检测结构变异方面存在局限，而长读测序虽然精确，但成本较高。**泛基因组（Pangenome）**的出现提供了一种**成本效益更高的结构变异分型方法**，它整合了群体的遗传变异信息。

**KAGE2** 是一种**利用泛基因组进行快速准确的结构变异分型的新工具**。不同于依赖线性参考基因组比对的传统方法，KAGE2 采用 **k-mer** 计算策略，直接基于泛基因组中已知的结构变异进行分型，从而避免参考基因组偏倚，提升短读测序的分型精度。

### **主要贡献：**
1. **高精度和高速度**：在基准测试中，KAGE2 在各种测序深度和基因组区域的分型准确性均优于 **PanGenie** 和 **Bayestyper**。
2. **计算效率高**：与 PanGenie 计算复杂度随泛基因组大小呈二次增长不同，KAGE2 在更大的泛基因组数据集上仍然保持高效运行。
3. **GLIMPSE 插补优化**：KAGE2 集成 **GLIMPSE** 进行基因型插补（Imputation），在低测序深度（0.5-2x）时仍能保持高准确率。
4. **适用于不同类型的变异**：在插入、缺失及不同基因组区域，KAGE2 始终表现出最佳的分型准确性。
5. **泛基因组大小的影响**：更大的泛基因组可以提高召回率，但可能降低精度。KAGE2 设计能够在泛基因组规模扩大时保持优良性能。

### **结论：**
KAGE2 是一种 **高效、精准、可扩展的结构变异分型工具**，它能够利用短读测序数据，结合泛基因组进行成本效益高的 SV 检测。随着人类和其他物种泛基因组数据的增长，KAGE2 将成为未来基因组学研究的重要工具。