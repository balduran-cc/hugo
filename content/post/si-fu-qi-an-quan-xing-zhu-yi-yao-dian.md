+++
author = "Balduran Chang"
categories = ["php", "apache", "server", "security"]
date = 2015-06-02T02:17:09Z
description = ""
draft = false
slug = "si-fu-qi-an-quan-xing-zhu-yi-yao-dian"
tags = ["php", "apache", "server", "security"]
title = "伺服器安全性注意要點"

+++


##php.ini 增強安全性

1. disable_functions =exec,passthru,shell_exec,system,proc_open,popen,curl_exec,curl_multi_exec,parse_ini_file,show_source

1. allow_url_fopen=Off

1. allow_url_include=Off

1. expose_php=Off
http header (X-Powered-By) 不帶php info

1. load less modules
php -m 可看 module 列表
rename 副檔名 ini 成 disable
`mv /etc/php.d/sqlite3.ini /etc/php.d/sqlite3.disable`

1. display_errors=Off
lod error 但不讓 end user 看到

1. file_uploads=Off
關閉上傳檔案，如果必要，限制檔案大小
```
file_uploads=On
upload_max_filesize=1M
```

1. sql.safe_mode=On

1. magic_quotes_gpc=Off

1. 避免執行過久，耗用資源，避免阻斷攻擊 DoS
```
max_execution_time =  30
max_input_time = 30
memory_limit = 40M
```

1. cgi.force_redirect=On

1. open_basedir="/var/www/html/"
限制 open_basedir，只開放必要的folder

## apache 增強安全性
1. 避免 root 身份執行 apache server
`chown -R apache:apache /var/www/html/`
/var/www/html/ 下的檔案權限 0444
/var/www/html/ 下的目錄權限 0445

1. Jails
應用虛擬化技術，Freebsd Jail, XEN, KVM or openVZ. 將伺服器跑在一個虛擬環境中

1. 伺服器依照用途分類
   1. static asset
   2. php (cgi), 動態內容產生
   3. mysql，資料庫
   4. memcache，快取層，架在資料庫前面
   5. proxy and reverse proxy server，擋在所有機器前面，做 load balance。

1. http://httpd.apache.org/docs/current/misc/security_tips.html
apache 的 security tips

