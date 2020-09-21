---
layout: post
keywords: flutter
description: "Flutter Navigator"
title: "Flutter Navigator"
categories: [flutter]
tags: [flutter]
---
{% include codepiano/setup %}

# Flutter Navigator

## Navigator作用

官方解释：

A widget that manages a set of child widgets with a stack discipline.

## Navigator组织形式

- 万物皆Widget

  所以Navigator也是一个Widget，是在创建WidgetsApp的时候创建

- 嵌套Navigator

    一个App是可以包含多个Navigator实例的，比较复杂的模块可以划分多个Navigator，模块化管理

只有一个Navigator的情况

``` dart
    Root
    |
    | - Navigator
        |
        | - Page1
        |
        | - Page2
        |
        | - Page3
```

多个Navigator的情况

```dart
    Root
    |
    | - Navigator
        |
        | - Page10
        |   |
        |   Navigator
        |   |
        |   | - Page20
        |   |
        |   | - Page21
        |       |
        |       Navigator
        |       |
        |       | - Page30
        |
        | - Page11
```

## Navigator的查找

Navigator的查找过程是通过Buildcontext的以下两个方法查询到它的实例的，具体使用那个是根据他的参数决定的，默认是使用findAncestorStateOfType

```dart
    1. context.findRootAncestorStateOfType<NavigatorState>()

    2. context.findAncestorStateOfType<NavigatorState>()
```

来查找的，两者的差别在于，一个查询最顶层祖先的NavigatorState， 一个查询最近祖先NavigatorState





