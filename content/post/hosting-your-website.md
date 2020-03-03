+++
author = "Balduran Chang"
categories = ["web", "hosting", "domain", "DNS", "godaddy"]
date = 2017-01-17T03:23:55Z
description = ""
draft = false
slug = "hosting-your-website"
tags = ["web", "hosting", "domain", "DNS", "godaddy"]
title = "自行架站要點"

+++


## 購買網域
又稱買網址、網域註冊。
可從 [GoDaddy][] 註冊或是 [hinet網域註冊][]，自己可以接受的價格就可以買了。

註冊網域之後，這個網域就屬於你了，可以從一些工具查到網域擁有者的名字，地址與使用的 DNS server。

例如 [http://whois.domaintools.com/](http://whois.domaintools.com/) 查詢yahoo.com 是登記在 Yahoo! inc這個組織之下，如果是個人使用的網址，就會是個人的資料。

附帶一提，這裏看到的 ip address 有可能是前面一層 DNS 的 ip。

喜歡使用指令的話，`whois hinet.com`

## 設定 DNS
網域商通常有提供 DNS 服務，但不一定要放在網域商上，有很多地方都提供 DNS服務，虛擬主機、CDN 或是 ISP，當然也可以自己架。

網域商會導向網址註冊的 DNS 伺服器，DNS 收到之後會開始正反解，DNS 用來轉換主機名稱到 ip address，有階層概念，可以自己架設也可以使用ISP或網域廠商提供，頂層從網域商指定DNS server，裡面在各自指向小網域。

例如 fr.news.yahoo.com，yahoo.com 是網域，fr.news 就是 subdomain，subdomain 可以自己任意指定。

最平常用的設定就是 A 與 CNAME，A 是直接連結 subdomain 與 ip，CNAME 是連結 subdomain 和另一個網址，類似別名的概念。

指令可以用

1. host -a us.yahoo.com
1. nsloopup us.yahoo.com
1. dig us.yahoo.com

[Godaddy]: https://www.godaddy.com/
[hinet網域註冊]: https://domain.hinet.net/

