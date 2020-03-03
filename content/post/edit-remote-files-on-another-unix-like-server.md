+++
author = "Balduran Chang"
categories = ["developer", "IDE", "sublime", "editor", "tools", "remote", "sftp"]
date = 2014-03-13T11:56:00Z
description = ""
draft = false
slug = "edit-remote-files-on-another-unix-like-server"
tags = ["developer", "IDE", "sublime", "editor", "tools", "remote", "sftp"]
title = "Edit remote files on another UNIX-like server"

+++


做開發工作，處理的系統一旦龐大，往往會蓋自己的開發機器，而不是用本機（不論是Mac, linux or Windows）建立伺服器，原因往往跟套件管理，機器權限管理有關。

大公司都有自己 inhouse 的套件管理，登入機器的權限管理與使用者管理也自有一套系統。想要用原生的 Mac建成類似的系統並且接上各個後端，是吃力不討好。

有些硬派開發者會標榜使用 Vim 無敵，當然這也是一個選項，但是我自己會儘量嘗試各種 IDE或 editor。

想要在本機編輯完程式檔案之後，直接使用開發機器驗證，有幾種方式。

1. [Aptana](http://aptana.com/products/studio3)  
免費版本的就可以直接設定SFTP存取，即時把檔案拉下來編輯的做法。

2. sublime with sftp plugin  
sublime 也是很方便的編輯器，但是只能編輯本地端檔案，折衷的方式安裝[sftp plugin](http://wbond.net/sublime_packages/sftp)，設定local folder 和 remote folder sync，同時開啟 [upload_on_save](http://wbond.net/sublime_packages/sftp/settings#setting-upload_on_save)選項，可以保證在每次存檔的時候就上傳到開發機。

3. Mount NFS  
直接開發機的目錄掛到本機，並使用自己熟悉的編輯器修改。其中mount的方式也有各種不同。  
a. finder mount   
[finder->go->connect to server(cmd+K)](http://support.apple.com/kb/PH10644) 有點麻煩 常常需要重新掛，下shell command的話異常慢。更正：[登入後自動掛載](http://support.apple.com/kb/HT4011)  
b. MacFusion  
[MacFusion](https://www.macupdate.com/app/mac/24768/macfusion) 是 [MacFuse](https://www.macupdate.com/app/mac/23729/macfuse) 的圖形化界面，特定版本搭配才ＯＫ，但我忘了是哪些版本。更新：根據[fuse for OS X](http://osxfuse.github.io/)，MacFuse 已經停止維護。[wiki](https://github.com/osxfuse/osxfuse/wiki)頁面有詳細說明。[Note for Mountain Lion](https://github.com/mgorbach/macfusion2/issues/32)

4. Rsync  
寫成bash command，用automator跑或是 Alfred workflow(需付費）執行。

