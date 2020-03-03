+++
author = "Balduran Chang"
categories = ["developer", "mac", "tools", "rbenv"]
date = 2015-05-05T04:37:15Z
description = ""
draft = false
slug = "rbenv-on-mac"
tags = ["developer", "mac", "tools", "rbenv"]
title = "rbenv on mac"

+++


`gem install xxxyyy` 大概是要在mac安裝些軟體時候會需要做的動作，安裝相依性套件，但是！！ 升級到 10.10 mac很容易跑出這樣的錯誤給你看。

> ERROR:  While executing gem ... (Gem::FilePermissionError)
>     You don't have write permissions for the /Library/Ruby/Gems/2.0.0 directory.

意思是`/Library/Ruby/Gems/2.0.0`無權限寫入，當然啦！這是root所有的目錄，通常一般人也就用`sudo gem install xxxyyy`來解決，但這並不是一個很好的方法。

建議用 [rbenv](https://github.com/sstephenson/rbenv/)來管理ruby的環境，隔離系統內建的ruby(2.0)與開發時候所使用的版本，開發的環境往往需要新舊共存，這樣就不會污染到系統內建的函式庫。

而 rbenv又可以由 [brew](/2013/03/30/use-homebrew-on-mac/) 來管理，使用 brew 來安裝 rbenv，然後使用 rbenv 來管理 ruby 開發環境 。

```
brew install rbenv ruby-build
#記得安裝完後要將`eval "$(rbenv init -)"` 加入到 bash_profile
```

`rbenv install -l`
可以查看可供下載的ruby版本

`rbenv install 2.0.0-p247`
install 2.0.0-p247

`rbenv versions`
list all installed version

`rbenv global 2.0.0-p247`
設定 2.0.0版為預設使用版本

之後在執行 `gem install xxxyyy` 的時候就不會嘗試寫入到 system ruby 了

