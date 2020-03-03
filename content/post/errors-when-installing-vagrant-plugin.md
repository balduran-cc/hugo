+++
author = "Balduran Chang"
categories = ["gem", "mac", "vagrant", "ruby", "nokogiri"]
date = 2015-05-05T04:11:43Z
description = ""
draft = false
slug = "errors-when-installing-vagrant-plugin"
tags = ["gem", "mac", "vagrant", "ruby", "nokogiri"]
title = "Errors when installing vagrant plugin"

+++


Vagrant 有很多 [providers](http://docs.vagrantup.com/v2/getting-started/providers.html) 可以運用，不只是預設的 VirtualBox，其他 VPS[^VPS] 也可以和 Vagrant 串接，例如 [AWS](https://github.com/mitchellh/vagrant-aws) 和 [DigitalOcean](https://github.com/smdahlen/vagrant-digitalocean)。我自己在試著用 [DigitalOcean] 的時候遇到了問題

[^VPS]: Virtual Private Server

[DigitalOcean]: https://m.do.co/c/3663792798f1


## 照著tutorial
首先 follow [DigitalOcean] 上的 [Tutorial](https://www.digitalocean.com/community/tutorials/how-to-use-digitalocean-as-your-provider-in-vagrant-on-an-ubuntu-12-10-vps)，看似簡單，只要
```
vagrant plugin install vagrant-digitalocean
vagrant box add digital_ocean https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box
```
但我的 mac 上卻給出了 nokogiri 相關的錯誤訊息。

## 安裝 nokogiri
> An error occurred while installing nokogiri (1.6.6.2), and Bundler cannot continue.
> Make sure that `gem install nokogiri -v '1.6.6.2'` succeeds before bundling.

當然，這個訊息提示了我們需要安裝 nokogiri，搭配 rbenv 來安裝 nokogiri 是建議做的做法，也比較乾淨。但無獨有偶，`gem install nokogiri` 也還是出現了錯誤。

> Building native extensions.  This could take a while...
> Successfully installed nokogiri-1.6.6.2
> Parsing documentation for nokogiri-1.6.6.2
> unable to convert "\xCF" from ASCII-8BIT to UTF-8 for lib/nokogiri/nokogiri.bundle, skipping
> 1 gem installed

翻翻查找 [nokogiri tutorial](http://www.nokogiri.org/tutorials/installing_nokogiri.html)，卻沒什麼幫助。

試著
```sh
gem install rdoc
gem install nokogiri
```

試著看看 nokogiri版本號。
`nokogiri --version`
如果有顯示ruby, limxml的路徑應該就沒什麼問題了。

最後的最後，如果直接執行```vagrant plugin install vagrant-digitalocean```也還是會有錯誤的話。

## 使用系統函式庫
```
NOKOGIRI_USE_SYSTEM_LIBRARIES=1 vagrant plugin install vagrant-digitalocean
vagrant box add digital_ocean https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box
```

