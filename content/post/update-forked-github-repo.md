+++
author = "Balduran Chang"
categories = ["git", "github"]
date = 2014-07-31T04:56:00Z
description = ""
draft = false
slug = "update-forked-github-repo"
tags = ["git", "github"]
title = "update forked github repo"

+++


Github 很方便的一點就是可以盡量fork自己會用到的library到自己的帳號下，也可以在這些forked repository 之下寫自己的模組。但是github上的 repo是不會自動從原本的repo拉更新。

有兩種做法，第一種是自己打 git command，另一種直接在github頁面上操作。

1. git command  
以 yui3 為例，原始的repo 是在 https://github.com/yui/yui3 。

```bash
$ git remote add upstream https://github.com/yui/yui3.git  
# add the remote named upstream  
$ git fetch upstream  
# fetch the latest version  
$ git rebase upstream/master  
# rebase local changes onto upstream/master

$ git push origin master  
# push to forked repo
```

2. 直接在github web介面操作  
在自己的帳號下，選擇 ‘pull requests’。  
點 ‘new pull request’，這時會出現 ‘There isn’t anything to compare.’  
選擇’switching the base’，以forked repo做為比較基底  
以此建立 pull request，在建立成功後自己merge，這樣就會把 original repo的更新merge到自己fork的repo了。

