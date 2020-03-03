+++
author = "Balduran Chang"
categories = ["mysql", "wiki"]
date = 2007-11-21T03:33:25Z
description = ""
draft = false
slug = "mediawiki_setup"
tags = ["mysql", "wiki"]
title = "mediawiki 安裝記錄"

+++


從昨天搞到現在一直在 try & error。遇到

> 1267: Illegal mix of collations

 網路上 google 到的解法都是一致性 (流傳?) 的說修改 Database.php，加上 mysql_query("SET NAMES ‘utf8′;", $this->mConn ); 巴拉巴拉的，對我來說都沒用。

然後我突然想到一個很根本的問題，我建立資料庫之後沒有更改 Collation (中文翻譯:校對)，所以 Localsettings.php 產生的時候建立的資料表都不是 UTF-8，打所有資料表刪除之後重新 config 一次，就 OK 了，白花了很多時間。

下一步，試著安裝 drupal。

notes: [oddmuse](http://www.chieftain.idv.tw/archives/2004/04/23/364.html) from Reflection

