---
layout: post
title: 《白话大数据与机器学习》读书笔记6
key: 20180306
tags:
  - 大数据
  - 机器学习
  - 读书笔记
  - 关联分析
  - 用户画像
  - 推荐算法
  - 文本挖掘
lang: zh-Hans
---

# 《白话大数据与机器学习》读书笔记6

## 关联分析

### 频繁模式

无序的组合叫做“模式”。一般认为频度较高的模式叫做“频繁模式”。
<!--more-->
#### 支持度和置信度

衡量频率的两个指标：支持度和置信度

* 样本中支持度（support）是，出现这个模式占总样本的比重。
* 置信度（confidence）是有“方向性”的。A->B的置信度是，A中含有B的比重。

#### Apriori算法

### 关联分析和相关性分析

#### 关联度（correlation）

提升度（Lift）是一种简单的关联度度量。

$$Lift(A,B)=\frac{P(B|A)}{P(B)}$$

与朴素贝叶斯公式类似。右侧分子是A发生情况下发生B的概率。

> 相关性等于1时，B发生概率和发生情况下发生B的概率一样，他们毫无关系。<br/>
> 相关性大于1时，发生A的情况下发生B的概率要比单独统计B发生的概率大，B和A是正相关的，也就是说A促进B的发生。<br/>
> 相关性小于1时，发生A的情况下发生B的概率比单独统计B的发生的概率要小，B和A是负相关的，也就是说A的发生抑制了B的发生。

## 用户画像

## 推荐算法

### 基于用户的协同过滤User-based CF（User-based Collaborative Filtering）

$$cos(a,b)=\frac{a\cdot b}{|a|\cdot |b|}$$

$a\cdot b$是两个向量的$x,y$维度各自乘积再加和，$\|a\|\cdot\|b\|$是两个向量线段的长度，即勾股定理，$x^2+y^2$。

### 基于商品的协同过滤Item-based CF（Item-based Collaborative Filtering）

$$cos(A,B)=\frac{N(A\cap B)}{\sqrt{N(A)\cdot n(B)}}$$

分子是喜欢A和B两种商品的用户数量，即交集。分子是喜欢A的用户数量和喜欢B的用户数量的乘积的平方根。

## 文本挖掘

### 文本挖掘的领域

1. 搜索与信息检索（Information Search ，IR）
2. 文本聚类
3. 文本分类
4. Web挖掘
5. 信息抽取（Information Extraction，IE）
6. 自然语言处理（Natural Language Processing，NLP）
7. 概念提取

### 文本分类

#### Rochhio算法

$$cos(\theta)=\frac{s_1c_1+s_2c_2+\cdots+s_nc_n}{\sqrt{s_1^2+s_2^2+\cdots +s_n^2}\cdot \sqrt{c_1^2+c_2^2+\cdots+c_n^2}}$$

#### 朴素贝叶斯算法

$$P(D_j|x)=\frac{P(x|D_j)P(D_j)}{\sum_{i=1}^n{P(x|D_i)P(D_i)}}$$

#### K-近邻算法（KNN算法）

K-近邻算法英文全称K-Nearest Neigbours。

#### 支持向量机（SVM）算法

