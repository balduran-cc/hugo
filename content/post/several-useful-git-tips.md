+++
author = "Balduran Chang"
categories = ["developer", "tips", "cli", "git"]
date = 2015-03-15T20:38:01Z
description = ""
draft = false
slug = "several-useful-git-tips"
tags = ["developer", "tips", "cli", "git"]
title = "several useful git tips"

+++


1. 需要從別人的branch延伸功能  
`git checkout -b featureA –track remote/featureA`
  
  或是設定upstream為remote branch
  * git v1.7 可用
  ```
  git br –set-upstream feature origin/featureA
  ```
  
  * git v1.8 有更直覺的語法  
  ```
  git br –set-upstream-to origin/featureA  
  git br -u origin/featureA
  ```

1. push branch 之前精簡曾有的commit log  
gire rebase -i HEAD~5  
精簡五個commit

1. 將本地端 branch featureA推到遠端  
git push origin featureA

1. 刪除github上的已存在的branch  
git push remote :featureA  
git branch -d -r remote/featureA

1. revert 前一個commit  
git reset –soft HEAD^

1. 顯示目前 branch 的 upstream  
git rev-parse –abbrev-ref –symbolic-full-name @{u}  
git branch -vv （版本 1.8+)

1. 如果rebase/merge/pull 出現 diverge  
先檢查commit history  
git log HEAD..origin/master

