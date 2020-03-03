+++
author = "Balduran Chang"
categories = ["vagrant"]
date = 2016-05-29T23:48:27Z
description = ""
draft = false
slug = "vagrant-introduction"
tags = ["vagrant"]
title = "Vagrant - introduction"

+++


## vagrant

開發人員在每個案子的最開頭，一定會遇到一件事，那就是建立開發環境。建立開發環境，在古早的時期，先是自己拿一台閒置的桌機或筆電，看是要裝 ubuntu 還是 debian，或是 Microsoft 系列的 windows server，基本上，就是一台電腦專職作開發用途。

到了後來有[虛擬機](https://en.wikipedia.org/wiki/Virtual_machine)的時候，開始了切割開發環境和一般使用兩種情境，不過這件事情大多是發生在進入業界以後，在學校，老師教導學生都不會提到這類方便的做法。這種作法就是靠 [VirtualBox](https://www.virtualbox.org/) 或是 [VMware](http://www.vmware.com/) 這類的虛擬機器軟體，切割出一台虛擬機，裡面只安裝開發環境所需要的軟體，而且也可以隨時開關，唯一的缺點，就是吃資源，需要一台夠有力的機器跑虛擬機。

虛擬機固然是一個很不錯的選擇，但如果所開發的軟體需要各種不同的環境下測試，例如開發網站的 web developer需要在 IE6, IE7, IE8, IE9, IE10 and IE11 and [Edge browser](https://www.microsoft.com/en-us/windows/microsoft-edge)，那就要安裝七個 windows 虛擬機，數量一多，實在累人。

面臨一堆的虛擬機要管理，這時候就需要小工具，[Vagrant](https://www.vagrantup.com/)就是這樣一個超方便的工具，他可以很方便快速的設定好虛擬機器，無論是架設開發環境或是用來重現測試環境，都很容易。

## Vagrant 的使用
Vagrant 支援多種虛擬機的格式，舉凡 VirtualBox、VMware、AWS、Hyder-V 或是 Docker 都支援。使用上也很簡單，安裝好 Vagrant 後直接下個命令

```
$ vagrant init hashicorp/precise64
$ vagrant up
```
就會自動下載 Ubuntu 12.04 LTS 64-bit 並且啟動。


只要在下個 `vagrant ssh` 就可以登入這台虛擬機器，如果想要砍掉這個虛擬機，只要 `vagrant destroy` 就可以無痕摧毀了。

