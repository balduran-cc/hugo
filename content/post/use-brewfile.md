+++
author = "Balduran Chang"
categories = ["homebrew", "cli", "developer", "brewfile", "mas"]
date = 2017-12-11T23:13:00Z
description = ""
draft = false
slug = "use-brewfile"
tags = ["homebrew", "cli", "developer", "brewfile", "mas"]
title = "使用 homebrew 快速建立環境"

+++


[使用 homebrew](/2013/03/30/use-homebrew-on-mac/) 至少也有四五年，真的是 mac 上套件管理的好工具，現在連應用程式都可以幫你裝，大幅減少因為換機而需要建立環境的時間。

現在學到一個新招是使用 Brewfile 一次大量安裝自己需要的套件，概念就跟 `npm install` 一樣。

<script src="https://gist.github.com/balduran/86a60fc8480cfdcd16da6a3f3803b155.js"></script>

這是我自己的 Brewfile，只要安裝好 homebrew，再輸入`brew bundle install`就會依序安裝。

其中我也使用了 [mas-cli](https://github.com/mas-cli/mas)，用來安裝 Mac App store上的程式。

