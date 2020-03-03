+++
author = "Balduran Chang"
categories = ["cookie", "javascript", "yui"]
date = 2014-07-21T11:06:00Z
description = ""
draft = false
slug = "write-cookie-in-js-level"
tags = ["cookie", "javascript", "yui"]
title = "Write Cookie in JS level"

+++


通常我們寫入cookie是直接使用[setrawcookie](http://php.net/manual/en/function.setrawcookie.php)，當然安全性是個問題，在此先不討論。  
setrawcookie有個要注意的事項是他必須在http response出去之前就被呼叫，因為他是[header的一部份](http://en.wikipedia.org/wiki/HTTP_cookie#Setting_a_cookie)，因此呼叫setrawcookie時要注意return value，或是自己必須確保呼叫之前沒有任何echo。

如果setcookie所要寫入的值是來自于另一個後端，而且這份資料並不是一定要在header建立cookie，為了不讓這個後端擋住前端機器吐頁面，我們可以讓他inline setup cookie。

sample PHP code  
$cookie = array(  
    ‘name’          => $name,  
    ‘value’         => $value,  
    ‘expiration’    => $expiration,  
    ‘path’          => $path,  
    ‘domain’        => $domain  
);

$cookie[‘expiration’] *= 1000;  // from seconds to mileseconds  
$config = json_encode($cookie);  
$script = <<EOS;  
<eos p="">Y.use(‘cookie’, function(Y){</eos>  
<eos p="">    setcookie = function(config){  
        Y.Cookie.set(config.name, config.value, {  
            expires: new Date(config.expiration),  
            path: config.path,  
            domain: config.domain  
        });  
    };  
    setcookie($config);  
});  
EOS;  
</eos>

<div>echo $script;</div><div></div>讓php準備好要寫入的值（簽核加密等等），再讓簡單的anonymous function寫入。這樣不容易debug，需斟酌。

其中需要注意的是，php 生成的 [date()](http://php.net/manual/en/function.date.php) 和 javascript [new Date()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) 的基本單位不同，從 php 傳遞到 js 的時候需要乘以1000。

如果有指定expires time，cookie 就不應該是 session cookie。  
<span style="background-color: white; color: #333333; font-family: 'PT Sans', 'DejaVu Sans', 'Bitstream Vera Sans', Verdana, sans-serif; font-size: 14px; line-height: 19.600000381469727px;">Since this cookie is created with all of the default settings, it becomes a session cookie. from [YUI](https://yuilibrary.com/yui/docs/cookie/)</span>

