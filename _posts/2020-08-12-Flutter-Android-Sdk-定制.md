---
layout: post
keywords: flutter
description: "Flutter Android SDK 源码定制"
title: "Flutter Android SDK 源码定制"
categories: [flutter]
tags: [flutter]
---
{% include codepiano/setup %}

# Flutter Android SDK 源码定制

## 目的

* 学习Flutter Android源码
* 方便修改、调试，并查看效果

虽然原来引用方式也可以直接调试，但是不可以直接修改源码，所以为了能够直接修并能查看效果，需要将sdk源码直接下载下来，以本地库依赖的方式引入。

## Flutter Android SDK 源码仓库地址：

[ https://github.com/flutter/engine](https://github.com/flutter/engine/tree/master/shell/platform/android/io/flutter)

问题：

* 如果直接下载下来，有可能版本跟本地的没有对应起来
* Flutter Android SDK 源码并不是一个独立的项目

优势：

    这样做的优势在于我们不需要编译整个engine，我们要对我们感兴趣的部分进行学习修改即可，而不用担心引起其他的版本号不对应的问题

# 提取步骤

## 缓存源码提取
首先从我们的Android studio查看我们依赖的sdk的版本号和缓存key，如：


找到缓存本地的源代码

## 创建新的Lib

## 修改错误

## 修改源码

## 运行查看结果





