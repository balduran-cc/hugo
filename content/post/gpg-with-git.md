+++
author = "Balduran Chang"
categories = ["git", "github", "code", "programming", "gpg"]
date = 2017-06-18T23:32:30Z
description = ""
draft = false
slug = "gpg-with-git"
tags = ["git", "github", "code", "programming", "gpg"]
title = "GPG with git"

+++


sign code commit with gpg 需要以下步驟。

1. 安裝 GPG command line
2. 產生 GPG key
3. export GPG public key
4. 在github上設定public key
5. commit and sign

## 安裝 GPG
可以在 [GnuPG](https://www.gnupg.org/download/) 下載安裝，或是用homebrew 執行 `brew install gpg`

近來也有一個服務，keybase.io 在做 pub/private key 的管理，也可以用它來產生 key

## 產生 GPG
`gpg --gen-key` 用 command line 做法

或是用 GPG keychain 產生，背後原理都一樣。

## export
命令列輸入 `gpg --list-secret-keys --keyid-format LONG`，如果只輸入 `gpg --list-secret-keys`，結果沒有顯示 keyid的話，請用 gpg2

`gpg --armor --export ==keyid==` 可以得到 public key，一長串的字元

```
-----BEGIN PGP PUBLIC KEY BLOCK-----
ABCDE
ABCDE
ABCDE
ABCDE
ABCDE
-----END PGP PUBLIC KEY BLOCK-----
```

## github setting
在github的帳號設定下，[貼入以上](https://help.github.com/articles/adding-a-new-gpg-key-to-your-github-account/)的 public key string

## commit and sign
指令 `git commit -S fileA` 就可以commit 的同時也用gpg sign過，但git 不是自動就會認得 gpg key，需要以下config

```
git config commit.gpgsign true
git config gpg.program gpg2
git config user.signingkey keyid
```
gpg.program 如果一直出現錯誤，可以改成用gpg2，至於 keyid，就是自己個人的 keyid 了

```
git config tag.gpgsign true
```
則是可以sign tag

另外可以用 GPG_TTY 這個變數
```
GPG_TTY=$(tty)
export GPG_TTY
```

## final
`git log --show-signature` 可以看到 sign 過的 commit

