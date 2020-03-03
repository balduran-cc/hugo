+++
author = "Balduran Chang"
categories = ["SSH", "tunnel", "remote", "developer"]
date = 2007-10-05T06:30:55Z
description = ""
draft = false
slug = "ssh-tunnels"
tags = ["SSH", "tunnel", "remote", "developer"]
title = "SSH tunnels"

+++


同事 Kcc教了我從家中電腦遠端連進辦公室電腦的方法，不是用VPN，是用SSH進入院內一台主機，在forward到我使用的電腦，然後用windows內建的遠端桌面連線。

[SSH Tunnel](http://stefan.huberdoc.at/comp/info/ssh_tunnel.html "sth - SSH Tunnel")我之前沒接觸過，一直想了解三台機器的關係，似乎是本機的 Source port經由和 Host的 SSH連線連到 destination，以遠端桌面為例 destination的 port是3189，Source port是自訂，在開啟遠端桌面連線時候鍵入 127.0.0.1:source port就可。

如果我早一點知道這一招就好了，之前在環保局都是用 port 443連線，不過前提是要有一台 SSH Server可以連線。  
[由http暗藏通道看網路安全](http://www-128.ibm.com/developerworks/tw/library/l-httpunnel/ "由http暗藏通道看網路安全")、[FreeBSD GIF Tunnel](http://ylchang.blogspot.com/2005/09/freebsd-gif-tunnel.html "ylchang - BBBbbbbb.....loggggggg: FreeBSD GIF Tunnel")講的是不是同一件事情呢？

Msn: 1080 dynamic勾選，destination空白  
 IE: 8080 destination:192.168.0.1:3180(??)  
 OE: Source: 25(smtp),110(pop3)

