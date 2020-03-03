+++
author = "Balduran Chang"
categories = ["mac", "cli", "homebrew", "jdk", "jenv"]
date = 2015-07-13T22:50:02Z
description = ""
draft = false
slug = "java-sdk-on-mac"
tags = ["mac", "cli", "homebrew", "jdk", "jenv"]
title = "java SDK on mac"

+++


##[java_home]
/usr/libexec/java_home 是個 symbolic link，link到目前正在用的 JVM version

	$ ll /usr/libexec/java_home
	lrwxr-xr-x 1 root wheel 79 Oct 28  2014 /usr/libexec/java_home -> /System/Library/Frameworks/JavaVM.framework/Versions/Current/Commands/java_home*

可以用一個環境變數 $JAVA_HOME 來記住這個 symbolic link 指到的JDK

```
export JAVA_HOME=$(/usr/libexec/java_home)
```

同時他可以列出目前安裝在機器上的所有 JDK

	$ /usr/libexec/java_home -V
	Matching Java Virtual Machines (5):
	    1.8.0_40, x86_64:	"Java SE 8"	/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home
	    1.7.0_80, x86_64:	"Java SE 7"	/Library/Java/JavaVirtualMachines/jdk1.7.0_80.jdk/Contents/Home
	    1.7.0_79, x86_64:	"Java SE 7"	/Library/Java/JavaVirtualMachines/jdk1.7.0_79.jdk/Contents/Home
	    1.6.0_65-b14-466.1, x86_64:	"Java SE 6"	/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
	    1.6.0_65-b14-466.1, i386:	"Java SE 6"	/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home

	/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home

如果要動態改變 JAVA_HOME 使用的 jdk版本，直接下`/usr/libexec/java_home -v 1.7`就會用 1.7 最新的版本（當然是已經安裝了)

配合 $JAVA_HOME，就可以用環境變數控制所要使用的 JDK版本

```
export JAVA_HOME=$(/usr/libexec/java_home -v 1.7)
```

## Oracle or Apple?
眼尖一點的人會發現，jdk 怎麼會有兩個不同的目錄，jdk 1.6 在 `/System/Library/Java/JavaVirtualMachines/`，jdk 1.7 在 `/Library/Java/JavaVirtualMachines/`

答案就是 Apple 官方網站下載的 JDK (1.6) 會放在 `/System/Library/Java/JavaVirtualMachines/{version}`

Oracle 網站上下載的 JDK (1.7, 1.8) 會是在 `/Library/Java/JavaVirtualMachines/{version}`

有些人會自己建 symbolic link 到 `/System/Library/Frameworks/JavaVM.framework/Versions/CurrentJDK`，這倒不是個建議的做法，用 java_home 會比較有彈性，也可以在多個 JDK 選擇。

很煩人吧，為了解決這個困擾，自然就有人寫了管理工具，[JEnv]。

## [JEnv]
JENV 在 mac 上有非常好用的 [brew] 可以管理安裝，`brew install jenv`馬上就解決。

至於 JEnv 的詳細使用，大體上和 [rbenv] 是差不多的


[java_home]: https://developer.apple.com/library/mac/qa/qa1170/_index.html
[JEnv]: http://www.jenv.be/
[brew]: /2013/03/30/use-homebrew-on-mac/
[rbenv]: /2015/05/05/rbenv-on-mac/

