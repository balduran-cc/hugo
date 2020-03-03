+++
author = "Balduran Chang"
categories = ["alarm", "eval", "note", "perl"]
date = 2009-02-12T09:14:08Z
description = ""
draft = false
slug = "perl-time-out-detect"
tags = ["alarm", "eval", "note", "perl"]
title = "perl - time out detect"

+++


想寫一支 perl 判斷程式什麼時候掛掉，不一定是 crash，執行到 hang 也算，因為現在面對的就是一支無法得知穩定度的 C 程式。我昨天就用 watchdog 當關鍵字在找，也沒什麼資料。

判斷 time out 的部份好不容易找到 [Using Eval for Time-Outs](http://docstore.mik.ua/orelly/perl/advprog/ch05_06.htm)，用 signal 來接收 time out 的 alarm，這部份算是一大進展，eval{} 區塊裡面放入我要判斷的程式，alarm handler 放入 system(“killall -9 myprogram”) 將 hang 住的程式殺掉，然後重啟。

> $SIG{ALRM} = \&timed_out;  
> eval {  
>     alarm (10);  
>     $buf = <>;  
>     alarm(0);           # Cancel the pending alarm if user responds.  
> };  
> if ($@ =~ /GOT TIRED OF WAITING/) {  
>     print “Timed out. Proceeding with default\n”;  
>     ….  
> }
> 
> sub timed_out {  
>     die “GOT TIRED OF WAITING”;  
> }

以此為記，[Advanced Perl Programming](http://docstore.mik.ua/orelly/perl/advprog/index.htm) 遇到困難應該來翻閱的。

另外，open INPUT, “myprogram |”; 的方式在 myprogram 停住的時候，無法 close(INPUT)，會 block 住，直接 kill -9 就好。

`ps -eaf |grep myprogram |grep -v grep` 會列出 myprogram 的詳細資料。

