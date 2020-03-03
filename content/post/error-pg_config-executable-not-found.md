+++
author = "Balduran Chang"
categories = ["mac", "postgresql", "error", "pip"]
date = 2014-12-27T19:14:00Z
description = ""
draft = false
slug = "error-pg_config-executable-not-found"
tags = ["mac", "postgresql", "error", "pip"]
title = "Error: pg_config executable not found."

+++


當使用pip安裝psycopg2遇到了以下錯誤

>     Error: pg_config executable not found.  
>     Please add the directory containing pg_config to the PATH  
>     or specify the full executable path with the option:  
>         python setup.py build_ext –pg-config /path/to/pg_config build …  
>     or with the pg_config option in ‘setup.cfg’.  
>     Complete output from command python setup.py egg_info:  
>     running egg_info

如果是用brew管理套件，可以安裝postgresql解決。
```
brew install postgresql
```

接著可能需要
```ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents``` 可以讓系統啟動時啟動postgresql

如果需要馬上啟動，```launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist```

如果不想加入系統啟動清單，單次執行，```postgres -D /usr/local/var/postgres```

另外有個應用程式可以安裝，不用打指令，http://postgresapp.com 。

