+++
author = "Balduran Chang"
categories = ["developer", "mac", "homebrew", "package", "tools"]
date = 2013-03-30T04:34:00Z
description = ""
draft = false
slug = "use-homebrew-on-mac"
tags = ["developer", "mac", "homebrew", "package", "tools"]
title = "use homebrew on mac"

+++


[homebrew](http://mxcl.github.com/homebrew/) 是 MAC 平台上普遍使用的 package management system. 同類型的工具還有 apt & yum

安裝 homebrew 很簡單，只要在 terminal 輸入 `ruby -e “$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)”` 安裝完成就可以使用以下指令   

* brew install 安裝套件
* brew uninstall 移除套件
* brew search [foo] 安裝之前先搜尋一下
* brew list 列出已安裝套件
* brew update 更新已安裝套件
* brew upgrade 升級 homebrew


可能遇到的疑難雜症有  
* xcode 非最新版 安裝新版即可。  
* > Warning: Your compilers are different from the standard versions for your Xcode. If you have Xcode 4.3 or newer, you should install the Command Line Tools for Xcode from within Xcode’s Download preferences. Otherwise, you should reinstall Xcode. 以上錯誤訊息需要到 [ Apple downloads ](https://developer.apple.com/downloads/index.action?name=for%20Xcode%20-) 下載 command line tools  
* /usr/local 目錄權限不足 `sudo chown -R $(whoami) /usr/local`

