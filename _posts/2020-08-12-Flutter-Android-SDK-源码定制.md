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
* 需要新的aar包就得编译整个project，时间花费长

优势：

这样做的优势在于我们不需要编译整个engine，我们要对我们感兴趣的部分进行学习修改即可，也不用担心引起其他的版本号不对应的问题

# 提取步骤

## 缓存源码提取
* 找到缓存路径
* 首先从我们的Android studio查看我们依赖的sdk的版本号和缓存key，如：
![](/image/2020-09-21-10-29-39.png)

可以发现gradle的缓存key就是```1.0.0-9d5b21729ff53dbf8eadd8bc97e0e30d77abec95```

找到缓存本地的源代码:
```
~/.gradle/caches/modules-2/files-2.1/io.flutter/flutter_embedding_debug/1.0.0-9d5b21729ff53dbf8eadd8bc97e0e30d77abec95/a3a5d5fbb289b6c2aee5244b420411b11adaa632/flutter_embedding_debug-1.0.0-9d5b21729ff53dbf8eadd8bc97e0e30d77abec95-sources.jar
```

将-sources.jar解压备用

## 创建新的Lib

创建![](/image/2020-09-21-10-50-16.png)

并把上一步解压的源文件copy的lib项目中，如图所示：
![](/image/2020-09-21-10-59-47.png)
拷贝过了的
## 修改错误
* 把JDK改为1.8
![](/image/2020-09-21-11-15-50.png)

* copy一份fluter.gradle, 改为fluter1.gradle，把fluter.gradle删除
![](/image/2020-09-21-11-19-05.png)

* 去flutter.gradle文件修改, 注释两个地方，因为这两个地方通过flutterlib的方式引入了
![](/image/2020-09-21-11-27-06.png)
![](/image/2020-09-21-11-27-31.png)

对错误做一下修改：
```
  注释BuildConfig.JIT_RELEASE
  修改androidx.annotation.NonNull
  修改androidx.annotation.Nullable
```

## 修改源码

运行没有错误就可以改源码了






