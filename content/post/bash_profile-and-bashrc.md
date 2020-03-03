+++
author = "Balduran Chang"
categories = ["developer", "programming", "bash", "rcfile", "dotfile"]
date = 2016-04-19T04:10:08Z
description = ""
draft = false
slug = "bash_profile-and-bashrc"
tags = ["developer", "programming", "bash", "rcfile", "dotfile"]
title = "bash_profile and bashrc"

+++


##bash_profile 和 bashrc 的差別

對很多程式人員來說，剛接觸到 Linux (or Mac)，打開 commandline，第一個學的就是 bash(shell)，也往往會 copy 別人的 bashrc來使用。

但不多人知道 bashrc and bash_profile 的差別。

GNU 上的 [Bash manual](http://www.gnu.org/software/bash/manual/html_node/Bash-Startup-Files.html) 倒是說得很清楚，差別就在於 [interactive shells](http://www.gnu.org/software/bash/manual/html_node/What-is-an-Interactive-Shell_003f.html#What-is-an-Interactive-Shell_003f)。

##interactive shells
最簡單的判別方式就是，你敲入一個指令，然後終端機回給你結果，這個時候你就是處在一個 interactive shells。這時候輸入 `echo $-`，執行結果有 *i* 代表目前正在一個 interactive shells。

##non-interactive shells
那什麼是 non-interactive shells ?? shell script 在執行的時候，就是一個 non-interactive shells，這時shell script 處理邏輯並依序執行完，`$-`變數不會有*i*

當 bash 是以 interactive login shells 執行的時候，也就是最普遍的 `ssh hostname`的時候，他會依序讀取 
1. /etc/profile
2. ~/.bash_profile
3. ~/.bash_login
4. ~/.profile，

`.profile`檔是一開始 sh 的命名，.bash_profile 是為了相容又有所區別

如果已經登入一台機器了，這時候再打一次 `bash`，這時候還是 interactive shells，但這時已經不是 login shell(不用打密碼了這次)，這時候讀取的設定檔就是
1. ~/.bashrc

所以，很清楚的，當每一次登入伺服器需要帳號密碼認證的時候，這時候就是吃 `~/.bash_profile`，如果已經登入了，開新process執行shell，那就是吃`~/.bashrc`。

##建議寫法
最簡單的方法就是把所有的環境變數都寫在 bashrc，然後由 bash_profile引入。

```bash
if [ -f ~/.bashrc ]; then
. ~/.bashrc
fi
```

