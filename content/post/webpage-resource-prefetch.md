+++
author = "Balduran Chang"
categories = ["webdev", "prefetch", "performance"]
date = 2015-09-08T21:01:08Z
description = ""
draft = false
slug = "webpage-resource-prefetch"
tags = ["webdev", "prefetch", "performance"]
title = "Webpage resource prefetch"

+++


Frontend peformance 一般著重的重點在於讓 resource files更小，或是各種 cahce機制(CDN or browser cache)，另一個 tuning 的方向可以是預先讀取。

## [減低解析時間][DNS prefetch]

[DNS prefetch]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Controlling_DNS_prefetching

### DNS prefetch
`<link rel="dns-prefetch" href="//abc.com">`
手動預查DNS。

## DNS prefetch control
`<meta http-equiv="x-dns-prefetch-control" content="on">`
前一項技巧是手動指定要預查的 domain，這一項則是在 meta 裡告訴瀏覽器要 prefetch domain。

### Preconnect
`<link rel="preconnect" href="http://abc.com">`
除了查DNS，也建立 TCP 連線，詳見[此文][preconnect]

[preconnect]: https://www.igvita.com/2015/08/17/eliminating-roundtrips-with-preconnect/

以上都只是針對下載 resource files的前半段動作，DNS 反查的優化，以下則是實際會下載 resource files 以備使用。
## [預先讀取][prefetch]
[prefetch]: https://developer.mozilla.org/zh-TW/docs/HTTP/Link_prefetching_FAQ
### Subresource
`<link rel="subresource" href="abc.png">`
如果是當下頁面使用的檔案，應該用 [subresource][]標明。

[subresource]: https://www.chromium.org/spdy/link-headers-and-server-hint/link-rel-subresource

### Prefetch
`<link rel="prefetch" href="abc.png" >`
先讀取並下載，但留待之後使用，適合當下頁面沒用到的檔案使用，例如其他頁面會用到的 js/css，可用此先下載，但優先權較 subresource低。

如果使用 webfont，那此技巧是最適合不過了

### prerender
`<link rel="prerender" href="http://abc.com">`
讀取 link URL 裡的所有 resource files，如同開個tab開頁面，負載非常重，如果 user 沒有進入 prerender的頁面，那頻寬完全是浪費，只有在某些情境下，使用者一定會進到下一個頁面，那用此技巧可。

