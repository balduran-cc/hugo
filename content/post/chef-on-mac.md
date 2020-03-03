+++
author = "Balduran Chang"
date = 2015-03-12T02:57:18Z
description = ""
draft = true
slug = "chef-on-mac"
title = "Chef on mac"

+++


[Chef](https://downloads.chef.io/) 是 DevOps必學的工具（之一）。

1. `sudo gem install chef`
2. 網站[下載 installer](https://downloads.chef.io/chef-dk/mac/)

dmg_package "Google Chrome" do  
  dmg_name "googlechrome"
  source "https://dl-ssl.google.com/chrome/mac/stable/GGRM/googlechrome.dmg"
  action :install
end

zip_app_package "Mou" do  
  source "http://mouapp.com/download/Mou.zip"
end

dmg_package "Virtualbox" do  
  source "http://dlc.sun.com.edgesuite.net/virtualbox/4.1.18/VirtualBox-4.1.18-78361-OSX.dmg"
  type "mpkg"
end  

http://www.rocu.de/how-to-setup-your-mac-automatically-with-chef/
https://github.com/opscode-cookbooks/homebrew
https://docs.chef.io/install_dk.html

