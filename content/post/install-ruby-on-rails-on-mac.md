+++
author = "Balduran Chang"
date = 2015-08-18T03:35:45Z
description = ""
draft = true
slug = "install-ruby-on-rails-on-mac"
title = "Install ruby on rails on mac"

+++


1. install homebrew

2. install ruby
brew install rbenv ruby-build

rbenv install 2.2.2
rbenv global 2.2.2
ruby -v

3. install rails
gem install rails -v 4.2.1
rbenv rehash
rails -v

4. start one
```
rails new myapp

#### If you want to use MySQL
rails new myapp -d mysql

#### If you want to use Postgres
# Note you will need to change config/database.yml's username to be
# the same as your OSX user account. (for example, mine is 'chris')
rails new myapp -d postgresql

# Move into the application directory
cd myapp

# If you setup MySQL or Postgres with a username/password, modify the
# config/database.yml file to contain the username/password that you specified

# Create the database
rake db:create

rails server
```

5. visit localhost
http://localhost:3000

