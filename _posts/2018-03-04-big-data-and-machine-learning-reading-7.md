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
modify_date: 2018-03-09
---

# 《白话大数据与机器学习》读书笔记7

## 人工神经网络

### 人工神经网络（Artificial Neural Network， ANN）

激励函数
<!--more-->
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

1)误差计算

整个网络误差函数为：

$$E=\frac{1}{2}\sum_{i=1}^nE_i=\frac{1}{2}\sum_{i=1}^n(d_{oi}-y_{oi})^2$$

2)反向传播

误差的梯度：

$$\delta_h=(\delta_ow_{ih})f\prime(h_i)$$

3)权值修正

隐含层更新：

$$w_{ho}^{N+1}=w_{ho}^{N}+\eta\delta_oh_o$$

输出层更新：

$$w_{ih}^{N}=w_{ih}^{N}+\eta\delta_hh_i$$

## 卷积神经网络

卷积神经网络（Convolutional Neural Network，CNN）是一种前馈神经网络。

一般来说，CNN的基础结构包括两层。

第一层是特征提取层，每个神经元的输入与前一层的局部接受域相连，并提取该局部的特征。

第二层是特征映射层，网络的每个计算层由多个特征映射组成，每个特征映射是一个平面，平面上所有神经元的权值相等。

### 卷积

在泛函分析中，有卷积，旋积或摺积（Convolution）的定义。他是通过两个函数$f$和$g$生成第三个函数的一种数学算子，表征函数$f$和$g$经过翻转和平移的重叠部分的面积。

卷积的数学定义如下：

$$h(x)=f(x)*g(x)=\int_{-\infty}^{+\infty}f(t)g(x-t)\text{d}t$$

