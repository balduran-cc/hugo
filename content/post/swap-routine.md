+++
author = "Balduran Chang"
categories = ["note", "program"]
date = 2007-11-23T20:41:51Z
description = ""
draft = false
slug = "swap-routine"
tags = ["note", "program"]
title = "交換變數"

+++


看到 [Tsung’s Blog | 交換兩個變數 (不使用 tmp 變數) 程式寫法](http://plog.longwin.com.tw/programming/2007/11/23/variable_swap_programming_2007)，恩，以前看到的時候也是讚嘆一下。

可以縮減成 a^=b^=a^=b ，但是短歸短，可讀性是零。所以完全不建議將程式寫成這樣，之後自己在看到這種程式碼或是別人要維護你的程式碼的時候，可就痛苦了。

最笨的就是最好的，還是繼續 c=a;a=b;b=c; 吧。

