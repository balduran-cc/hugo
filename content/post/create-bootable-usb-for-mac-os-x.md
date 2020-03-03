+++
author = "Balduran Chang"
categories = ["mac OS X", "USB", "tools"]
date = 2015-12-23T22:16:50Z
description = ""
draft = false
slug = "create-bootable-usb-for-mac-os-x"
tags = ["mac OS X", "USB", "tools"]
title = "create bootable USB for mac OS X"

+++


以前都還有光碟，現在的時代筆電都不配光碟了，用 USB 做個開機碟還比方便。

需要一個至少 8G的隨身碟，大於 8G 的其他空間在做成開機碟之後就不能用，所以，就用個剛好 8G 的 USB disk。

簡單作法，用 [DiskMaker X](http://liondiskmaker.com/)，目前支援 10.9, 10.10 and 10.11 的 mac OS X，這個方法推薦給一般使用者。

For [commandline](https://support.apple.com/en-ap/HT201372) lover

1. download 10.11 installer from App Store
2. `sudo /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia--applicationpath /Applications/Install\ OS\ X\ El\ Capitan.app --volume /Volumes/MyVolume`
 其中的 MyVolume要改成自己的隨身碟 path
 
開機之後，按住 option 鍵，就可以選用 USB開機，並且安裝。

2018/1/15 更新：
請直接參考 [Apple 說明頁面](https://support.apple.com/zh-tw/HT201372)，有詳細指令範例。

