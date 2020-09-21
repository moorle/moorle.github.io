---
layout: post
keywords: flutter
description: "Flutter中将回调(Callback)转换为Futrue"
title: "Flutter中将回调(Callback)转换为Futrue"
categories: [flutter]
tags: [flutter]
---
{% include codepiano/setup %}

# Flutter中将回调(Callback)转换为Futrue

考虑将回调转成Future的情形：

* 使用回调不好处理时
* 回调的嵌套太深

``` dart

  void workCallback(String path, onSuccess(url), onFailure()) {
    // do upload
    Future.delayed(Duration(seconds: 1)).then((value) {
      onSuccess("");
    });
  }

  Future<String> workFuture(String path) {
    Completer<String> completer = Completer();
    warkCallback(path, (url) => completer.complete(url),
        () => completer.completeError(StateError('This is a Dart exception.')));
    return completer.future;
  }

```



