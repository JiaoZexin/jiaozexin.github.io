---
layout: post
title:  "Note_SVs_software_list"
date:   2025-03-14 15:25:00 +0000
categories: Note
---


猪 [SVs](https://doi.org/10.1186/s40104-023-00929-x) 软件

Here are the software and R packages used in the study, along with a brief description of their functions:

### **Software and Tools:**
1. **Samplot** – Used for visualizing structural variants (SVs).
2. **GCTA** – Performs principal component analysis (PCA) for population genetics.
3. **Admixture** – Estimates population structure based on genetic data.
4. **Phylip** – Constructs phylogenetic trees for evolutionary analysis.
5. **MEGA11** – Visualizes phylogenetic trees.
6. **SnpEff** – Annotates and predicts effects of genetic variants.
7. **VCFtools** – Analyzes and manipulates VCF files for genetic variation studies.
8. **DAVID** – Provides gene ontology (GO) and pathway enrichment analysis.
9. **Structure Harvester** – Determines the best K-value in population structure analysis.
10. **GenAIEx** – Conducts genetic diversity and AMOVA analysis.

### **R Packages:**
1. **ggplot2** – Creates elegant visualizations of genetic and statistical data.
2. **ggspatial** – Enhances spatial data visualization in genetic mapping.
3. **factoextra** – Extracts and visualizes results of multivariate data analyses.
4. **nnet** – Implements neural networks for statistical computing.
5. **SNPRelate** – Performs SNP-based principal component analysis and relatedness estimation.
6. **wordcloud** – Generates word clouds for visual representation of enriched terms.
7. **[rMVP](https://github.com/xiaolei-lab/rMVP)** - An r package for Memory-efficient, Visualization-enhanced, and Parallel-accelerated Genome-Wide Association Study 

These tools and R packages were essential in analyzing genetic variation, population structure, and functional annotation of SVs in the study .



样本地理分布图是使用R中的ggplot2 [27]和ggspatial包生成的。使用GCTA [28]软件进行了主要成分分析（PCA）。使用Admixture[29]评估了种群结构，并计算了三个可能的种群（K = 2-4）。接下来，使用ggplot2软件包绘制PCA和种群结构结果。相邻连接的树木是使用Phylip[30]建造的，并由MEGA11 [31]可视化。SV分布位置是根据Ensemble数据库中的基因位置注释确定的，Snpeff[32]根据SV断点的位置估计了SV效应。为了识别品种分层的SV，VCFtools [33]使用Weir和Cockerham方法计算所有SV的固定指数（FST）值，比较15 Min与15头大白猪。选择了FST值位于前5%的分化区域内的所有SV，并根据Ensemble注释的基因信息，与SV重叠的相应基因被视为品种分层的候选者。候选基因由DAVID在线网站（https://david.ncifcrf.gov/）使用基因本体（GO）和京都基因与基因组百科全书（KEGG）功能富集分析注释。wordcloud webloci（https://www.jasondavies.com/wordcloud/）用于为前10个显著丰富的术语（P < 0.05）创建单词云，以揭示潜在的分子机制。

特定人群的SV筛查、基因分型和GWAS
为了获得影响特定特征的潜在因果位点，对差异基因型位点使用了筛选策略。这项筛选策略选择了6头相对纯种的Min猪（M1，M3-M7）和15头大白猪。设定了两个条件：第一，为一个品种选择一个基因型，为另一个品种设定其余两个基因型；第二，Min猪（≥5个个体）基因型的频率超过80%，大白猪（≥8个个体）的基因型频率超过50%（图。S2，附加文件2）。当SV基因位基因库符合上述两个条件时，它被认为是候选基因位基因。筛选的SV基因座使用F2个体的bam文件进行基因分型，其中DEL、DUP和INV使用SVtyper进行基因分型，而MEI使用段落[34]进行基因分型。Plink [35]执行了用以下特定参数过滤所有基因型SV基因座：样本呼叫率>90%，SV呼叫率>90%，次要等位基因频率>5%。EMMAX [36]用于使用所有过滤的SV基因座的混合线性模型来执行GWAS。性别和屠宰批次被用作固定效应，PCA被用作协变量。显著性截止值被定义为Bonferroni测试阈值，设置为0.05/（SV总数）。所有GWAS结果都使用rMVP [37]软件包进行可视化。