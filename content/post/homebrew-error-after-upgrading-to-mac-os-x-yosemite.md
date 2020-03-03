+++
author = "Balduran Chang"
categories = ["mac", "cli", "homebrew", "error", "xcode"]
date = 2014-07-29T10:16:00Z
description = ""
draft = false
slug = "homebrew-error-after-upgrading-to-mac-os-x-yosemite"
tags = ["mac", "cli", "homebrew", "error", "xcode"]
title = "homebrew error after upgrading to Mac OS X Yosemite"

+++


[Yosemite](https://www.apple.com/osx/preview/) is still in preview, everyone could join [beta program](https://appleseed.apple.com/sp/betaprogram/) and play with it.

我剛好就把 OS 升上 10.10，但遇到homebrew出現錯誤訊息。

> /usr/local/bin/brew: /usr/local/Library/brew.rb: /System/Library/Frameworks/Ruby.framework/Versions/1.8/usr/bin/ruby: bad interpreter: No such file or directory  
> /usr/local/bin/brew: line 26: /usr/local/Library/brew.rb: Undefined error: 0 

解法是

1. 安裝 xcode 6, (beta version)  
2. 安裝 command line tool

>     xcode-select –install

3. 重新安裝 homebrew

> ruby -e “$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)”

4. 安裝完成記得 brew doctor檢查一下

