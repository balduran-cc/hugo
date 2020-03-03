+++
author = "Balduran Chang"
categories = ["bookmarklet", "javascript", "youtube"]
date = 2009-06-22T00:32:26Z
description = ""
draft = false
slug = "download-youtube-video-using-bookmarklet"
tags = ["bookmarklet", "javascript", "youtube"]
title = "download youtube video using bookmarklet"

+++


via [http://googlesystem.blogspot.com/2008/04/download-youtube-videos-as-mp4-files.html](http://googlesystem.blogspot.com/2008/04/download-youtube-videos-as-mp4-files.html)

我對於怎麼下載youtube的影音滿有興趣的，不過動機並沒有那麼邪惡，是想要作youtube上面的影片的一些分析，不過這個不在我的學位論文範疇之內，就先打住。

youtube的影音是用flv的方式在傳遞，有些網站可以解析出這些flv檔案的所在位置並下載，對影音檔處理苦手的我是不太碰觸這領域的，google怎麼隱藏這些原始位置巴拉巴拉，我完全都不知道。

[get youtube video](javascript:if(document.location.href.match(/http:\/\/[a-zA-Z\.]*youtube\.com\/watch/)){document.location.href='http://www.youtube.com/get_video?fmt='+(isHDAvailable?'22':'18')+'&video_id='+swfArgs['video_id']+'&t='+swfArgs['t']}) 這個小書籤實在太強了，很短，作用卻很大。稍微看了一下，是解析網頁原始檔中用jscript引入flash的參數，有video_id，這個很明顯在網址可以看到，還有一個隱藏的 t 作檢查之用，這樣一看，就稍微有點概念youtube的頁面適用jscript動態生成，只看html的部份是無所穫。

jscript 學會的話對於解析網頁應該頗有幫助。

