---
layout: post
title: 《白话大数据与机器学习》读书笔记7
key: 20180306
tags:
  - 大数据
  - 机器学习
  - 读书笔记
  - 人工神经网络
lang: zh-Hans
---

# 《白话大数据与机器学习》读书笔记7

## 人工神经网络

### 人工神经网络（Artificial Neural Network， ANN）

激励函数

$$f(x)=\sum_{x=1}^nw_ix_i=w^Tx$$

逻辑回归（Logistic Regression）

### FANN库

FANN是一个开源的神经网络模型库，全称Fast Artificial Neural Network。

### 常见的神经网络

* 感知器网络（Perceptron）
* 按误差逆转传播算法训练的多层前馈网络（Back Propagation，BP神经网络）
* 自组织特征映射神经网络（Self-Organizing Feature Map，SOM）
* Hopfield网络
* 玻尔兹曼机（Boltzmann Machine）
* 卷积神经网络（Convolutional Neural Network，CNN）

### BP神经网络

#### 结构与原理

激活函数为Logistic 函数：

$$f(v)=\frac{1}{1+e^{-w^Tv+b}}$$

有的地方写成如下形式：

$$f(t)=\frac{1}{1+e^{-mt}}$$

m是可以调整的正整数，m越小曲线越平缓，m越大曲线越立陡。

#### 训练过程

