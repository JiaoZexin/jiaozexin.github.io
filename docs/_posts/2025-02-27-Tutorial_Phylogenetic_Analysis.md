---
layout: post
title:  "Tutorial_Phylogenetic_Analysis"
date:   2025-02-27 20:59:00 +0000
categories: Tutorial
---


系统发育分析（phylogenetic analysis）常见流程如下：  

---

### **1. 数据收集（Data Collection）**  
- **基因选择**：常用基因包括**线粒体基因（COI, Cytb, 16S rRNA）**和**核基因（RAG1, RAG2, EGR2B, IRBP2等单拷贝基因）**。  
- **序列获取**：
  - 直接从**NGS数据**或**基因组数据**提取序列。  
  - 从**NCBI GenBank**等公共数据库下载相关物种的基因序列。  
  - 通过**PCR扩增和Sanger测序**获得特定基因序列。  

---

### **2. 序列比对（Sequence Alignment）**  
- **工具**：  
  - **MAFFT**（快速高效，适用于大规模数据）  
  - **ClustalW**（传统方法，适用于小规模数据）  
  - **MUSCLE**（适用于高精度比对）  
- **比对优化**：
  - 使用**Gblocks**去除低质量比对区域（去除高变区和插入缺失）。  
  - 进行**手动调整**（例如在MEGA中检查比对质量）。  

---

### **3. 选择合适的进化模型（Model Selection）**  
- **工具**：  
  - **ModelTest（MEGA）**  
  - **jModelTest（适用于核苷酸序列）**  
  - **ProtTest（适用于蛋白序列）**  
  - **PartitionFinder（用于选择分区模型）**  
- **常见替代模型**：  
  - GTR+G+I（广泛适用于核苷酸序列）  
  - HKY+G（适用于线粒体基因）  
  - LG+G（适用于蛋白序列）  

---

### **4. 系统发育树构建（Phylogenetic Tree Construction）**  
- **构建方法**：
  - **最大似然法（Maximum Likelihood, ML）**（高效、适用于大数据集）  
    - 工具：**IQ-TREE、RAxML、PhyML**  
  - **贝叶斯推断（Bayesian Inference, BI）**（计算更耗时，但支持率较高）  
    - 工具：**MrBayes**（MCMC采样）  
  - **邻接法（Neighbor-Joining, NJ）**（计算快但精度较低）  
    - 工具：**MEGA**  
  - **最小进化法（Minimum Evolution, ME）**（类似NJ，但更稳定）  
- **支持率评估**：
  - **Bootstrap**（常设1000次重复，>70%为可靠支持）  
  - **Posterior Probability**（BI树支持率，>0.9较可靠）  

---

### **5. 时间树构建（Divergence Time Estimation，可选）**  
- **工具**：
  - **BEAST2**（使用贝叶斯方法推算分歧时间）  
  - **MEGA**（可进行分子钟分析）  
- **标定点**：
  - 采用**化石记录**或**已知进化时间（TimeTree数据库）**作为校准点。  

---

### **6. 进化地理分析（Ancestral Geographic Reconstruction，可选）**  
- **工具**：
  - **RASP（Reconstruct Ancestral State in Phylogenies）**：用于祖先地理重建。  
  - **BioGeoBEARS**：用于生物地理建模分析。  

---

### **7. 结果可视化与解析（Visualization & Interpretation）**  
- **工具**：
  - **FigTree**（常用于美化进化树）  
  - **iTOL**（在线交互式可视化）  
  - **MEGA**（基本进化树绘制）  
  - **ggtree（R包）**（高阶绘图）  
- **分析重点**：
  - 物种分类关系是否符合已知研究。  
  - 进化树支持率是否可靠。  
  - 进化分歧时间是否符合地质事件。  

---

以上是系统发育分析的常见流程，具体方法可根据研究目标和数据类型进行调整。 