+++
author = "Balduran Chang"
categories = ["doc", "google", "spreadsheet", "stock"]
date = 2014-02-13T18:36:00Z
description = ""
draft = false
slug = "import-stock-price-data-in-google-doc"
tags = ["doc", "google", "spreadsheet", "stock"]
title = "Import stock price data in google doc"

+++


在google doc的spreadsheet 裡面可用函數取得股價資訊。

最直接的，就是使用google 提供的函數 [=GoogleFinance()](https://support.google.com/drive/answer/3093281)，直接用 `=GOOGLEFINANCE("GOOG")`就可以直接拉回股價，若要取得台股資訊，可以直接使用股票號碼，以中華電信 2412為例，  
`=GoogleFinance("2412", "price")`

但事情不是如此美好，有些台股股票代號和其他地區的代碼相衝，例如 1314，直接使用`<br></br>=GoogleFinance("1314", "price")`會拉到[香港Tsui Wah Holdings Ltd(HKG:1314)](https://www.google.com/finance?cid=472042275792381)，此時需要用=GoogleFinance(“1314.tw”, “price”)

你以為這樣就大功告成了嗎？事實上google對於台股的資料並不齊全，上櫃股票完全沒有資料，例如[德昌(5511)](http://tw.stock.yahoo.com/q/bc?s=5511)，怎麼樣都找不到。這個時候，就來求助Yahoo finance吧。

Yahoo finance的資料頗為齊全，雖然台灣網站界面陽春，但是在 [US yahoo finance](http://finance.yahoo.com/)是可以查得到台股資料的，[5511.two](http://finance.yahoo.com/q?s=5511.TWO)就是德昌的公司資訊，請注意代號後面灌的是 two。

Yahoo finance 有很多 API，記下兩種。第一個直接用web service，第二個則是csv output。

1. web service API範例：  
[http://finance.yahoo.com/webservice/v1/symbols/2412.tw/quote](http://finance.yahoo.com/webservice/v1/symbols/2412.tw/quote)  
可直接輸入`= ImportXML(API,"//field[@name='price']")`，用xpath自動去切出股價那一欄
2. 
csv output： Yahoo finance還有提供另一api可直接輸出成csv（excel可直接吃），範例URL: [http://finance.yahoo.com/d/quotes.csv?s=2412.TW&f=l1](http://finance.yahoo.com/d/quotes.csv?s=2524.TW&f=l1)，取得價格的function爲`= ImportData(URL)`，因為此csv output已經調整為只輸出價格資訊，不需要再過濾。 值得注意的一點是上櫃公司的代號尾碼需要使用two，德昌 5511的url為 [http://finance.yahoo.com/d/quotes.csv?s=5511.TWO&f=l1](http://finance.yahoo.com/d/quotes.csv?s=5511.TWO&f=l1)


以股票資訊來說，Yahoo還是有比較充足的後端資料。

