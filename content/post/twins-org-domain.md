+++
author = "Balduran Chang"
categories = ["balduran", "blog", "domain", "wordpress"]
date = 2008-09-28T15:18:00Z
description = ""
draft = false
slug = "twins-org-domain"
tags = ["balduran", "blog", "domain", "wordpress"]
title = "balduran.twbbs.org"

+++


感謝 [chenpc](http://chenpc.csie.net/) 學長的 [comment](http://balduran.twbbs.org/2008/09/08/%e5%a4%aa%e9%99%bd%e5%8a%87%e5%9c%98/#comment-272)，原來我把 wp-config 檔案設成 644 是不行的，用 wget 之類是看不到，但是用別的帳號 cat 可以看到內容，嗯～我完全沒想過這問題。

如果我用成 600 ，就會出現錯誤是 wp-load.php，一整個奇怪啊！chenpc 學長是系計中助教，帳號的機器和我的好像不一樣，我對系統管理很無知，對於 php 更無知，後來就只好先暫時不管這問題，掩耳盜鈴當沒人看到。

雖然學到了一個方法是 vhost，我弄了 balduran.twbbs.org 這個免費 domain，也設了cname 和目錄，還是不通啊！就又把他擱著。

原來 wordpress 裡的 blog address 和 wordpress address 也要跟著設定，所以弄一弄之後，這個 domain 就可以用啦！

所以 [balduran.twbbs.org](http://balduran.twbbs.org) 以後就用這個吧！向 www.cs.nctu.edu.tw/~changcc/wordpress 告別。

