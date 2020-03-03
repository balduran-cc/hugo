+++
author = "Balduran Chang"
categories = ["automation", "visual studio", "project"]
date = 2016-06-28T00:12:30Z
description = ""
draft = false
slug = "visual-studio-project"
tags = ["automation", "visual studio", "project"]
title = "Visual studio project folder"

+++


visual studio project folder 中的檔案

[.sln](https://msdn.microsoft.com/en-us/library/bb165951.aspx) 可以 commit 進 VCS[^VCS]

[.suo](https://msdn.microsoft.com/en-us/library/bb165909.aspx?f=255&MSPPError=-2147217396) 檔則不該commit 進 VCS

.vcxproj 是 [project file](https://msdn.microsoft.com/en-us/library/669zx6zc.aspx)，可以 commit，其中會標明 [project](https://msdn.microsoft.com/en-us/library/8x480de8.aspx) 的類別，例如是 Application、DLL 或是 Static Lib。

project file 可以使用 [MSBuild](https://msdn.microsoft.com/en-us/library/dd393574.aspx) 來達到自動化建置的效果，在 Jenkins 裡面設置好對應的參數 `/p:buildEnv=jenkins /p:Configuration=Release /p:Platform=Win32`，就可以用 commandline 去建置。

.user 檔案盡量避免，這是個人的設定，會覆寫 project file的設定，如果要用統一的 build system，不要有 .user 檔案。

[^VCS]: Version control system

