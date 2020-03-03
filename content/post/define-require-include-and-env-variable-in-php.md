+++
author = "Balduran Chang"
categories = ["programming", "php"]
date = 2016-04-22T02:10:54Z
description = ""
draft = false
slug = "define-require-include-and-env-variable-in-php"
tags = ["programming", "php"]
title = "define require include and env variable in PHP"

+++


# Env variable

如果是變數，且是敏感資料，不能 commit 進 git (version control)，那請用 envronment variable，最好舉的例子就是 DB password。

在 shell 裡 `export BD_PASSWD="Passw0rd!`，設定好環境變數，

php 裡可以用

1. [$_ENV](http://php.net/manual/en/reserved.variables.environment.php) 讀取。
2. [getenv](http://php.net/manual/en/function.getenv.php) function取的。

# define
如果是固定的字串，例如 PATH、SRC_PATH、INC_PATH，這些是固定內容的常數那就使用 define。

1. `const FOO='BAR';`
2. `define('FOO', 'BAR');`

程式原始碼或是一些include files可以放在一個共通的目錄，這時候 [define](http://php.net/manual/en/function.define.php) SRC_PATH 就很適合。

常見的組合是用 define
從環境變數設定值。
`define('DB_PASSWD', getenv('APP_DB_PASSWD'));`

# require and include
[require](http://php.net/manual/en/function.require.php) 是用來引入([include](http://php.net/manual/en/function.include.php))其他的 php檔案，如果引入失敗，會產生 FATAL error，[include](http://php.net/manual/en/function.include.php) 則只是產生 warning。

require 也會先讀取 required file 並執行，include 則是單純把檔案內容引入而已，所以有時候會看到 if/else 配合 include 使用，動態載入 某些程式(一組的變數等等)，至於使用第三人寫的library，那就使用 require

有時候會看到 `require($config.php);`，首先 require 是 statement，不需要把它當成 function，第二則是不要 require 變數。

直接寫成 `require 'SRC_PATH'. 'foo.php';`會比較推薦。

require 和 require_once的使用，如果是小project，效能沒有那麼重要，那隨意寫 require_once也不會有人跳起來，如果架構很大，那還是只使用 require吧，記憶體使用有差。

