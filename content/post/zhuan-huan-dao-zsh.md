+++
author = "Balduran Chang"
date = 2020-03-01T23:48:29Z
description = ""
draft = false
slug = "zhuan-huan-dao-zsh"
title = "轉換到 zsh"

+++


macOS Catalina 預設使用的 shell [從 bash 換到 zsh](https://support.apple.com/en-us/HT208050)，雖然早就知道 zsh 有很多方便的套件，但沒特別動力轉換，畢竟遠端登入的機器大多數都還是 bash，不過自己 mac的 shell被改了，那也是個轉換的好時機。

最快速方便的方法就是用別人調好的 framework，[https://github.com/ohmyzsh/ohmyzsh](https://github.com/ohmyzsh/ohmyzsh)直接 clone 下來安裝，裡面已經有設定好的 plug-in 和 theme ，也不用花太多時間在搞這些細節上。

需要注意的是 `.zshrc` 會新增一些內容，如果有自己另外管理 rc 檔案的話要注意不要覆寫了。

## theme

theme 的部分很多元，[themes list](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) 挑一個順眼的。如果使用到了 Solarized colors scheme，那就要額外安裝顏色設定，這些顏色會比預設的來得柔和許多。

在 [https://ethanschoonover.com/solarized/](https://ethanschoonover.com/solarized/) 直接下載，如果用 iterm2 就直接 iterm2 資料夾下的檔案。

## fonts

其中一些 theme 有使用特別的字型，可以在 [https://github.com/powerline/fonts](https://github.com/powerline/fonts) 下載，工程師應該都會選擇直接 git clone 然後直接下指令，這部分還滿簡單直覺。

像 [https://github.com/agnoster/agnoster-zsh-theme](https://github.com/agnoster/agnoster-zsh-theme) 這個花俏的主題就需要字型和顏色設定。

## syntax highlight / autosuggestions

額外再推薦加裝這個 [https://github.com/zsh-users/zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)

`brew install zsh-syntax-highlighting`需要手動修改 .zshrc，加上 `source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh`

或是最簡單的方法，修改 .zshrc 裡的 plugins需要手動 git clone 到 oh-my-zsh folder 內

```
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting

```

然後在 .zshrc 裡面打開 zsh-syntax-highlighting and zsh-autosuggestions

