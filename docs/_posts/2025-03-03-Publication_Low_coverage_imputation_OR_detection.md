---
layout: post
title:  "Publication_Low_coverage_imputation_OR_detection"
date:   2025-03-03 13:00:00 +0000
categories: Publication
---

Rapid genotype imputation from sequence with reference panels: [QUILT](https://doi.org/10.1038/s41588-021-00877-0)

Efficient phasing and imputation of low-coverage sequencing data using large reference panels: [Glimpse](https://doi.org/10.1038/s41588-020-00756-0)

Imputation of low-coverage sequencing data from 150,119 UK Biobank genomes: [Glimpse2](https://doi.org/10.1038/s41588-023-01438-3)

Evaluating genotype imputation pipeline for ultra-low coverage ancient genomes 2020: [Low coverage pipeline](https://doi.org/10.1038/s41598-020-75387-w)

Imputation of ancient human genomes: [Using Glimpse 2023](https://doi.org/10.1038/s41467-023-39202-0)

Opening the Black Box of Imputation Software to Study the Impact of Reference Panel Composition on Performance [the Impact of Reference Panel Composition 2023](https://doi.org/10.3390/genes14020410)

High performance imputation of structural and single nucleotide variants in Atlantic salmon using low-coverage whole genome sequencing [Manu Glimpse 2023](https://doi.org/10.1101/2023.03.05.531147)

Whole-genome sequencing analysis of CNV using low-coverage and paired-end strategies is efficient and outperforms array-based CNV analysis [CNV array 2018](https://doi.org/10.1136/jmedgenet-2018-105272)

Detecting structural variations with precise breakpoints using low-depth WGS data from a single oxford nanopore MinION flowcell [SENSV for 4xONT 2022](https://doi.org/10.1038/s41598-022-08576-4) **HKU**

NanoVar: accurate characterization of patients’ genomic structural variants using low-depth nanopore sequencing [Low coverage nanopore SVs 2020](https://doi.org/10.1186/s13059-020-01968-7)


---

The publication presents **QUILT**, a novel method for rapid genotype imputation using low-coverage whole-genome sequencing (lcWGS) and large haplotype reference panels. QUILT applies **Gibbs sampling** to partition sequencing reads into maternal and paternal sets, allowing for efficient haploid imputation. It outperforms existing methods in imputation accuracy, especially for rare variants and diverse populations, and demonstrates high accuracy across multiple sequencing technologies, including Illumina short-read, Oxford Nanopore long-read, and haplotagging. Compared to genotyping microarrays, QUILT offers **higher accuracy at lower costs**, particularly in underrepresented populations. Additionally, it accurately imputes **human leukocyte antigen (HLA) types**, a first for lcWGS data.

---

The publication introduces **GLIMPSE**, a novel method for genotype imputation and haplotype phasing of **low-coverage whole-genome sequencing (lcWGS)** data using large reference panels. GLIMPSE significantly improves imputation accuracy across different population groups while reducing computational costs. It leverages the **Positional Burrows-Wheeler Transform (PBWT)** and an efficient **Gibbs sampling algorithm** to enhance performance. The method enables cost-effective genome-wide association studies (GWAS), outperforming traditional SNP arrays, especially in identifying rare variants. GLIMPSE is scalable, allowing for large datasets and accurate phasing, making **lcWGS a viable alternative to high-density genotyping arrays** for population and disease genetics.

---
The study introduces **GLIMPSE2**, an improved imputation method for **low-coverage whole-genome sequencing (lcWGS)**, leveraging the **150,119 UK Biobank (UKB) genomes** as a reference panel. It achieves **high accuracy, particularly for rare variants (MAF <0.1%)**, while significantly reducing computational costs. Compared to previous methods (GLIMPSE1, QUILT), GLIMPSE2 scales efficiently, imputing even very low-coverage samples (0.1×–0.5×) with greater accuracy. The study shows that **0.5× lcWGS imputation rivals or outperforms SNP arrays** in genome-wide association studies (GWAS). GLIMPSE2’s scalability makes **lcWGS a cost-effective alternative to SNP arrays**, with implications for diverse biobanks and ancestry studies.

---
The study evaluates a two-step **genotype imputation pipeline** for **ultra-low coverage (0.05–1×) ancient genomes** to improve the usability of degraded DNA. The pipeline first **updates genotype likelihoods** using Beagle and then **imputes missing genotypes** after filtering for confidence. This approach **outperforms traditional one-step imputation** methods, achieving **~90% accuracy for heterozygous common variants at 0.05× coverage** and **>97% accuracy at 0.5× coverage** in a Neolithic Hungarian genome. The study highlights the importance of **quality filtering, reference panel selection, and imputation tools** in mitigating reference bias and improving genotype accuracy in ancient DNA analysis.

---

### **Summary of "Imputation of Ancient Human Genomes" (Approx. 100 Words)**

Ancient DNA (aDNA) analysis faces challenges due to degradation and contamination, leading to low-coverage genomes that hinder accurate genotyping. This study evaluates genotype imputation as a solution, using **GLIMPSE** to impute 43 ancient genomes from different time periods and regions. Results show that imputation accuracy for ancient genomes is comparable to modern genomes, particularly for common variants. However, **African genomes and very ancient samples (>30,000 years old) exhibit higher error rates** due to reference panel limitations. Imputation preserves genetic clustering, PCA, and runs of homozygosity analyses, making it a reliable method for improving ancient genome studies with low-coverage data.

---

### **Summary of "Opening the Black Box of Imputation Software to Study the Impact of Reference Panel Composition on Performance" (Approx. 500 Words)**

Genotype imputation is a key method in genomic research, allowing for the estimation of missing genetic variants by comparing target individuals to a reference panel. The composition of this reference panel significantly affects imputation accuracy. While previous studies emphasize that reference panels closely matching the target population yield the best results, diverse panels that include multiple ancestries can also improve accuracy. This study systematically investigates how **reference panel diversity affects imputation performance** by tracking the contributions of individual haplotypes during the imputation process.

### **Key Findings:**
1. **Impact of Reference Panel Composition on Imputation Accuracy**
   - The study used **synthetic genetic variants** to track which reference haplotypes were contributing to imputation across different genomic regions.
   - While **a diverse reference panel generally improves accuracy**, it also introduces **false positive imputed genotypes**, especially in rare variants.

2. **Tracking Reference Panel Contributions**
   - The authors used a method called **imputation barcoding**, which inserts artificial single-nucleotide variants into the reference panel, enabling precise tracking of which haplotypes contribute to imputation.
   - This revealed that **more distant populations sometimes contribute to imputation, but not uniformly across the genome**.

3. **Balancing Diversity and Accuracy**
   - To optimize performance, the study introduced an **"informed choice" imputation strategy**, where each genomic region is imputed using **only the most relevant** reference haplotypes instead of an entire diverse panel.
   - This approach slightly **improved accuracy, particularly for rare variants**, while reducing the number of false-positive imputed genotypes.

4. **Evaluation Across Populations**
   - The study tested the approach on **admixed populations** from the **1000 Genomes Project**, particularly focusing on African (AFR), European (EUR), East Asian (EAS), South Asian (SAS), and American (AMR) groups.
   - Imputation accuracy varied among populations, with **MXL (Mexican) individuals benefiting the most from diverse reference panels**, while African and European ancestry individuals showed **less dependence on distant populations**.

5. **Comparison with Existing Imputation Methods**
   - The study compared two leading imputation software: **IMPUTE5 and MINIMAC4**.
   - **MINIMAC4 performed slightly better for rare variants**, whereas IMPUTE5 maintained higher accuracy for common variants.

### **Conclusion:**
This study provides **a deeper understanding of how reference panel diversity influences genotype imputation**. While diversity **generally improves accuracy**, it can also lead to incorrect imputations in certain cases. The proposed **informed choice** approach refines imputation by selectively using reference haplotypes **only where necessary**, striking a balance between **leveraging diversity and minimizing errors**. The findings are particularly relevant for **genome-wide association studies (GWAS) and biobank-scale genomic analyses**, where imputation plays a crucial role in expanding available genotype datasets.



### **Chinese Translation (摘要翻译，约500字)**

### **《揭开基因型插补软件的“黑箱”，探究参考面板组成对性能的影响》摘要**

基因型插补（Genotype Imputation）是基因组研究的重要工具，可通过参考数据库预测目标个体的缺失基因型。**参考面板的组成**对插补的准确性有重大影响。传统观点认为，**与目标群体相匹配的参考面板能提供最佳效果**，但也有研究指出，**多样化的参考面板可能进一步提升插补精度**。本研究采用创新方法，系统性分析了**参考面板的多样性如何影响插补表现**。

### **主要研究发现：**
1. **参考面板的多样性影响插补准确性**
   - 研究通过**合成基因变异**（Synthetic Variants）追踪哪些参考单倍型对插补有贡献。
   - **多样化的参考面板通常能提升准确度，但可能导致错误的基因型插补，特别是在稀有变异（Rare Variants）上。**

2. **追踪参考面板的贡献**
   - 研究引入了**插补条形码（Imputation Barcoding）**方法，在参考面板中**插入人工 SNP**，以精确追踪哪些单倍型贡献了插补数据。
   - 结果表明，**来自远缘人群的参考数据可能在某些基因区域有所贡献，但并不均匀**。

3. **优化插补策略：平衡多样性与准确性**
   - 研究提出**“知情选择”插补策略（Informed Choice Strategy）**，在不同基因组区域**仅使用最相关的参考单倍型**，而非整个多样化面板。
   - **该策略改善了稀有变异的插补准确性**，并减少了错误插补的发生。

4. **不同人群的插补表现**
   - 研究在**1000基因组计划（1000 Genomes Project）**中测试了该方法，特别关注**非洲（AFR）、欧洲（EUR）、东亚（EAS）、南亚（SAS）和美洲（AMR）**人群的插补表现。
   - **MXL（墨西哥）个体最受益于多样化参考面板**，而**非洲和欧洲人群的插补准确性对远缘人群的依赖性较低**。

5. **对比主流插补算法**
   - 研究对比了**IMPUTE5 和 MINIMAC4** 两种主流插补软件。
   - **MINIMAC4 在稀有变异上的表现稍优，而 IMPUTE5 在常见变异上的准确性更高**。

### **结论：**
本研究**深入解析了参考面板多样性对基因型插补的影响**。尽管**多样化参考面板通常提升插补准确性**，但在某些情况下可能会导致**错误的基因型预测**。**"知情选择"** 策略通过仅在必要时使用特定参考单倍型，使插补更加精准，减少错误预测。这些研究成果对**全基因组关联研究（GWAS）和生物银行规模的基因组分析**具有重要意义，帮助优化插补方法，提高基因组研究的可靠性和有效性。

---
### **Summary of "High-Performance Imputation of Structural and Single Nucleotide Variants in Atlantic Salmon Using Low-Coverage Whole Genome Sequencing" (Approx. 300 Words)**  

Whole-genome sequencing (WGS) is a powerful tool for genetic studies but remains expensive at high depths. **Genotype imputation**, which estimates missing variants using reference panels, offers a cost-effective alternative, especially for **low-coverage sequencing**. However, while imputation is well-established for single nucleotide variants (SNVs), its application to **structural variants (SVs)** remains underexplored.  

This study evaluates the feasibility of **joint SNV and SV imputation** in **Atlantic salmon (Salmo salar)** using **low-coverage WGS**. The researchers employed **GLIMPSE**, a leading imputation tool, to test performance at 1x–4x sequencing depths. A high-quality **reference panel** comprising **445 wild Atlantic salmon** was used for validation. Additional **15x WGS data from 20 commercial salmon** provided an independent test set.  

### **Key Findings:**  
1. **SNV Imputation:**  
   - Achieved **high accuracy (95%)** at even **1x coverage**, with recall improving at **higher sequencing depths**.  
   - Performance remained consistent even for commercial salmon outside the reference panel.  

2. **SV Imputation:**  
   - **Two approaches tested:** (i) based on linkage disequilibrium (LD) with SNVs and (ii) incorporating **SV genotype likelihoods (GLs)**.  
   - Using **SV GLs improved accuracy but reduced recall**, requiring **3x–4x coverage** for optimal results.  
   - At **1x WGS**, the model captured **84% of reference deletions with 87% accuracy**.  

### **Conclusion:**  
This study demonstrates that **low-coverage WGS combined with imputation can effectively recover SNVs and SVs**, offering a **cost-efficient strategy** for large-scale **genome-wide association studies (GWAS)** and **selective breeding programs**. Future improvements will focus on **enhancing SV reference panels and integrating long-read sequencing** for better structural variant characterization.  


### **Chinese Translation (摘要翻译，约300字)**  

### **《使用低覆盖度全基因组测序对大西洋鲑鱼的结构变异和单核苷酸变异进行高效插补》**  

全基因组测序（WGS）是遗传研究的重要工具，但高深度测序的成本较高。**基因型插补（Imputation）** 通过参考数据推测缺失变异，为 **低覆盖度测序** 提供了一种经济高效的替代方案。然而，尽管 **SNV（单核苷酸变异）** 插补技术较为成熟，其在 **结构变异（SVs）** 方面的应用仍然有限。  

本研究评估了 **大西洋鲑（Salmo salar）** 在 **低覆盖度 WGS** 条件下的 **SNV 和 SV 联合插补** 的可行性。研究人员使用 **GLIMPSE** 进行插补测试，覆盖深度为 **1x–4x**。**参考数据集** 包含 **445 只野生大西洋鲑鱼**，并利用 **20 只商业养殖鲑鱼的 15x WGS 数据** 进行独立验证。  

### **主要发现：**  
1. **SNV 插补：**  
   - 在 **1x 测序深度下已可达到 95% 的高准确度**，随着 **测序深度增加，召回率进一步提高**。  
   - 即使在参考数据之外的商业鲑鱼群体中，插补表现仍然稳定。  

2. **SV 插补：**  
   - **测试了两种方法：** (i) 仅依赖 SNVs 的 **连锁不平衡（LD）** 关系，(ii) **结合 SV 可能性（GLs）** 进行插补。  
   - **加入 SV GLs 可提高准确性，但降低召回率**，需 **3x–4x 覆盖度** 以获得最佳效果。  
   - 在 **1x WGS** 条件下，可 **捕获 84% 的参考数据集缺失变异，准确率为 87%**。  

### **结论：**  
本研究表明，**低覆盖度 WGS 结合插补技术可有效恢复 SNV 和 SV 信息**，为 **大规模基因组关联研究（GWAS）和水产育种** 提供了 **高效、低成本** 的策略。未来研究将着重 **优化 SV 参考数据集，并结合长读长测序**，以提高结构变异的检测精度。

---

### **Summary of "Whole-genome sequencing analysis of CNV using low-coverage and paired-end strategies is efficient and outperforms array-based CNV analysis" (Approx. 200 Words)**  

Copy number variation (CNV) analysis is crucial in genomics for understanding genetic diversity and disease mechanisms. Traditionally, **microarray-based CNV detection** has been the first-tier method in clinical cytogenetics. However, this study systematically evaluates the efficiency of **low-coverage whole-genome sequencing (WGS) with paired-end strategies** for CNV detection compared to arrays.  

### **Key Findings:**  
- **Low-coverage WGS (≥1×) detects significantly more CNVs** than array-based methods.  
- **Three WGS strategies were tested** (short-insert, 3 kb mate-pair, and 5 kb mate-pair) at **1×, 3×, and 5× coverages**, with benchmarking against **gold-standard CNVs** from the 1000 Genomes Project.  
- **WGS detected all seven deletions >100 kb** in NA12878 at 1× coverage, whereas **most arrays detected only one**.  
- **Paired-end strategies (mate-pair sequencing) improve CNV detection**, especially for large variants.  
- **15 Mb Cri-du-chat syndrome deletion was detected even at 1× coverage**, demonstrating clinical applicability.  

This study confirms that **low-coverage WGS is a cost-effective and more accurate alternative to arrays** for CNV detection, providing a powerful tool for clinical diagnostics and genomic research.  

### **Chinese Translation (摘要翻译，约200字)**  

### **《低覆盖度和成对末端测序策略在全基因组CNV分析中的应用：高效且优于芯片检测》**  

拷贝数变异（CNV）分析是研究**基因组多样性和疾病机制**的重要手段。传统上，**基因芯片**（microarray）是临床细胞遗传学中检测 CNV 的一线方法。本研究**系统评估了低覆盖度全基因组测序（WGS）结合成对末端测序**在 CNV 检测中的优势，并与芯片技术进行了对比。  

### **主要发现：**  
- **低覆盖度 WGS（≥1×）检测到的 CNV 远超芯片方法**。  
- **测试了三种 WGS 策略**（短插入片段、3 kb 连接子测序、5 kb 连接子测序），覆盖度分别为 **1×、3× 和 5×**，并与**1000基因组计划的金标准 CNV** 进行比对。  
- 在 NA12878 样本中，**WGS 在 1× 覆盖度下检测到所有 7 个 >100 kb 的缺失 CNV**，而**大多数芯片仅能检测 1 个**。  
- **成对末端策略（mate-pair sequencing）显著提高大 CNV 的检测能力**。  
- **Cri-du-chat 综合症的 15 Mb 缺失** 即使在 **1× 覆盖度下也能被检测**，表明其在临床诊断中的应用潜力。  

本研究表明，**低覆盖度 WGS 是一种更具成本效益且准确度更高的 CNV 检测方法**，可广泛应用于**临床遗传学和基因组研究**。

---

### **Summary of "Detecting Structural Variations with Precise Breakpoints Using Low-Depth WGS Data from a Single Oxford Nanopore MinION Flowcell" (Approx. 200 Words)**  

Structural variations (SVs) are major contributors to genetic disorders, but their detection using **low-depth whole-genome sequencing (WGS)** remains a challenge. This study demonstrates that **4× Oxford Nanopore Technologies (ONT) WGS** from a single **MinION flowcell** can efficiently detect pathogenic SVs with high sensitivity. The authors introduce **SENSV**, a novel SV detection tool designed to improve **sensitivity and breakpoint accuracy (±100 bp)** in low-coverage ONT data.  

### **Key Findings:**  
- **SENSV detected pathogenic SVs in 22 of 24 patient samples**, outperforming existing SV callers such as Sniffles, SVIM, and cuteSV.  
- **Accurate detection of deletions (>100 kbp), duplications, terminal deletions, and unbalanced translocations**, which other software often missed.  
- **Breakpoints were identified within ±100 bp**, allowing cost-effective **PCR validation**.  
- **Integration of sequencing depth analysis and realignment techniques** improved SV detection, reducing false positives.  
- **Benchmarking on real and simulated datasets** confirmed superior performance in **detecting long and complex SVs**.  

This study highlights the **cost-effectiveness and clinical applicability of low-depth ONT WGS for SV detection**, providing a **feasible alternative to high-depth sequencing for clinical diagnostics**.  


### **Chinese Translation (摘要翻译，约200字)**  

### **《使用单个 Oxford Nanopore MinION 流控芯片的低深度 WGS 数据精准检测结构变异》**  

结构变异（SVs）是遗传疾病的重要原因，但**低深度全基因组测序（WGS）** 的检测能力仍面临挑战。本研究表明，**4× Oxford Nanopore Technologies (ONT) WGS**（单个 MinION 流控芯片）可实现 **高灵敏度的致病性 SV 检测**。研究团队开发了**SENSV**，一种新型 SV 检测工具，可在 **低覆盖度 ONT 数据中提供 ±100 bp 的精确断点检测**。  

### **主要发现：**  
- **SENSV 成功检测 22 例患者中的 24 例致病性 SV**，表现优于 **Sniffles、SVIM 和 cuteSV** 等现有工具。  
- **准确检测 >100 kbp 缺失、重复、末端缺失和非平衡易位**，而这些变异常被其他软件遗漏。  
- **断点精度达 ±100 bp**，可用于 **PCR 低成本验证**。  
- **结合测序深度分析和重比对策略**，提高 SV 检测能力并减少假阳性。  
- **在真实和模拟数据集上的基准测试** 证实其在 **长片段和复杂 SV 识别** 方面的优势。  

本研究证明，**低深度 ONT WGS 可用于临床 SV 检测**，为 **高深度测序提供了一种经济高效的替代方案**，推动其在遗传疾病诊断中的应用。

---

### **Summary of "NanoVar: Accurate Characterization of Patients’ Genomic Structural Variants Using Low-Depth Nanopore Sequencing" (Approx. 150 Words)**  

Structural variants (SVs) are critical in genetic disorders, but detecting them accurately from **low-depth whole-genome sequencing (WGS)** is challenging. This study introduces **NanoVar**, a structural variant (SV) caller optimized for **Oxford Nanopore Technologies (ONT) low-depth WGS**. NanoVar combines **neural network-based algorithms** with long-read sequencing to improve **SV detection accuracy and breakpoint resolution**.  

### **Key Findings:**  
- **Outperforms existing SV callers (Sniffles, SVIM, Picky, NanoSV)** in **low-depth (4X) settings**, achieving **higher recall and precision**.  
- **Detected >14,000 SVs in acute myeloid leukemia (AML) patients**, with **100% PCR validation accuracy**.  
- **Identifies deletions, duplications, insertions, inversions, and translocations**, with **±100 bp breakpoint precision**.  
- **Computationally efficient**, reducing **runtime by 10× compared to other SV callers**.  

NanoVar proves that **low-depth ONT WGS is sufficient for accurate SV detection**, making it a **cost-effective solution for clinical genomics and disease research**.  

### **Chinese Translation (摘要翻译，约150字)**  

### **《NanoVar：利用低深度纳米孔测序精确表征患者基因组结构变异》**  

结构变异（SVs）在遗传病中具有重要作用，但在 **低深度全基因组测序（WGS）** 下检测这些变异仍然充满挑战。本研究提出 **NanoVar**，一种专为 **Oxford Nanopore Technologies（ONT）低深度 WGS** 优化的 SV 检测工具。NanoVar 结合 **神经网络算法** 和长读长测序，提高 **SV 检测的准确性和断点解析能力**。  

### **主要发现：**  
- **在低深度（4X）下优于现有 SV 检测工具（Sniffles、SVIM、Picky、NanoSV）**，召回率和精度更高。  
- **在急性髓系白血病（AML）患者中检测到 >14,000 个 SVs**，并通过 **PCR 验证 100% 准确**。  
- **可检测缺失、重复、插入、倒位和易位**，断点解析精度达 **±100 bp**。  
- **计算效率高**，比其他 SV 检测工具 **运行时间减少 10 倍**。  

本研究表明，**低深度 ONT WGS 可用于高精度 SV 检测**，为 **临床基因组学和疾病研究提供了经济高效的解决方案**。