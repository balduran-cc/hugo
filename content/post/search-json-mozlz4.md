+++
author = "Balduran Chang"
categories = ["mozilla", "search", "firefox", "developer", "json"]
date = 2017-06-27T09:53:09Z
description = ""
draft = false
slug = "search-json-mozlz4"
tags = ["mozilla", "search", "firefox", "developer", "json"]
title = "search.json.mozlz4"

+++


Firefox 從 FF45 開始，不再使用 searchplugins  folder，改用 search.json.mozlz4 這個檔案。讀取這個檔案是有點麻煩的，原因是這個檔案並不是一般的 LZ4 壓縮檔，它是 Mozilla 客製化的版本。

Mozilla 客製化的方法就是在header加入幾個 [Magic Number](https://dxr.mozilla.org/mozilla-central/source/toolkit/components/lz4/lz4.js#28)， 這個 Magic Number 就是 `mozLz4a\0`，去掉這些字元之後才是正常的 LZ4 格式。

估計這樣的設計，是不要讓其他程式可以讀取 Firefox的設定，而這個非標準格式，也有 [ticket 在討論](https://bugzilla.mozilla.org/show_bug.cgi?id=1209390)。

reference:
[LZ4.js](https://dxr.mozilla.org/mozilla-central/source/toolkit/components/lz4/lz4.js#28)

