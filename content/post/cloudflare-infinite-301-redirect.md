+++
author = "Balduran Chang"
categories = ["cloudflare"]
date = 2020-03-01T22:40:14Z
description = ""
draft = false
slug = "cloudflare-infinite-301-redirect"
tags = ["cloudflare"]
title = "cloudflare infinite 301 redirect"

+++


重開之後遇到的小麻煩，會一直 301 redirect，然後就是 infinite loop

主要是 cloudflare SSL 的設定，如果自己的主機 (VPS) 上面已經有啟用 self signed certificate，那 cloudflare 上就不需要使用 Flexible SSL，事實上 Flexible SSL 比較像是掩耳盜鈴的做法，伺服器端其實沒有打開 SSL，只有瀏覽器到 cloudflare 這一段有 SSL，cloudflare 到伺服器這一段是完全沒有加密的。

解決方法也簡單，使用 Full SSL on cloudflare，讓 cloudflare 連到自己主機這一段也啟用 SSL就可。

參考資料 [https://support.cloudflare.com/hc/en-us/articles/115000219871-Troubleshooting-redirect-loop-errors](https://support.cloudflare.com/hc/en-us/articles/115000219871-Troubleshooting-redirect-loop-errors)

