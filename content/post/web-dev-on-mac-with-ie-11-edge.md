+++
author = "Balduran Chang"
categories = ["browser", "IE", "webdev"]
date = 2015-10-28T10:16:11Z
description = ""
draft = false
slug = "web-dev-on-mac-with-ie-11-edge"
tags = ["browser", "IE", "webdev"]
title = "web dev 如何在 Mac 上使用 IE 11 (Edge)"

+++


## 跨瀏覽器
Web dev 的工作本來就常常需要跨瀏覽器，就算是 Mac user 也要知道一些方法可以 debug IE 11 ([Edge])。

[Edge]: https://www.microsoft.com/en-us/windows/microsoft-edge


## Virtual machines
比較耗資源，但也是最直覺的解法，就是裝一個 windows VM，但要買一個 windows 的授權也是一筆錢（守法），所幸微軟現在就有提供[免費的 VM images][MSVM]。

VirtualBox, Vagrant, VMware and Parallels 的映像檔都有提供。
[MSVM]: https://dev.modern.ie/tools/vms/mac/

## remote desktop
另一個方法，就是使用雲端資源啦，微軟也是大力地在推 Azure，其中就有一項是 [RemoteIE]。

[RemoteIE]: https://remote.modern.ie/

1. 先安裝 [remote-desktop]

[remote-desktop]: 
https://itunes.apple.com/us/app/microsoft-remote-desktop/id715768417

2. 打開 remote desktop，登入 Azure remoteApp

3. 同意 IE Technical Preview 的權限，直接打開就是一個遠端的 IE囉！

## BrowserStack
[BrowserStack]同樣也是一個雲端服務，只是專攻跨瀏覽器測試，有 free tier，一個月可用 25 分鐘免費，可選擇的瀏覽器非常多，手機桌機都有，瀏覽器版本也非常齊全。

[BrowserStack]: https://www.browserstack.com/

## 選擇哪一種較好
以上的方法，在功能的開發期間最適合用的就是 VM了，如果程式還在本機上的話。

如果已經是上線的功能或網站，那用雲端方案是最方便的。

