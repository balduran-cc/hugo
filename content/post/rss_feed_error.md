+++
author = "Balduran Chang"
categories = ["feedburner", "rss"]
date = 2007-11-08T12:22:11Z
description = ""
draft = false
slug = "rss_feed_error"
tags = ["feedburner", "rss"]
title = "RSS feed 暫時出錯"

+++


這幾天一直好奇 FeedBurner 的訂閱人數怎麼會是 “0”，點下去之後也是錯誤訊息，本來以為是 FeedBurner 的問題，但事實上是我不知道把 WP 搞到出問題了，實在是失禮啊。  
 看 FeedBurner 的 troubleshoot顯示是 404 – Not Found ，才發現 /~changcc/wordpress/feed 無法開啟，可是原始的 RSS feed 位址 wp-rss2.php 是正常的，我也不知道自己改了哪些設定，WP 我不熟悉，但直接先把 plugins裡面的 FeedBurner FeedSmith 關掉，還是無效，最後直接更改 FeedBurner 指向 wp-rss2.php 就解決了。  
 事後我想應該是 self reference 造成，Feedsmith 會更改 /Feed 目錄指向 FeedBurner/balduran，而我的 FeedBurner 的原始 RSS Feed 又是 /Feed，就這樣兩個互相指向對方，內容當然是空白啦。

裝很多 Plugins 很好玩，但是也有些問題會出現。

