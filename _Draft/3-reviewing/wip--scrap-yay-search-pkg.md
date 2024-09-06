---
mymetag_version: v3.1.0
id: 7f1c8f45-16fa-4804-803b-30c5e5e1bc40
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-07T04:46
created_at: 2024-09-07T04:46
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::installed", "tool::yay"]
tags:
keywords:
title: "yay：パッケージの検索と確認の方法（v2024-09"
aliases: ["yay：Installed（v2024-09"]
---

## まとめ

- 検索：`$ yay -Ss パッケージ名`
- 確認：`$ yay -Si パッケージ名`


## パッケージの検索

```sh
$ yay -Ss パッケージ名
```
### 例

```sh
$ yay -Ss cica
aur/ttf-cica 5.0.3-1 (+6 0.00) 
    A Japanese monospace font for programming
aur/cicada-bin 0.1.50-1 (+1 0.00) (Orphaned) 
    Write CI/CD Pipelines in TypeScript
aur/cicada-shell 0.9.38-1 (+2 0.00) 
    A bash-like Unix shell written in Rust
aur/cicada-git 2015.06.24-1 (+3 0.00) 
    programming language with the following features 1. threaded code based 2. aggressively developed 3. never provide backward compatibility [github git version]
aur/cicada 2015.06.24-1 (+1 0.00) (Out-of-date: 2023-12-05) 
    programming language with the following features 1. threaded code based 2. aggressively developed 3. never provide backward compatibility [github zip version]
```

## パッケージの確認

```sh
$ yay -Si パッケージ名
```

### 例

```sh
$ yay -Si ttf-cica
Repository                    : aur
Name                          : ttf-cica
Version                       : 5.0.3-1
Description                   : A Japanese monospace font for programming
URL                           : https://github.com/miiton/Cica
Licenses                      : custom
Groups                        : None
Provides                      : None
Depends On                    : None
Optional Deps                 : None
Make Deps                     : None
Check Deps                    : None
Conflicts With                : None
Replaces                      : None
AUR URL                       : https://aur.archlinux.org/packages/ttf-cica
First Submitted               : Fri 21 Oct 2016 03:08:59 AM JST
Keywords                      : None
Last Modified                 : Tue 29 Mar 2022 11:47:38 AM JST
Maintainer                    : azon
Popularity                    : 0.000003
Votes                         : 6
Out-of-date                   : No
```

## 環境

```console
$ proper7y
proper7y v0.4.2 - A tiny Bash script to get OS and other
software version info. https://github.com/rnazmo/proper7y
============================================================
OS NAME      : Manjaro Linux
OS VERSION   : 24.0.3
Current Shell: Zsh
Bash VERSION : 5.2.26(1)-release (x86_64-pc-linux-gnu)
Zsh VERSION  : 5.9 (x86_64-pc-linux-gnu)
CPU ARCH     : x86_64
============================================================

$ yay --version
yay v12.3.5 - libalpm v14.0.0
```

## 参考

- [Arch Linux(2) Manjaro でのコマンド操作 #パッケージの検索 - Qiita](https://qiita.com/FuRuYa7/items/e727dc1ecff6163f79ac#yay-%E3%81%A7%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%81%AE%E6%A4%9C%E7%B4%A2%E3%81%8A%E3%82%88%E3%81%B3%E7%A2%BA%E8%AA%8D)
- [Arch Linux(2) Manjaro でのコマンド操作 #パッケージの詳細を確認 - Qiita](https://qiita.com/FuRuYa7/items/e727dc1ecff6163f79ac#%E6%B0%97%E3%81%AB%E3%81%AA%E3%81%A3%E3%81%9F%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%81%AE%E8%A9%B3%E7%B4%B0%E3%82%92%E7%A2%BA%E8%AA%8D)

## TODO

- [ ] 一次情報を確認する (`man yay` とか)
