+++
author = "Balduran Chang"
categories = ["developer", "mac", "php", "nginx", "hhvm"]
date = 2015-05-24T19:45:49Z
description = ""
draft = true
slug = "install-nginx-and-hhvm-on-mac"
tags = ["developer", "mac", "php", "nginx", "hhvm"]
title = "Install nginx and hhvm on mac"

+++


## install nginx
1. brew install nginx
2. ln -sfv /usr/local/opt/nginx/*.plist ~/Library/LaunchAgents
3. execute `launchctl load ~/Library/LaunchAgents/homebrew.mxcl.nginx.plist` or `nginx`

## install hhvm
1. tap brew version
```bash
brew tap homebrew/dupes
brew tap homebrew/versions
brew tap mcuadros/homebrew-hhvm
```
2. install hhvm
`brew install hhvm --HEAD`
or
`brew install hhvm --HEAD --with-gcc --verbose`

## install gcc
`brew install binutils`
`brew install gcc`

