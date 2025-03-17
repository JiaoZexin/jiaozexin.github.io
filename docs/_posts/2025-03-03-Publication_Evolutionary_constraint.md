---
layout: post
title:  "Publication_Evolutionary_constraint"
date:   2025-03-03 20:10:00 +0000
categories: Publication
---

### **Summary (English)**  
This study leverages **mammalian evolutionary constraint** to improve the identification of **functionally important genetic variants** related to **human disease and complex traits**. By analyzing **240 placental mammal genomes**, the researchers identified **3.3% of the human genome as highly constrained**, with **80.7% of these regions being noncoding**. These constrained regions were found to be **enriched for disease-associated single-nucleotide polymorphisms (SNPs)**, highlighting their importance in **genetic heritability and phenotypic variation**.  

The study demonstrates that evolutionary constraint—measured as **base-pair conservation across mammals**—is a **powerful predictor of functional importance**, independent of cell type or developmental stage. The researchers compared constrained regions to **genome-wide association study (GWAS) results**, expression quantitative trait loci (eQTL), and clinical variant databases such as ClinVar. Their findings show that **pathogenic variants in ClinVar are significantly more constrained than benign variants**, confirming the functional importance of constrained bases in human health and disease.  

One key application of this evolutionary constraint approach is its integration into **fine-mapping techniques for GWAS loci**. The study finds that incorporating **constraint scores significantly improves the identification of causal disease variants**. The enrichment of disease heritability in constrained regions was found to be **greater than in nonsynonymous coding variants or fine-mapped eQTL SNPs**, emphasizing the **relevance of evolutionary constraint in noncoding regions**.  

Additionally, the study highlights the importance of **structural variations (SVs)** and **copy-number variants (CNVs)** in constrained genomic regions. CNVs overlapping constrained regions were associated with increased disease risk, particularly in **schizophrenia-related genomic regions**. The researchers also applied their method to **cancer genomics**, showing that **noncoding constrained mutations (NCCMs) in brain tumors, such as medulloblastomas, can identify novel candidate driver genes**.  

Another major contribution of this research is its application to **polygenic risk scores (PRS)**. The study demonstrates that evolutionary constraint can improve **PRS accuracy across multiple human diseases and traits**, enhancing the prediction of genetic risk for individuals. Variants in constrained regions contribute disproportionately to **the predictive power of PRS models**, indicating their **biological relevance** in disease risk assessment.  

Overall, this study provides a **genome-wide measure of evolutionary constraint** that enhances the identification of **functionally important genetic variants**. By integrating **comparative genomics, GWAS, fine-mapping, and PRS**, the findings significantly advance our ability to **prioritize disease-associated variants, understand genetic heritability, and inform therapeutic development**.  

---

### **摘要 (Chinese)**  
本研究利用**哺乳动物进化约束**方法，改进对**人类疾病和复杂性状相关功能性遗传变异**的识别。通过分析**240种胎盘哺乳动物的基因组**，研究人员发现**人类基因组中3.3%的区域受到高度进化约束**，其中**80.7%为非编码区域**。这些受约束的区域**富含疾病相关的单核苷酸多态性（SNPs）**，表明它们在**遗传力和表型变异**中发挥着重要作用。  

研究表明，**通过哺乳动物基因组比对计算的碱基对进化约束**，可作为**功能重要性的强大预测指标**，不依赖于特定细胞类型或发育阶段。研究人员将这些受约束区域与**全基因组关联研究（GWAS）**、**表达数量性状位点（eQTL）**和**临床变异数据库（ClinVar）**进行比对，发现**ClinVar数据库中的致病变异比良性变异更加受约束**，进一步验证了这些碱基对在**人类健康和疾病中的功能重要性**。  

本研究的一个关键应用是**改进GWAS位点的精细定位（fine-mapping）**。结果表明，结合**进化约束评分**可以**显著提高疾病因果变异的识别率**。研究发现，受约束区域中的**疾病遗传力富集程度**甚至高于**非同义编码变异或eQTL SNPs**，说明**非编码区域的进化约束信息具有重要生物学意义**。  

此外，研究还强调了**结构变异（SVs）**和**拷贝数变异（CNVs）**在受约束基因组区域的重要性。研究发现，与受约束区域重叠的CNVs**与疾病风险增加相关**，特别是在**精神分裂症相关基因组区域**。研究还将该方法应用于**癌症基因组学**，发现**非编码约束突变（NCCMs）在脑部肿瘤（如髓母细胞瘤）中，可用于识别新的候选驱动基因**。  

另一个重要贡献是**改进多基因风险评分（PRS）**。研究发现，进化约束可以提高**多种人类疾病和性状的PRS预测准确性**，增强个体**遗传风险评估**的能力。研究表明，**受约束区域的变异在PRS模型的预测能力中占据不成比例的高权重**，进一步验证了它们的**生物学重要性**。  

总体而言，本研究提供了一种**基于全基因组的进化约束度量**，可用于**改进疾病相关遗传变异的识别**。通过整合**比较基因组学、GWAS、精细定位和PRS分析**，研究结果为**优化疾病变异的优先排序、理解遗传力，以及促进治疗开发**提供了重要的科学基础。


---

**Mammalian evolutionary constraint（哺乳动物进化约束）** 是指在**哺乳动物进化过程中，由于功能重要性而受到严格选择的基因组区域**。这些区域在多个哺乳动物物种中**高度保守（conserved）**，即它们的DNA序列在长时间的进化过程中变化极少，这通常意味着它们在生物学功能上至关重要，例如在**基因调控、发育、代谢、免疫等关键生理过程中起作用**。

### **核心概念**
1. **进化约束的定义**  
   - **进化约束（evolutionary constraint）** 反映了某个基因组区域因受到**净化选择（purifying selection）** 而保守不变的程度。  
   - 受高度约束的区域通常**不能容忍突变**，因为这些突变可能会对个体生存或繁殖产生负面影响。  

2. **哺乳动物进化约束的计算**  
   - 研究人员通过比较**多个哺乳动物物种（例如人类、小鼠、灵长类、犬类等）**的基因组序列，识别出进化过程中**变化极少的碱基或区域**。  
   - 计算方法通常基于**系统发育学（phylogenetics）**，比如：
     - **PhyloP**（进化速率计算）  
     - **PhastCons**（用于检测保守序列的统计方法）  

3. **功能性区域的识别**  
   - **蛋白编码区（Coding regions）**：大约 **57.6% 的编码序列** 受到强烈进化约束。  
   - **非编码区（Noncoding regions）**：**约80.7%的受约束碱基位于非编码区**，其中许多是**调控元件（regulatory elements）**，如启动子、增强子等，对基因表达至关重要。

### **应用**
1. **遗传变异的功能预测**
   - 进化约束区域的变异往往是**功能关键突变（functional mutations）**，影响表型和疾病风险。  
   - 例如，在人类遗传研究中，受高度约束的突变通常是**致病突变（pathogenic variants）**，而非约束突变可能是**中性变异（neutral variants）**。

2. **疾病相关突变的优先排序**
   - 在**全基因组关联研究（GWAS）**中，研究人员发现**疾病相关SNPs在受约束区域显著富集**，表明这些区域的变异可能影响疾病风险。
   - **例如：** 精细定位（fine-mapping）研究发现，**进化约束区域的遗传变异比非约束区域更可能与疾病直接相关**。

3. **多基因风险评分（Polygenic Risk Score, PRS）优化**
   - 受进化约束的变异对**多基因疾病（如糖尿病、精神疾病、癌症）的PRS贡献更大**，说明这些区域的变异对疾病风险具有更高的预测价值。

4. **癌症和结构变异分析**
   - 在癌症基因组学中，研究发现**肿瘤基因中的某些非编码受约束区域（NCCMs）可能是新的驱动突变（driver mutations）**，并帮助识别新的癌症相关基因。

### **总结**
**哺乳动物进化约束是基于进化压力来衡量基因组序列重要性的方法**，它能帮助科学家鉴定功能关键变异，并在**疾病研究、基因组功能注释、进化生物学和精准医学**中发挥重要作用。