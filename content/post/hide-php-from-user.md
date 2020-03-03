+++
author = "Balduran Chang"
categories = ["php", "apache"]
date = 2014-07-22T09:57:00Z
description = ""
draft = false
slug = "hide-php-from-user"
tags = ["php", "apache"]
title = "Hide php from user"

+++


為了安全性的理由，我們儘量不想讓網頁的副檔名出現在url內，也就是儘量不讓外界得知 uri 的實際檔案形態，例如 https://www.google.com.tw/?#q=obj 就完全把負責處理的檔案名稱隱藏了。

php.net 上有[說明頁面](http://php.net/manual/en/security.hiding.php)，可用的php ini  
expose_php = off

或是  
AddType application/x-httpd-php .asp .py .pl  
此為偽裝php 為其他script lang

AddType application/x-httpd-php .htm .html  
此為偽裝php 為靜態html 頁面

除此之外，還有[sethandler](http://httpd.apache.org/docs/2.2/mod/core.html#sethandler)可用。

<script src="https://gist.github.com/balduran/f9cd4ef35231640477b2.js"></script>

