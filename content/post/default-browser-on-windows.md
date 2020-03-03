+++
author = "Balduran Chang"
categories = ["browser", "windows", "registry"]
date = 2016-06-28T01:53:08Z
description = ""
draft = false
slug = "default-browser-on-windows"
tags = ["browser", "windows", "registry"]
title = "windows 上的 default browser"

+++


需要知道使用者的 [default browser](https://msdn.microsoft.com/en-us/library/windows/desktop/dd203067%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) 的話，可以讀取 `\SOFTWARE\Clients\StartMenuInternet` 這個 registry key。如果是一台全新的 windows，這時候 HKEY_CURRENT_USER 應該沒有這個值，在 HKEY_LOCAL_MACHINE 下預設是 IEXPLORE.EXE。

隨著安裝 Firefox 或是 Chrome，會在 `HKEY_LOCAL_MACHINE\SOFTWARE\Clients\StartMenuInternet` 下增加 subkey，每個 subkey 的 `shell\open\command` 就會是指到瀏覽器的路徑。

使用者自己更改了 default browser 的話，就會在 HKEY_CURRENT_USER 下面新增 `\SOFTWARE\Clients\StartMenuInternet`，並且寫入新的 browser value。

不過這個 registry 在 Win10 上有點問題，如果設定 Edge 為 default browser 但是這個 registry key 還會是寫 IEXPLORE.EXE。

