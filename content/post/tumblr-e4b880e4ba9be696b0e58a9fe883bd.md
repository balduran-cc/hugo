+++
author = "Balduran Chang"
categories = ["tumblelog", "tumblr"]
date = 2007-03-19T17:07:05Z
description = ""
draft = false
slug = "tumblr-e4b880e4ba9be696b0e58a9fe883bd"
tags = ["tumblelog", "tumblr"]
title = "Tumblr 一些新功能"

+++


其實是從開發者的blog上介紹的。

[Syntax Highlighting in Tumblr](http://drnicwilliams.com/2007/03/08/syntax-highlighting-in-tumblr/ "Dr Nic � Syntax Highlighting in Tumblr")讓tumblr上的程式碼更整潔美觀。

[Tumblr API](http://tumblr.com/api/ "Tumblr API")釋出，但是不完整，write的部份還在測試。

版型新增“Litewire“

引言(quote)長度分三種，短、中、長。

[Tumblr Radar](http://tumblr.com/radar "Tumblr Radar")，上面顯示的是最新張貼的連結預覽，並且有條不絮地排列顯示。

張貼連結(link)的話多出一個欄位叫敘述(description)。

import feed的部份也增加了 “Links with descriptions” ,“YouTube Videos”

bookmarklet也更新了，[bookmarklet V3](javascript:var d=document,w=window,e=w.getSelection,k=d.getSelection,x=d.selection,s=(e?e():(k)?k():(x?x.createRange().text:0)),f='http://www.tumblr.net/share',l=d.location,e=encodeURIComponent,p='?v=2&u='+e(l.href) +'&t='+e(d.title) +'&s='+e(s),u=f+p;try{if(!/^(.*\.)?tumblr[^.]*$/.test(l.host))throw(0);tstbklt();}catch(z){a =function(){if(!w.open(u,'t','toolbar=0,resizable=0,status=1,width=450,height=430'))l.href=u;};if(/Firefox/.test(navigator.userAgent))setTimeout(a,0);else a();}void(0) "Drag this link to your Bookmarks Bar. Click to learn more.")

