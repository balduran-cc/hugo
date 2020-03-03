+++
author = "Balduran Chang"
categories = ["environment", "windows"]
date = 2016-05-06T03:36:00Z
description = ""
draft = false
slug = "env-var-windows"
tags = ["environment", "windows"]
title = "Some Environment variables on Windows"

+++


##Windows 上的環境變數

Windows 上也有環境變數可以用，有些記起來會方便許多，和 unix-like 平台不一樣，windows 的環境變數是 %變數名稱%，以 % 作為開頭與結尾。

%PATH% PATH 是查找執行檔時候的順序

%HOMEPATH% 會是 \Users\\{username}

%USERPROFILE% 則是 C:\Users\\{username}

%APPDATA% 和 %LOCALAPPDATA% 程式的 profile folder 通常是在這，差別是 roaming 或是 local

%SYSTEMROOT% 通常是 C:\Windows ，如果是 NT 那會是 WINNT
%ProgramFiles% 就是程式集的路徑，

%TEMP% 會是 C:\Users\\{Username}\AppData\Local\Temp，有時候會把程式的 log 放這裡

