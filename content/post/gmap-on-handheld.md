+++
author = "Balduran Chang"
categories = ["gmap", "GPS", "mobile"]
date = 2008-04-09T17:42:25Z
description = ""
draft = false
slug = "gmap-on-handheld"
tags = ["gmap", "GPS", "mobile"]
title = "Gmap on handheld"

+++


<iframe frameborder="0" height="350" marginheight="0" marginwidth="0" scrolling="no" src="http://maps.google.com.tw/maps/ms?f=l&hl=zh-TW&geocode=&near=%E5%8F%B0%E4%B8%AD&ie=UTF8&om=1&msa=0&msid=102609927208026166024.00044176a5c2c8372cc74&ll=24.787431,120.997528&spn=0,0&t=h&output=embed&s=AARTsJrboCrQ2AoGwWEQtWfFWlEKF8nZqw" width="425"></iframe>  
<small>[檢視較大的地圖](http://maps.google.com.tw/maps/ms?f=l&hl=zh-TW&geocode=&near=%E5%8F%B0%E4%B8%AD&ie=UTF8&om=1&msa=0&msid=102609927208026166024.00044176a5c2c8372cc74&ll=24.787431,120.997528&spn=0,0&t=h&source=embed)</small>  
 上次拿到內建 GPS 的智慧型手機，一直想要嘗試結合 GPS 和 J2ME的程式，正好找到 [Mobile Gmaps](http://www.mgmaps.com/)，是 J2ME 程式，透過 WLAN 或是 電信網路使用 GMAP，其實 yahoo map 是預設地圖，Gmap 被 google 去函關切。

mobile Gmaps 使用上不如想像中順利，ASUS P750 只能選擇一般版本程式，有其他專門給 NOKIA, blackberry, Motorola 手機使用的版本，執行上，一存取 GPS 功能就會出現 MIDlet 錯誤，所以我想試試看地圖服務的路徑規畫功能也不行，只能透過無線網路看看地圖，實在沒什麼新意。

同時間發現 GMap 有 [http://www.google.com.tw/gmm/GoogleMaps.CAB](http://www.google.com.tw/gmm/GoogleMaps.CAB) 可下載安裝，這是個 windows mobile 6 的程式，想必透過微軟的 [GPS API](http://msdn2.microsoft.com/en-us/library/bb202050.aspx) 存取定位，就很順利的玩了起來，像是線上的 PAPAGO 勒。

問題來了，我努力的轉正地圖，想要對正我目前的方向，半夜在浩然與工三之間大廣場的我就這樣在原地站著。被地圖疑惑的我看著位在工四上的全家便利商店標誌和行政大樓上的 7-11 標誌發傻，什麼時候這裡有小七和全家了呢？

補充資料: [如何以 Java 取得衛星定位資訊 ?](http://ccc.kmit.edu.tw/ccc/code/java/gps/index.htm) 寫程式可參考用。

