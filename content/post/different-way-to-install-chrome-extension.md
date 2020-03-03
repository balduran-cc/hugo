+++
author = "Balduran Chang"
categories = ["extension", "chrome", "registry"]
date = 2016-05-30T08:43:54Z
description = ""
draft = false
slug = "different-way-to-install-chrome-extension"
tags = ["extension", "chrome", "registry"]
title = "different way to install chrome extension"

+++


##安裝 chrome extension 的幾種方法

一般的使用者都會是直接連到 [Chrome Web Store][]，搜尋特定 extension 然後安裝。

還有[其他種方式](https://developer.chrome.com/extensions/external_extensions)適用其他情境。

1. [inline JS](https://developer.chrome.com/webstore/inline_installation)

 可以直接使用 js trigger chrome 安裝 extension，適合用在 promotion page上，user 不用轉換頁面，同時埋入 analytics code可以分析轉換率。

 `chrome.webstore.install(url, successCallback, failureCallback)` 對於 JS developer 應該不陌生，不贅述。
 
2. [preferences JSON file](https://developer.chrome.com/extensions/external_extensions#preferences)

 Mac OS 和 Linux適用，如果 extension 經由單機軟體散佈，那就需要用這個方法。假設要安裝的extension ID 是 aabbccddee，那麼在 `~USERNAME/Library/Application Support/Google/Chrome/External Extensions/` 或 `/usr/share/google-chrome/extensions/ 
` 寫入一個 aabbccddee.json，裡面內容寫明 `external_update_url`，在 chrome 下次啟動的時候，會跳出一個小 popup windows問你要不要啟動這個 extension。

3. [Windows registry](https://developer.chrome.com/extensions/external_extensions#registry)

 Windows上也有類似的方法，不過寫入的地方是 windows registry，需要用 C++ 之類的語言寫入 registry key。在 `HKEY_LOCAL_MACHINE\Software\Google\Chrome\Extensions`下開一個 new key，key name 就是 aabbccddee (extension ID)，在這個 key 之下也需要指定 `update_url`，同樣地，chrome每次啟動的時候就會掃這些 metadata，然後試著安裝或更新 extension。
 
這些方法都是為了能夠讓 extension 開發者可以將安裝的權力從 chrome web store 拉出來，有更多的選擇性。
 
[Chrome Web Store]: https://chrome.google.com/webstore/category/extensions

