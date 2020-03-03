+++
author = "Balduran Chang"
categories = ["mac OS X", "cli", "NTFS"]
date = 2015-06-19T20:09:39Z
description = ""
draft = false
slug = "readwrite-ntfs-on-mac-os-x"
tags = ["mac OS X", "cli", "NTFS"]
title = "read/write NTFS on MAC OS X"

+++


## 讀取NTFS 檔案系統
[NTFS](https://www.wikiwand.com/en/NTFS) 是微軟研發的檔案系統，如果外接硬碟是用 Windows 格式化，那九成是採用 NTFS，而這個檔案系統，MAC 是能讀不能寫，如果要用外接硬碟分享檔案，就需要安裝額外的驅動程式讓 MAC 可以寫入。

## 付費方案

1. [http://www.paragon-software.com/tw/home/ntfs-mac/](http://www.paragon-software.com/tw/home/ntfs-mac/)
NT 550元，花錢是最快最直接的方式，

2. [Tuxera NTFS for mac](http://www.tuxera.com/products/tuxera-ntfs-for-mac/)
31 USD，看起來是 NTFS-3G project 的[商業版本](http://www.tuxera.com/about-us-2/)。

## 免費方案
1. Download [Fuse for OS X](http://osxfuse.github.io/)
[MacFUSE](https://code.google.com/p/macfuse/) 停止開發後的繼任者。

2. Download [NTFS-3G](http://macntfs-3g.blogspot.tw/2010/09/ntfs-3g-for-mac-os-x-201088.html)
停止開發了，最後一次更新是2010，

3. Download [fuse-wait](https://github.com/bfleischer/fuse_wait/downloads)
Patch for NTFS-3G，總是有好心人會發 patch

### CLI-lover
```
brew install osxfuse
brew install ntfs-3g
```

```
sudo mv /sbin/mount_ntfs /sbin/mount_ntfs.original
sudo ln -s /usr/local/Cellar/ntfs-3g/2014.2.15/sbin/mount_ntfs /sbin/mount_ntfs
```

## 參考資料
* [https://github.com/osxfuse/osxfuse/wiki/NTFS-3G](https://github.com/osxfuse/osxfuse/wiki/NTFS-3G)
* [gist](https://gist.github.com/bjorgvino/f24e5c079b92f921b765)
* [Homebrew Formulas NTFS-3G](http://brewformulas.org/Ntfs-3g)

