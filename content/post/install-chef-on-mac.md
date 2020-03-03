+++
author = "Balduran Chang"
categories = ["mac", "chef", "install"]
date = 2015-12-06T22:32:23Z
description = ""
draft = false
slug = "install-chef-on-mac"
tags = ["mac", "chef", "install"]
title = "install chef on mac"

+++


1. download chef
https://downloads.chef.io/chef-dk/mac/

1. xcode-select --install
check the xcode command line tools

1. check shell is bash and bash_profile
`echo 'eval "$(chef shell-init bash)"' >> ~/.bashrc`


1. check ruby and gem
 `which ruby` should be `/opt/chefdk/embedded/bin/ruby`

 `which gem` should be `/opt/chefdk/embedded/bin/gem`

 `echo $GEM_PATH` should be like `/Users/<you>/.chefdk/gem/ruby/2.1.0:/opt/chefdk/embedded/lib/ruby/gems/2.1.0`

1. check version

 `knife -v`

 `kitchen -v`

 `chef -v`

1. install bundler
 `gem install bundler`

