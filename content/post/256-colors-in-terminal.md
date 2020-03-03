+++
author = "Balduran Chang"
categories = ["color", "cli", "iterm"]
date = 2015-06-21T23:24:36Z
description = ""
draft = false
slug = "256-colors-in-terminal"
tags = ["color", "cli", "iterm"]
title = "256 colors in terminal"

+++


好的 programmer(?)總是有自己喜歡的 terminal 設定，越花越好！！

## $TERM 設定
1.  Terminal setting

	[iTerm 2](http://www.iterm2.com/) or terminal 裡面 Terminfo 要設定成 `xterm-256color`

1.  screen 要支援 256 colors
	```
	brew tap homebrew/dupes
	brew install screen
	```
	系統內建的沒有支援，太老舊了，直接用 homebrew 裝新的吧

	記得 `/usr/local/bin` 要在 $PATH 前面位置

1.  screenrc 設定
	```
	attrcolor b ".I"
	termcapinfo xterm 'Co#256:AB=\E[48;5;%dm:AF=\E[38;5;%dm'
	defbce "on"
	term screen-256color-bce
	```

## 測試 shell

`for i in $(seq 0 $(tput colors) ) ; do tput setaf $i ; echo -n "█" ; done ; tput setaf 15 ; echo
`

如果出現256個漸層方塊，那設定就成功囉。

