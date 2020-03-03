+++
author = "Balduran Chang"
categories = ["CI/CD", "build", "automation"]
date = 2015-12-21T09:27:54Z
description = ""
draft = false
slug = "race-condition-in-component-build"
tags = ["CI/CD", "build", "automation"]
title = "race condition in component build"

+++


CI/CD 是軟體業界頗熱門的字詞，觀念是一路從 CI ([Continuous integration](https://en.wikipedia.org/wiki/Continuous_integration)) 延續到 CD ([Continuous delivery](https://en.wikipedia.org/wiki/Continuous_delivery))，公司也強制推動這一個 flow，所有的 project 都要自動化。

剛好發現一個 CD pipeline設計時候要注意的點。

原本的流程是

1. setup container
2. init environment, pull git changes
3. init script by user
4. update version number
5. build package(maven, or grunt or gulp)
6. distribute artifact
7. git push (update repo)

一切順利的話，component build 不會有 code conflict，但如果連續 merge 兩個 PR，第一個 PR 在第四步 update version number 之後，第二個 PR 才 merge，接著第一個 PR 在第七步要 git push 的時候，有可能會失敗。

如果 git push command 寫成`git push origin` 的話，那就會 build failed了，因為這時候 build machine上的 git branch 已經落後 source repo了。

這時候 git push command 要彈性一點，update version 時候只更動最少的檔案，減少 automation update version 造成的 code conflict。在 git push 之前，多一步 git pull upstream 以避免 conflict。

在第五步 build 完 package 之後，建議馬上寫回 source code，讓 git pull & push 中間執行的工作單純一點。

