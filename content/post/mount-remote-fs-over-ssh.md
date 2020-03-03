+++
author = "Balduran Chang"
categories = ["remote", "developer", "SSH", "mount"]
date = 2017-06-19T01:43:28Z
description = ""
draft = false
slug = "mount-remote-fs-over-ssh"
tags = ["remote", "developer", "SSH", "mount"]
title = "Mount remote FS over SSH"

+++


工作的場合中常常會需要編輯的檔案，如果是老派的程式猿，會告訴你用 VIM，我以前也是這麼想，不過現在越來越喜歡用單純的編輯器編輯本地端的檔案。

本地端的檔案和遠端伺服器之間就一定需要有同步的機制。

## SFTP
有一種做法是直接使用 FTP 軟體瀏覽遠端檔案結構，設定對應的編輯軟體，讓 FTP 軟體幫你傳送到遠端，例如 [cyberduck](https://cyberduck.io/)的功能介紹裡所說的 ```Edit any file with your preferred editor```

## Mount SSHFS
還有一種做法是將遠端伺服器 mount 到自己本地目錄下。付費軟體有 [mountainduck](https://mountainduck.io/)，免費軟體有 [macfusion2](https://github.com/mgorbach/macfusion2/issues/52)。

如果是 CMD 控可能會想要打打指令，安裝 sshfs是一定要的。Mac上則是用 [osxfuse](https://github.com/osxfuse/osxfuse)，安裝完後還要自己下 mount 指令。

1. `sudo mkdir /mnt/myfolder`
  myfolder 自訂，先開個目錄等等 mount用
2. `sudo sshfs -o allow_other,defer_permissions,IdentityFile=~/.ssh/id_rsa username@xxx.xxx.xxx.xxx:/ /mnt/myfolder`
  這樣就會用 id_rsa 去連到 xxx.xxx.xxx.xxx，並把遠端的home掛到 myfolder
3. `sudo umount /mnt/myfolder`
  不需要的時候把它移掉

不知道是不是錯覺，有時候感覺 finder 在看 sshfs目錄的時候會很頓。

## Rsync over SSH
另外一個方式是直接 Rsync，`rsync -avz -e ssh SRC DEST"`，如果很在意安全性的話，可以特別做個 ssh key出來，用`-e "ssh -i ssh_key"`去執行。

如果是 node project，一定要把 node_modules folder 放到 –exclude

