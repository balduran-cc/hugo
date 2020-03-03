+++
author = "Balduran Chang"
categories = ["cli", "Cryptocurrency"]
date = 2018-01-03T09:48:52Z
description = ""
draft = false
slug = "mining-by-cli"
tags = ["cli", "Cryptocurrency"]
title = "minergate by CLI"

+++


上次提到了用 [minergate](https://minergate.com/a/3856b288abb92c7096595953) 的 GUI [體驗挖礦](/2017/07/17/minergate/)，算是非常好入門的挖礦方法，不過身為一個工程師，想要試試看指令模式也是很合理的。

## 幣別選擇

先說說有哪些可以挖。

最知名的就是 BTC，但是現階段可以說不用想了，線上雲端挖礦和各種礦機的存在已經不是休閒挖礦可以踏入的，開了也只是浪費電而已。[ETH 還可以](http://ethdocs.org/en/latest/mining.html#mining)，不過沒有顯示卡的加速，也是一般般。想要用 cpu來挖礦，是有滿多限制的，而最近滿值得試試看的就是 XMR 門羅幣了。

其他可以用 cpu的還有 BCN, QCN, XDN, FCN, MCN and DSH。

##挖礦程式的選擇

CPU 挖礦可以用 [Claymore CryptoNote CPU Miner](https://mega.nz/#F!Hg4g1bLT!4Upg8GNiEZYCaZ04XVh_yg)，指令就
`NsCpuCNMiner64.exe -o stratum+tcp://xmr.pool.minergate.com:45560 -u EMAIL -p x`

另外還有 [OhGodAPet/cpuminer-multi](https://github.com/OhGodAPet/cpuminer-multi)
指令是`minerd -a cryptonight -o stratum+tcp://xmr.pool.minergate.com:45560 -u EMAIL -p x`

更新：OhGodAPet版本的 cpuminer-multi 已經停止維護，還有在維護的是 [tpruvot/cpuminer-multi](https://github.com/tpruvot/cpuminer-multi)
，可以下載原始碼之後自行編譯，編譯的指令是
```
git clone https://github.com/tpruvot/cpuminer-multi.git
cd cpuminer-multi
./autogen.sh
./configure --with-crypto --with-curl
make
```

編譯完成後可以下`./cpuminer --cputest`做一下測試。挖礦的指令也要更新為`./cpuminer -a cryptonight -o stratum+tcp://xmr.pool.minergate.com:45560 -u EMAIL -p x -t 1`

其實用 CPU真的挺不符合效益的，不過既然是玩玩，也就不要太認真囉，閒暇之餘看看別人怎麼寫挖礦程式比較有趣。

