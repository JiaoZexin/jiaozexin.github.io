---
layout: post
title:  "Publication_SV_Publication_Review"
date:   2025-03-03 13:00:00 +0000
categories: Publication
---

[Genetic variation across and within individuals, 2024](https://doi.org/10.1038/s41576-024-00709-x)

[Genome structural variation discovery and genotyping, 2011](https://doi.org/10.1038/nrg2958)

Comprehensive evaluation of structural variation detection algorithms for whole genome sequencing [2019 SVs tools](https://doi.org/10.1186/s13059-019-1720-5)

Evaluation of tools for identifying large copy number variations from ultra-low-coverage whole-genome sequencing data [2021 CNV Tools ](https://doi.org/10.1186/s12864-021-07686-z)


Comprehensive evaluation and characterisation of short read general-purpose structural variant calling software [Multy tools compare short read 多种Tools不能提高检测准确性 NC 2019](https://doi.org/10.1038/s41467-019-11146-4)

In it for the long run: perspectives on exploiting long-read sequencing in livestock for population scale studies of structural variants [2023 Genetic Selection Evolution Livestock SVs](https://doi.org/10.1186/s12711-023-00783-5)


Structural Variants and Speciation: Multiple Processes at Play [SVs influence reproductive isolation](https://doi.org/10.1101/cshperspect.a041446)

Optical genome mapping and revisiting short-read genome sequencing data reveal previously overlooked structural variants disrupting retinal disease−associated genes [Disease OGM 光学检测 2023](https://doi.org/10.1016/j.gim.2022.11.013) 

Current status of structural variation studies in plants [SVs in Plant 2021](https://doi.org/10.1111/pbi.13646)

The impact of structural variation on human gene expression [NG 2017 eQTL SVs](https://doi.org/10.1038/ng.3834)

---

### **Summary of "Comprehensive evaluation of structural variation detection algorithms for whole genome sequencing" (Approx. 200 Words)**  

Structural variations (SVs), including deletions, duplications, insertions, inversions, and translocations, significantly impact genome function and are associated with various diseases. Despite numerous SV detection algorithms, no single tool can detect all SV types with high precision and recall. This study comprehensively evaluates **69 SV detection algorithms** using **both simulated and real whole-genome sequencing (WGS) datasets**.  

Key findings include:  
- **Best-performing algorithms vary by SV type and size range**. **GRIDSS, Lumpy, SVseq2, SoftSV, Manta, and Wham** performed well for **deletions and duplications**, while **MELT, Mobster, and Tangram** were superior for mobile element insertions.  
- **Combining multiple algorithms improves accuracy**, but optimal pairings depend on SV type.  
- **Short-read and long-read sequencing methods yield different strengths**: Long-read approaches (e.g., **Sniffles and pbsv**) provide better accuracy for **large insertions and complex SVs**, while short-read tools excel at smaller variants.  
- **Precision-recall tradeoff**: Increasing recall often lowers precision, requiring careful selection of detection pipelines.  

This study underscores the importance of **choosing SV detection tools based on dataset characteristics and research objectives**, providing a guideline for improving SV analysis in **genomic medicine and evolutionary studies**.  

### **Chinese Translation (摘要翻译，约200字)**  

### **《全基因组测序中结构变异检测算法的全面评估》**  

结构变异（SVs）包括**缺失（DEL）、重复（DUP）、插入（INS）、倒位（INV）和易位（TRA）**，对基因组功能有重要影响，并与多种疾病相关。然而，当前的 SV 检测工具众多，**尚无单一算法能同时实现所有 SV 类型的高精度检测**。本研究对 **69 种 SV 检测算法** 进行了**系统评估**，使用**模拟数据和真实全基因组测序（WGS）数据**进行对比分析。  

**主要发现：**  
- **不同算法在检测特定 SV 类型时表现最佳**。**GRIDSS、Lumpy、SVseq2、SoftSV、Manta 和 Wham** 适用于**缺失和重复检测**，而 **MELT、Mobster 和 Tangram** 对 **移动元件插入** 具有更高灵敏度。  
- **多算法组合可提高准确性**，但最佳组合因 SV 类型而异。  
- **短读长 vs. 长读长测序方法**：长读长工具（如 **Sniffles 和 pbsv**）在**检测大插入和复杂 SV** 方面表现更优，而短读长工具更适合**小型变异**。  
- **精度与召回率的权衡**：提高召回率通常会降低精度，因此需要**优化检测策略**。  

本研究为 **SV 分析提供了实用指南**，可用于 **基因组医学和进化研究**，优化不同研究需求的 SV 检测策略。

---
### **Summary of "Evaluation of Tools for Identifying Large Copy Number Variations from Ultra-Low-Coverage Whole-Genome Sequencing Data" (Approx. 200 Words)**  

Copy number variations (CNVs) are large DNA deletions or amplifications that contribute to genetic diversity and disease susceptibility. Detecting CNVs from **ultra-low-coverage whole-genome sequencing (ULC-WGS)** data is challenging due to low sequencing depth (0.0005–0.8×). This study systematically evaluates six read-depth-based CNV detection tools: **BIC-seq2, Canvas, CNVnator, FREEC, HMMcopy, and QDNAseq** using **both simulated and real-world datasets**.  

### **Key Findings:**  
- All tools detected **large CNVs (>2 Mbp)** but struggled with smaller ones, producing false positives.  
- **BIC-seq2 performed best statistically but had the slowest runtime (~3 hours)**, whereas **FREEC was second-best and much faster (~3 minutes).**  
- **CNV detection in sex chromosomes varied significantly among tools**, with BIC-seq2 being the most reliable.  
- **Computational performance varied:** FREEC required the least memory, while Canvas had the highest usage.  
- **Optimal detection accuracy was achieved at ≥0.01× read coverage.**  

This study provides insights into selecting appropriate tools for **ULC-WGS CNV detection**, particularly in **noninvasive prenatal testing, cancer genomics, and stem cell research**, where sequencing cost and computational efficiency are major considerations.  

### **Chinese Translation (摘要翻译，约200字)**  

### **《超低覆盖度全基因组测序数据中大拷贝数变异检测工具的评估》**  

拷贝数变异（CNVs）是**大规模DNA缺失或扩增**，影响遗传多样性和疾病易感性。然而，**超低覆盖度全基因组测序（ULC-WGS, 0.0005–0.8×）** 由于测序深度低，CNV 检测具有挑战性。本研究系统评估了 **6 种基于读深度的 CNV 检测工具（BIC-seq2、Canvas、CNVnator、FREEC、HMMcopy 和 QDNAseq）**，并使用**模拟数据和真实数据**进行分析。  

### **主要发现：**  
- **所有工具可检测大 CNVs（>2 Mbp），但对小 CNVs 容易产生假阳性。**  
- **BIC-seq2 统计表现最佳，但运行最慢（约3小时），FREEC 次优且运行最快（约3分钟）。**  
- **不同工具在性染色体 CNV 检测上表现差异明显，BIC-seq2 可靠性最高。**  
- **FREEC 占用内存最低，而 Canvas 计算资源需求最高。**  
- **在 ≥0.01× 覆盖度时，检测准确率最佳。**  

本研究为 **ULC-WGS CNV 分析提供参考**，特别适用于 **无创产前检测、癌症基因组学、干细胞研究**，优化成本与计算效率。

---

### **Summary of "Comprehensive Evaluation and Characterisation of Short-Read General-Purpose Structural Variant Calling Software" (Approx. 300 Words)**  

Structural variants (SVs) play a significant role in genomic diversity and disease, yet their detection using **short-read sequencing** remains challenging due to sequencing and alignment artifacts. This study provides a **comprehensive benchmarking** of **10 general-purpose SV calling tools** using **high-quality reference cell lines and simulated data** to evaluate their **accuracy, sensitivity, and computational performance**.  

### **Key Findings:**  
- **Benchmarking 10 SV callers**, selected from over **40 tools**, representing different detection methods.  
- **Assembly-based tools (Manta, GRIDSS) performed best**, achieving high **sensitivity and precision**.  
- **Pure read-pair-based tools (e.g., BreakDancer) had poor performance**, especially on complex genomic regions.  
- **Simple ensemble calling does not consistently improve accuracy**, and no single ensemble outperformed the best individual caller.  
- **Genomic context affects SV detection**: callers struggled with **low-complexity and repeat regions**, leading to **higher false discovery rates**.  
- **Variant quality scores were not well-calibrated**, with **high read support not always indicating a true SV**.  

### **Conclusion:**  
The study highlights the **strengths and weaknesses** of different SV detection approaches, recommending **assembly-based methods** for **general-purpose SV detection**. It also provides **guidance for users and developers**, emphasizing **improved benchmarking practices, quality score calibration, and integration of multiple SV detection signals**.  


### **《短读长通用结构变异检测软件的综合评估与表征》摘要（约300字）**  

结构变异（SVs）在基因组多样性和疾病研究中起关键作用，但**短读长测序**的SV检测仍面临**测序和比对伪影**的挑战。本研究对**10种通用SV检测工具**进行了**全面基准测试**，使用**高质量参考细胞系和模拟数据**评估其**准确性、灵敏度和计算性能**。  

### **主要研究发现：**  
- 从**40多个工具**中筛选出**10种SV检测软件**，涵盖不同的检测方法。  
- **基于组装的方法（Manta、GRIDSS）表现最佳**，实现了**高灵敏度和准确性**。  
- **仅依赖成对比对（PE）的工具（如BreakDancer）性能较差**，尤其在**复杂基因组区域**。  
- **简单的多工具联合检测并未显著提升准确率**，最佳单工具的表现仍优于大多数联合策略。  
- **基因组背景影响SV检测**：在**低复杂度和重复区域**，检测工具的**假发现率较高**。  
- **变异质量评分存在偏差**，即使**高读长支持的SV也可能是错误变异**。  

### **研究结论：**  
本研究全面剖析了**不同SV检测方法的优劣**，推荐**基于组装的工具**作为**通用SV检测的首选**。研究还为**用户和开发者提供建议**，强调**改进基准测试方法、优化质量评分校准，以及整合多种SV检测信号**。


### **Summary of "In It for the Long Run: Perspectives on Exploiting Long-Read Sequencing in Livestock for Population-Scale Studies of Structural Variants" (Approx. 200 Words)**  

Structural variants (SVs) play a crucial role in **genomic diversity, evolution, and livestock breeding**, but their detection using **short-read sequencing** has been challenging. This review explores the **potential of long-read sequencing** to overcome these limitations, providing more accurate SV discovery and genotyping at the **population scale**.  

### **Key Findings:**  
- SVs **impact Mendelian traits and complex traits** in livestock but remain underexplored due to **technological and computational challenges**.  
- Short-read sequencing **struggles to detect large SVs**, particularly in **repetitive regions**, limiting its effectiveness.  
- Long-read sequencing technologies (e.g., **PacBio, ONT**) significantly improve **SV detection, phasing, and genotyping accuracy**.  
- A **global livestock SV sequencing consortium** is needed to generate large **population-scale SV datasets**, enhancing **genetic studies and breeding programs**.  
- Integrating **pangenome approaches, long-read sequencing, and short-read databases** can improve **SV discovery, imputation, and genomic selection**.  

### **Conclusion:**  
Long-read sequencing is **transforming livestock genomics**, enabling **comprehensive SV analysis**. Future research should focus on **expanding reference populations, improving bioinformatics tools, and integrating SVs into breeding programs** to enhance **livestock genetic improvement**.  

### **《长期视角：利用长读长测序进行牲畜种群规模结构变异研究》摘要（约200字）**  

结构变异（SVs）在**基因组多样性、进化及牲畜育种**中具有关键作用，但由于**短读长测序**的技术限制，SVs 研究面临挑战。本综述探讨了**长读长测序的潜力**，如何克服短读长测序的局限性，并提供更精确的**种群规模 SV 鉴定和基因分型**。  

### **主要发现：**  
- SVs **影响孟德尔性状和复杂性状**，但由于**技术和计算难题**，仍研究不足。  
- **短读长测序难以检测大规模 SVs**，尤其在**重复区域**，限制了其应用。  
- **长读长测序技术（PacBio, ONT）** 显著提高**SV 检测、单倍型解析及基因分型的准确性**。  
- 需建立**全球牲畜 SV 测序联盟**，生成**种群规模 SV 数据集**，推动**遗传研究和育种改良**。  
- **泛基因组方法、长读长测序与短读长数据库结合**，可提升**SV 发现、推算及基因组选择**的效率。  

### **研究结论：**  
**长读长测序正变革牲畜基因组学**，使**SV 研究更全面**。未来应聚焦**扩展参考种群、优化生物信息工具，并将 SVs 融入育种计划**，促进**牲畜遗传改良**。


---

### **Summary of "Structural Variants and Speciation: Multiple Processes at Play" (Approx. 100 Words)**  

This study explores the role of **structural variants (SVs)** in **speciation**, highlighting **chromosomal rearrangements, copy number variations (CNVs), and transposable elements (TEs)** as key factors in genetic divergence. SVs **reduce recombination, impact hybrid fitness, and shape reproductive isolation** by modifying genome architecture. Advances in **long-read sequencing** have revealed that **SVs are more common and influential than previously thought**, affecting **gene regulation, adaptation, and species formation**. The study emphasizes that **multiple evolutionary processes interact**, making SVs **critical drivers of speciation across taxa**.  


### **《结构变异与物种形成：多重进化过程的作用》摘要（约100字）**  

本研究探讨了 **结构变异（SVs）** 在 **物种形成** 中的作用，重点关注 **染色体重排、拷贝数变异（CNVs）和转座元件（TEs）** 对遗传分化的影响。SVs 通过 **减少重组、影响杂交个体适应性**，以及 **改变基因组结构** 促进生殖隔离。**长读长测序技术的进步** 揭示了 **SVs 远比之前认为的更常见且更具影响力**，影响 **基因调控、适应性进化和新物种形成**。研究强调 **多种进化机制协同作用**，使 SVs 成为 **驱动物种形成的关键遗传因素**。
---

### **Summary of "Optical genome mapping and revisiting short-read genome sequencing data reveal previously overlooked structural variants disrupting retinal disease-associated genes" (Approx. 100 Words)**  

This study investigates the role of **structural variants (SVs) in inherited retinal diseases (IRDs)** by using **optical genome mapping (OGM) and reanalyzing short-read genome sequencing data**. In a case of **USH2A-related disease**, OGM identified a **previously undetected 173 Mb pericentric inversion**, which was overlooked in initial sequencing. A reanalysis of **427 IRD cases** revealed **30 pathogenic SVs**, of which **>25% were previously missed**. This study highlights the importance of **improving SV detection protocols**, as SVs are **underestimated contributors** to **retinal diseases and missing heritability in genetic disorders**.  



### **《光学基因组测序与短读长基因组数据重分析揭示视网膜病相关基因的未检测结构变异》摘要（约100字）**  

本研究利用 **光学基因组测序（OGM）** 和 **短读长基因组数据重分析** 探讨 **结构变异（SVs）** 在 **遗传性视网膜病（IRDs）** 中的作用。在一例 **USH2A 相关疾病** 患者中，OGM 发现了 **此前未检测到的 173 Mb 染色体倒位**，该变异在初始测序中被忽略。对 **427 例 IRD 患者的重新分析** 发现了 **30 个致病性 SVs**，其中 **超过 25% 先前未被识别**。研究强调 **优化 SV 检测方法的重要性**，并指出 **SV 在视网膜疾病和遗传病中的贡献被低估**。


---

### **Summary of "Current Status of Structural Variation Studies in Plants" (Approx. 150 Words)**  

Structural variations (SVs) such as **gene presence/absence variations (PAVs) and copy number variations (CNVs)** play a significant role in plant genomic diversity and phenotypic variation. Unlike single nucleotide polymorphisms (SNPs), SVs can **cause gene loss, duplication, or novel gene formation**, leading to key agronomic traits. Early SV studies were limited by low-resolution technologies, but **long-read sequencing (PacBio, Nanopore), optical genome mapping, and Hi-C** have dramatically improved SV detection accuracy. High-quality **plant pangenome assemblies** have enabled better understanding of SVs, especially in polyploid species. SVs influence **crop evolution, domestication, and breeding**, with increasing evidence of their importance in traits such as **flowering time, disease resistance, and stress response**. The study highlights future challenges, including **refining computational tools, reducing false positives, and integrating SV data into breeding programs**.  

### **《植物结构变异研究的现状》摘要（约150字）**  

**结构变异（SVs）**，如 **基因存在/缺失变异（PAVs）和拷贝数变异（CNVs）**，在植物基因组多样性和表型变异中发挥重要作用。与 **单核苷酸多态性（SNPs）** 不同，SVs 可导致 **基因丢失、重复或新基因形成**，影响关键农艺性状。早期 SV 研究因低分辨率技术受限，但 **长读长测序（PacBio、Nanopore）、光学基因组测序和 Hi-C** 显著提高了检测精度。高质量的 **植物泛基因组组装** 促进了 SV 研究，特别是在 **多倍体植物** 中。SV 影响 **作物进化、驯化和育种**，并与 **开花时间、抗病性、环境适应性** 等性状密切相关。研究强调了未来挑战，包括 **优化计算工具、减少误报，以及将 SV 数据整合到育种计划中**。

---

### **Summary of "The Impact of Structural Variation on Human Gene Expression" (Approx. 150 Words)**  

This study investigates the **role of structural variations (SVs) in gene expression regulation**, using **deep whole-genome sequencing (WGS) and RNA-seq** from the GTEx project across **13 human tissues**. The authors identified **23,602 high-confidence SVs**, including deletions, duplications, and mobile element insertions. Through **cis-expression quantitative trait loci (cis-eQTL) mapping**, they found **SVs contribute to 3.5–6.8% of eQTLs**, a significantly larger fraction than previously estimated. Most **expression-altering SVs are noncoding**, enriched in enhancers and regulatory regions. Additionally, **rare SVs are strongly associated with gene expression outliers**, suggesting a substantial impact on human gene regulation. These findings highlight the importance of **SVs in genetic variation and gene expression**, emphasizing the need for **WGS-based approaches in genetic association studies and precision medicine**.  

### **《结构变异对人类基因表达的影响》摘要（约150字）**  

本研究探讨了 **结构变异（SVs）在基因表达调控中的作用**，基于 **GTEx 项目 13 种人类组织的深度全基因组测序（WGS）和 RNA-seq** 数据。研究人员鉴定了 **23,602 个高置信度 SVs**，包括 **缺失、重复和移动元件插入**。通过 **顺式表达数量性状位点（cis-eQTL）分析**，发现 **SVs 影响 3.5–6.8% 的 eQTLs**，这一比例显著高于以往估计。大多数 **影响基因表达的 SVs 为非编码变异，富集于增强子和调控区域**。此外，**罕见 SVs 与基因表达异常显著相关**，表明其对人类基因调控的重大影响。本研究强调了 **SVs 在遗传变异和基因表达中的重要性**，并突出了 **WGS 在基因组学研究和精准医学中的关键作用**。

---
