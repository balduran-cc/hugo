+++
author = "Balduran Chang"
categories = ["chrome", "puppeteer", "headless", "phantomjs", "es6"]
date = 2017-10-25T17:59:00Z
description = ""
draft = false
slug = "phantomjs-and-puppeteer"
tags = ["chrome", "puppeteer", "headless", "phantomjs", "es6"]
title = "PhantomJs and puppeteer"

+++


[PhantomJs](http://phantomjs.org/) 一度是唯一的 headless browser，意思是他是可以用程式操控的瀏覽器，舉凡定時對網站做screenshot，或是檢查 html裡面某些內容，都可以透過程式操作 PhantomJs做到。

在軟體開發的過程中，只要是 html+js+css的專案，需要做 Unit Test的時候，都可以使用這個「看不見」的瀏覽器去執行，讓自動化的流程更順利。

不過我最近在寫的程式用到了 [ES6](https://github.com/lukehoban/es6features) 的語法，PhantomJS在讀取這部分程式的時候就噴 error了，正尋找解法的時候，發現 PhantomJs已經停止新功能的開發，主要開發者 Vitaly Slobodin 發了[一篇聲明](https://groups.google.com/forum/#!topic/phantomjs/9aI5d-LDuNE)說明，因為 Headless Chrome推出，PhantomJs也算功成身退了。

[Headless Chrome](https://github.com/GoogleChrome/puppeteer) a.k.a puppeteer 由 Google 維護，當然能獲得的資源更多，支援也會更全面，在自動化網頁測試的領域可以直接使用 puppeteer。

