---
mymetag_version: v3.1.0
id: 2f0fcaef-7cbd-4f69-bd75-64b5aae2d560
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-07T04:10
created_at: 2024-09-07T04:10
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::installed", "tool::yay"]
tags:
keywords:
title: "yay：インストールした（v2027-01"
aliases: ["yay：Installed（v2027-01"]
---

## まとめ

- `$ sudo pacman -S yay`

## 経緯

- Starship 試したい
- <- Nerds Fonts が必要
- <- Cica (Nerds Fonts が含まれている) が良さそう。試したい
- <- aur でインストールするのが楽そう
- <- yay を入れよう (今ココ)
- 何という yak shaving

## インストール方法の選定

- Manjaro Linux には yay の公式リポジトリがあるため、pacman コマンドを使って直接インストールできる
    - 一方 Arch Linux には無いため、`git` 経由でインストールする必要があるぽい

## 手順（やったこと）

### 1. インストール

```sh
$ pacman -S --needed git base-devel yay
```

### 2. バージョン確認

```sh
$ yay --version
yay v12.3.5 - libalpm v14.0.0
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

- [yay/README.md at next #Installation · Jguer/yay](https://github.com/Jguer/yay/blob/675f0ba3f3d4bbc006a12c29e273df0f4f533edc/README.md#other-distributions)
- [Arch: Manjaro で「pacman」と「yay」のコマンド操作〈H53〉 - Linux あれこれ](https://furuya7.hatenablog.com/entry/2020/05/06/180426)

## 関連リンク

- [yay/README.md at next #Installation · Jguer/yay](https://github.com/Jguer/yay/blob/675f0ba3f3d4bbc006a12c29e273df0f4f533edc/README.md)
- [yay package versions - Repology](https://repology.org/project/yay/versions)

## ChangeLog

- 2024-09-07
    - インストールコマンドを変更
        - `$ sudo pacman -S yay` -> `$ pacman -S --needed git base-devel yay`
            - そうしないと、後々何かしらのパッケージをインストールする際に 「`fakeroot` パッケージが見つかりません」的なエラーが起こる
