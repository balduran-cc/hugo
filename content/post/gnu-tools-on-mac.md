+++
author = "Balduran Chang"
categories = ["GNU", "mac", "tips", "cli", "homebrew"]
date = 2015-06-19T16:04:28Z
description = ""
draft = false
slug = "gnu-tools-on-mac"
tags = ["GNU", "mac", "tips", "cli", "homebrew"]
title = "GNU tools on MAC"

+++


在 MAC 與 linux 之間穿梭，就會發現頗多 commandline tool 有些微不一樣，原因就是 MAC OS X 是延續 BSD 發展的，想要加強這些tool，我們可以自己安裝。

##安裝 GCC

身為軟體工程師，安裝 GCC on mac 好像不需要理由。

```
$ gcc --version
Configured with: --prefix=/Applications/Xcode.app/Contents/Developer/usr --with-gxx-include-dir=/usr/include/c++/4.2.1
Apple LLVM version 6.1.0 (clang-602.0.53) (based on LLVM 3.6.0svn)
Target: x86_64-apple-darwin14.3.0
Thread model: posix
```
內建的gcc是由llvm編譯的。

1. 安裝 official Command Line Tools for Xcode package
可直接下指令`xcode-select --install`或是從 [https://developer.apple.com/downloads/](https://developer.apple.com/downloads/) 下載 Command Line Tools

2. 經由 homebrew安裝

```
brew tap homebrew/versions
brew install gcc48
```
要更改支援的語言，可從`brew options gcc48`看可以下的參數。

```
$ /usr/local/opt/gcc48/bin/gcc-4.8 --version
gcc-4.8 (Homebrew gcc48 4.8.4) 4.8.4
Copyright (C) 2013 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```
Homebrew 安裝的版本就不是用llvm產生的。


##安裝 coreutil
[GNU Core Utilities](http://www.wikiwand.com/en/GNU_Core_Utilities)包含了一堆基本工具，會用 UNIX-like 系統的話應該都不陌生。

1. 安裝 coreutils
`brew install coreutils`

2. 設定 $PATH
`export PATH="$(brew --prefix coreutils)/libexec/gnubin:/usr/local/bin:$PATH"`
3. 設定 $MANPATH
`export MANPATH="$(brew --prefix coreutils)/libexec/gnuman:$MANPATH"`

##安裝其他 tool
```
brew install binutils
brew install diffutils
brew install findutils --with-default-names
```
```
brew install gnu-indent --with-default-names
brew install gnu-sed --with-default-names
brew install gnu-tar --with-default-names
brew install gnu-which --with-default-names
```
```
brew install wdiff --with-gettext
brew install gawk
brew install gnutls
brew install gzip
brew install screen
brew install watch
brew install wget
```
其中 --with-default-names 可以避免 g被冠上去。


##安裝 grep
系統上內建安裝的是 BSD 版本，比較慢，而且參數和習慣使用的 linux 不同，bashrc要分開處理有點討厭。

1. 安裝grep

```
brew tap homebrew/dupes
brew install grep --with-default-names
```

2. 前後版本文字

```
$ /usr/bin/grep --version
grep (BSD grep) 2.5.1-FreeBSD
```

```
/usr/local/bin/grep (GNU grep) 2.21
Copyright (C) 2014 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Written by Mike Haertel and others, see <http://git.sv.gnu.org/cgit/grep.git/tree/AUTHORS>.
```

## homebrew-dupes
[homebrew-dupes](https://github.com/Homebrew/homebrew-dupes) 列出了和 OS X 系統內建重複的程式，想要替換系統內建的話，可以參考。

