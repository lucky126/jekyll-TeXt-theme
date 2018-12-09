---
layout: post
title: React Native APP开发学习笔记1
key: 20181209
tags:
  - React
  - React Native
  - APP
lang: zh-Hans
---

# React Native APP开发学习笔记1

## 开发环境准备
<!--more-->
### 安装Homebrew
Homebrew, Mac系统的包管理器，用于安装NodeJS和一些其他必需的工具软件。

Homebrew全称Homebrew is the easiest and most flexible way to install the UNIX tools Apple didn’t include with OS X

在终端中输入这行代码

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
译注：在Max OS X 10.11（El Capitan)版本中，homebrew在安装软件时可能会碰到/usr/local目录不可写的权限问题。可以使用下面的命令修复：

```
sudo chown -R `whoami` /usr/local
```

### 安装node

React Native 需要 NodeJS 4.0或更高版本，Homebrew的Node默认包是6.0版本的，所以直接安装即可：

```
 brew install node
```

安装完node后建议设置npm镜像以加速后面的过程（或使用科学上网工具）。
```
npm config set registry https://registry.npm.taobao.org --global
npm config set disturl https://npm.taobao.org/dist --global
```

### 安装watchman

Watchman是Facebook开发的一个检测文件系统变化的工具，在RN开发中可以检测js文件等是否有变化，从而达到保存及编译的效果。

```
brew install watchman
```

### 安装flow

静态类型检查工具
```
brew install flow
```

## 移动端准备

### IOS准备
安装Xcode ，可直接在app store 中下载

Windows下请忽略，无法完成IOS的调试和开发

### Android准备

#### 安装Java Development Kit

React Native 需要 Java Development Kit [JDK] 1.8（暂不支持 1.9 及更高版本）

下载地址：

https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

以macos为例：

1. 安装 Android Studio
首先下载和安装 Android Studio，国内用户可能无法打开官方链接，请自行使用搜索引擎搜索可用的下载链接。安装界面中选择"Custom"选项，确保选中了以下几项：

* Android SDK
* Android SDK Platform
* Performance (Intel ® HAXM)
* Android Virtual Device

2. 安装 Android SDK

Android Studio 默认会安装最新版本的 Android SDK。目前编译 React Native 应用需要的是Android 8.1 (Oreo)版本的 SDK。

```
SDK Manager 还可以在 Android Studio 的"Preferences"菜单中找到。具体路径是Appearance & Behavior → System Settings → Android SDK。
```

在 SDK Manager 中选择"SDK Platforms"选项卡，然后在右下角勾选"Show Package Details"。展开Android 8.1 (Oreo)选项，确保勾选了下面这些组件（重申你必须使用稳定的翻墙工具，否则可能都看不到这个界面）：

* Android SDK Platform 27
* Intel x86 Atom_64 System Image（官方模拟器镜像文件，使用非官方模拟器不需要安装此组件）

然后点击"SDK Tools"选项卡，同样勾中右下角的"Show Package Details"。展开"Android SDK Build-Tools"选项，确保选中了 React Native 所必须的27.0.3版本。

3. 配置 ANDROID_HOME 环境变量

在~/.bash_profile的最下面增加
```
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
export PATH=$PATH:$ANDROID_HOME/emulator
```

使用source $HOME/.bash_profile命令来使环境变量设置立即生效

## 我的第一个项目
```
react-native init demo --version 0.44.3

cd demo 

react-native run-ios

react-native run-android
```

坑1：本人尝试如果react-native命令不加版本号则创建项目失败