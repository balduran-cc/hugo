+++
author = "Balduran Chang"
categories = ["aws", "ecs"]
date = 2020-03-01T22:57:08Z
description = ""
draft = false
slug = "ecs-agent-ports"
tags = ["aws", "ecs"]
title = "ecs agent ports"

+++


一般情境是使用AWS 提供的 ecs AMI，但有時候還是會有需要自己安裝 ecs agent 自行管理的情況。

ecs 上跑的 container 會用哪些 port呢？Docker 1.6 之後會看 /proc/sys/net/ipv4/ip_local_port_range，如果找沒有的話就會用預設值，預設是 49153 到 65535。

Docker 1.6 之前的版本則是固定使用 49153 到 65535。

ecs agent 則是使用 51678-51680 這些port 來通訊。

Docker daemon 需要 2375 and 2376

這時候 VPC 裡的 NACL 就要打通對應的 port，如果沒開，ecs cluster 就不會加入新開的機器。算是個小地方但如果沒注意就要多花時間找原因了。

ref: [https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_PortMapping.html](https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_PortMapping.html)

