+++
author = "Balduran Chang"
categories = ["NSIS", "installer", "unicode"]
date = 2016-09-05T02:29:46Z
description = ""
draft = false
slug = "nsis-and-unicode"
tags = ["NSIS", "installer", "unicode"]
title = "NSIS and unicode"

+++


目前工作上需要寫 Nsis script 來打包程式，遇上了 unicode 的問題。

[官方網站][NSIS]下載的 NSIS2 是不支援 unicode的，NSIS3 則是[最近公布](http://nsis.sourceforge.net/News)了穩定版並且支援 unicode，在這漫長的 NSIS2 to NSIS3 中間，有善心人士發表了 [Unicode NSIS][]，也是美事一樁，但可惜[到了2012](https://code.google.com/archive/p/unsis/downloads)年就不再更新。

Unicode NSIS沒有與時俱進，如果用到 nsDialog 或是 MUI2 等後期出現的 plugin，那就會爆炸給你看。會產出 exe 檔案，但不會如妳所預期。

另外有一個 [plugin](http://nsis.sourceforge.net/Unicode_plug-in) 可以讀取 unicode files，轉換編碼，我沒有使用過，但如果要搭配 NSIS2，這個 plugin 可以考慮。

依照目前 NSIS3 的發布，直接使用 [Unicode attribution][]設定即可，對於已經寫好的 nsis script，應該不需要做額外改動還是可以動。


[NSIS]: http://nsis.sourceforge.net/Download
[Unicode NSIS]: http://www.scratchpaper.com/
[Unicode attribution]: http://nsis.sourceforge.net/Docs/Chapter1.html#intro-unicode

