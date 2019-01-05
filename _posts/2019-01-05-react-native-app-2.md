---
layout: post
title: React Native APP开发学习笔记2
key: 20190105
tags:
  - React
  - React Native
  - APP
lang: zh-Hans
---

# React Native APP开发学习笔记2

## Android 打包发布
<!--more-->
### 基本打包流程

基本打包流程可以参见：ReactNative之Android打包APK方法(https://www.jianshu.com/p/1380d4c8b596)

### 特殊情况处理

但是在参考网页的过程中遇到了如下问题：

* 无法使用Android Studio完成签名
  
  解决办法：使用方法一，通过命令行完成签名

* 使用
  ```
  ./gradlew installRelease
  ```
  命令系统提示找不到instalRelease命令

  解决办法：确认buildTypes的release节点下面存在如下语句：
  ```
  signingConfig signingConfigs.release
  ```

* 版本不一致问题：
   
  解决办法：确认compileSdkVersion和targetSdkVersion，dependencies.compile中所涉及的版本号是否都正确或者一致。

* 图片无法显示问题：

  解决办法：和IOS一样，把图片目录拷贝到assets目录下即可。不过记得是使用“打包离线Bundle”后哦，不是签名的步骤哦。

  ## IOS打包发布

  参考 react native ios打包到真机（https://blog.csdn.net/ailongyang/article/details/54866469） 即可。