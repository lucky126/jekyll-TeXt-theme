---
layout: post
title: 《西瓜书》读书笔记1
key: 20180328
tags:
  - 西瓜书
  - 机器学习
  - 读书笔记
  - 概念
lang: zh-Hans
---

# 《西瓜书》读书笔记1

## 基本术语

### 数据集

数据记录的集合称作一个“数据集”（data set），其中每条记录是关于一个事件或者对象的描述，称作一个“示例”（instance）或者“样本”（sample）。
<!--more-->
反映事件或对象在某方面的表现或性质的事项，称作“属性”（attribute）或者“特征”（feature）。属性上的取值称为“属性值”（attribute value）。

属性张成的空间称为“属性空间”（attribute space）、“样本空间”（sample space）或者“输入空间”。

由于空间中的每个点都对应于一个坐标向量，因此把一个示例称作一个“**特征向量**”（feature Vector）。

令$D=\{x_1,x_2,\cdots,x_m\}$表示包含$m$个示例的数据集，每个示例由$d$个属性描述，则每个属性$x_i=(x_{i1};x_{i2};\cdots;x_{id})$是d维样本空间$\chi$中的一个向量，$x_i\in \chi$，其中$x_{ij}$是$x_i$在第$j$个属性上的取值，$d$称为样本$x_i$的“维数”（dimensionality）。

### 训练

从数据中学得模型的过程叫做“**学习**”（learning）或者“**训练**”（training）。这个过程通过执行某个学习算法来完成。

训练过程中使用的数据称为“训练数据”（training data），其中每个样本称为一个“训练样本”（training sample）。

训练样本组成的集合称为“训练集”（Training set）。

学习模型对应了关于数据的某种潜在的规律，称为“假设”（hypotheis）。这种潜在的规律自身，则称为“真相“或者”真实“（ground-truth）。

### 预测

若我们欲预测的是离散值，此类学习任务称为”**分类**“（classification）；若预测的是连续值，此类学习任务称为”**回归**“（regression）。

对只涉及两个类别的”二分类“（binary classification），通常称其中一个类为”正类“（positive class），另一个类为”反类“（negative class）。

### 测试

学得模型后，使用其进行预测的过程称为”测试“（testing），被预测的样本称为”测试样本“（testing sample），例如学得$f$后，对预测例$x$，可得到其预测的标记$y=f(x)$。

### 聚类

我们还可以对数据做”聚类“（clustering），即将训练集中的数据分为若干组，每组称为一个”簇“（cluster）。在聚类学习中簇我们事先是不知道的，而切学习过程中使用的训练样本通常不拥有标记信息。

根据训练数据是否拥有标记信息，学习任务大致划分为两大类：”**监督学习**“（supervised learning）和”**非监督学习**“（unsupervised learning），分类和回归是前者的代表，而聚类则是后者的代表。

