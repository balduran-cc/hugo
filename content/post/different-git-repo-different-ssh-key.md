+++
author = "Balduran Chang"
categories = ["SSH", "tips", "git"]
date = 2016-01-21T03:55:02Z
description = ""
draft = false
slug = "different-git-repo-different-ssh-key"
tags = ["SSH", "tips", "git"]
title = "different git repo, different ssh key"

+++


一般來說，git 的 user 設定只要會是自己，所有的 commit 也都是自己的名字。不過剛好工作上有需要用一個共用的 github account 來和另一家公司合作，流程是我方需要隨著對方版本的更新而更新，更新的內容主要就是版號而不是程式實做的更動。

當每一次對方要出新版之前，我方就要先拉下對方新版程式碼，更新我方程式中的版本號，進行測試，測試完成則使用 github 發 PR 給對方，對方會將我方的程式碼納進下次要發行的新版本。

我想要簡化 commit 的時候要輸入共用 github account 的流程，就開始設定 ssh config，同時也做了一個 key for this shared account。

```
Host github_partner
User git
HostName github.com
IdentityFile ~/.ssh/partnerKey
```

在 fork 對方 git repo 之後，直接 clone 下來的 remote url 會是 `https://github.com/xxxteam/myrepo.git` 或是 `git@github.com:xxxteam/myrepo.git`，直接用這組 url 來 push 的話，還是會要你輸入帳號密碼。

試著將 `git@github.com:xxxteam/myrepo.git` 改成 `git@ github_partner:xxxteam/myrepo.git`就會直接使用 ssh config 裡面的 key了，要更簡化的話，`github_partner:xxxteam/myrepo.git`。

