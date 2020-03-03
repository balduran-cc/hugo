+++
author = "Balduran Chang"
categories = ["bash", "shell", "cli", "homebrew"]
date = 2014-08-19T11:25:00Z
description = ""
draft = false
slug = "change-default-shell"
tags = ["bash", "shell", "cli", "homebrew"]
title = "change default shell"

+++


Mac OS X預先安裝的bash版本是 3.2.x，已經是非常老舊的版本了，很多 linux的預載版本都已經是 4.1以上，建議是[使用 brew](/2013/03/30/use-homebrew-on-mac/) 安裝新版的 bash。

```
brew install bash
```
會安裝到 /usr/local/bin/ 下

可檢查 $BASH_VERSION 變數，確認版本

如果要更改系統預設的 login shell，需把shell location 加到 /etc/shells 裏，可以直接 sudo vim或是 echo ‘/usr/local/bin/bash’ >> /etc/shells

之後再執行 [chsh](http://en.wikipedia.org/wiki/Chsh) 就可以更改自己登入後的預設shell了，範例語法`chsh /usr/local/bin/bash balduran`，之後再輸入密碼就會更改預設shell。

