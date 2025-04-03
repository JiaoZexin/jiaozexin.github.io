---
layout: post
title:  "Note_Zscore_normalization"
date:   2025-04-03 21:50:00 +0000
categories: Note
---


**Z-score标准化**（也叫标准差标准化，Z-score normalization 或 standardization）是一种将数据转换为标准正态分布的方法，其目的是将不同量纲或范围的数据变为具有相同尺度的数据，便于比较或用于某些对尺度敏感的算法（如PCA、聚类等）。

### 标准化公式如下：

\[
z = \frac{x - \mu}{\sigma}
\]

- \( x \)：原始数据
- \( \mu \)：该特征的均值（mean）
- \( \sigma \)：该特征的标准差（standard deviation）

### 标准化后的结果：
- 转换后的数据 **均值为0**，**标准差为1**
- Z-score表示某个数据点距离均值的“标准差个数”，比如：
  - \( z = 1 \)：该数据点比均值大一个标准差
  - \( z = -2 \)：该数据点比均值小两个标准差

### 什么时候用Z-score标准化？
- 特征数据呈**高斯分布（近似正态）**
- 特征之间的量纲不一致、方差差异较大
- 用于PCA、K-means、SVM、逻辑回归等对数据分布敏感的算法

如果你想，我可以用Python或R帮你演示一组数据如何进行Z-score标准化。需要吗？