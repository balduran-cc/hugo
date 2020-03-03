+++
author = "Balduran Chang"
categories = ["javascript", "programming", "ajax"]
date = 2015-10-20T05:21:06Z
description = ""
draft = false
slug = "cross-domain-request-by-cors"
tags = ["javascript", "programming", "ajax"]
title = "cross domain request by CORS"

+++


#same origin 限制
[Same-origin policy][][^同源政策]是在瀏覽器上用 javascript 發動 request的時候，要求所在頁面與 requested resource需要是同個 domain，因為安全性的因素，做 ajax call 或是拉 webfont 的時候，只能向自家伺服器請求，也加深了對於應用程式開發的限制。

[Same-origin policy]: https://en.wikipedia.org/wiki/Same-origin_policy
[^同源政策]: https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Same_origin_policy_for_JavaScript "同源政策"

[CORS][][^Cross-Origin Resource Sharing] 則是解決 cross domain 的方法之一，需要將 server/client 都設定好才會成功。

[CORS]: https://en.wikipedia.org/wiki/Cross-origin_resource_sharing

[^Cross-Origin Resource Sharing]: https://en.wikipedia.org/wiki/Cross-origin_resource_sharing "Cross-Origin Resource Sharing"

# [CORS]
中文翻作跨來源資源共享，直接叫 cross domain 比較乾脆，現代的瀏覽器內建的  XMLHttpRequest 都支援，除了 js script 要寫好之外，還需要額外設定伺服器。

基本順序如下

1. JS 發出 cross-domain XHR
2. server 收到 request 檢查 header and 自身設定
3. 符合 cors 設定，回傳結果，如果設定不對，request 失敗是常有的事。

# client side 發送端
發送 request 的時候，會設定 header裡的 
1. Origin
2. Access-Control-Request-Headers (optional)
3. Access-Control-Request-Method(optional)

POST 的 contentType and dataType 很重要

1. contentType 用於發送端表明送出資料的類別，default 是
`application/x-www-form-urlencoded; charset=UTF-8`
常用的有
`application/json; charset=utf-8`

2. dataType則是期待伺服器回傳的類別，可以是 json, html or text



# server side 伺服器端
設定了 CORS 的伺服器在接到之後，會核對了Origin和自身的CORS設定後回傳
Access-Control-Allow-Headers
Access-Control-Allow-Origin
Access-Control-Allow-Credentials

 
1. Access-Control-Allow-Origin 是最主要的設定

2. Access-Control-Allow-Credentials 則是比較特別一點，根據 [MDN][mdn_cors] 上的說明，是resource 端回傳的cookie能不能被 requester 看到。通常不建議設成 true，除非這個 api endpoint 需要讀取或更新 cookie。在預防 [CSRF]的時候可以帶資訊在 user cookie

[mdn_cors]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS#Requests_with_credentials
[CSRF]: https://en.wikipedia.org/wiki/Cross-site_request_forgery


# pre-flight request

pre-flight[^先導請求] 中文有人翻譯叫做先導請求，上面的例子是最單純的 POST，如果非 GET/HEAD/POST 或是有自定 HEADER 的時候，就會是 pre-flight mode，client side 會先送一次 OPTIONS 之後看伺服器回的 Access-Control-Allow-Methods，client side 再決定要不要送真正的 request 出去。

[^先導請求]: https://developer.mozilla.org/zh-TW/docs/HTTP/Access_control_CORS#.E5.85.88.E5.B0.8E.E8.AB.8B.E6.B1.82 "先導請求"

Access-Control-Request-Headers and Access-Control-Request-Method 在這時候就會被 client side 參考了。

