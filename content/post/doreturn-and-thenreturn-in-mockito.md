+++
author = "Balduran Chang"
categories = ["java", "programming"]
date = 2015-10-20T04:38:36Z
description = ""
draft = false
slug = "doreturn-and-thenreturn-in-mockito"
tags = ["java", "programming"]
title = "doReturn and thenReturn in Mockito"

+++


用 [Mockito] 寫 unit test 的時候，一開始分不清楚 doReturn 和 thenReturn 的差別，基本上是一樣的，都是在做 stub。

[Mockito]: http://mockito.org/

但有一些例外。

1. thenReturn 不能用來 stub void method
2. spy 不能搭配 thenReturn
3. stub same method 多次不能用 thenReturn
4. doReturn 在編譯期間不做 return value 的型別檢查，thenReturn 會做 type check
5. thenReturn 會先去執行 stub 的 method，然後改寫掉 return value，如果 method 裡有些變數沒有 mock ，極可能會 null pointer exception

總結，只要使用 `doReturn`, `doThrow `, `doAnswer ` 就會，會單純一點。

Btw, @Mock 可以簡化一些 code

