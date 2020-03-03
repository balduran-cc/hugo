+++
author = "Balduran Chang"
categories = ["bookmarklet"]
date = 2007-12-04T06:56:39Z
description = ""
draft = false
slug = "dict-bookmarklet"
tags = ["bookmarklet"]
title = "查字典小書籤"

+++


[gagadict](javascript:q = %22%22 + (window.getSelection ? window.getSelection() : document.getSelection ? document.getSelection() : document.selection.createRange().text); if (!q) q = prompt(%22You didn't select any text.  Enter a search phrase:%22, %22%22); if (q!=null) location=(%22http://cdict.giga.net.tw/q/%22   + escape(q.replace(/\%22/g,%22%22)) ); void 0)

自己為了方便查單字弄得，修改網路上找到的查字典小書籤，改成查 [giga dictionary](http://cdict.giga.net.tw/)。

使用方法，拖到書籤列上，要使用時後就反白要查的字，在點這個小書籤就可以了，如果沒有選擇任何字會跳出輸入對話框。

