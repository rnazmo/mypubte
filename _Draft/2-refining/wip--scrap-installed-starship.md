---
mymetag_version: v3.1.0
id: d55279bf-3a40-4441-a0ac-a9a91529b388
type: Scrap
status: ["visibility::public", "workflow::drafting"]
drafted_at: 2024-09-06T23:23
created_at: 2024-09-07T09:31
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::installed", "tool::Starship"]
tags:
keywords: ["terminal", "prompt"]
title: "Starship：インストールした（v2024-09"
aliases: ["Starship：Installed（v2024-09"]
---

## まとめ

- foo

## 経緯

- TODO:

## やりたかったこと

- TODO:

## インストール方法の選定

- バイナリ or pacman or mise or ...
- mise でやる？
    - そんなに厳密なバージョン管理は必要ないだろう。最新版だけで十分。バージョン切り替える予定ない
- なら pacman でいいか

## 手順（やったこと）

### 前提

- [Nerd Font](https://www.nerdfonts.com/) の一つがインストールされていて、かつターミナルで有効になっていること

### 1. インストール

```sh
$ sudo pacman -S starship
```

### 2. シェルの設定

~~`~/.zshrc` の末尾に以下を追記：~~

```sh
eval "$(starship init zsh)"
```

Manjaro Linux のデフォルトの `~/.zshrc` には powerline とか色々書いてあるので、今回はそれを捨ててまっさらな `~/.zshrc` を作り直した。

### 3. バージョン確認

```sh
$ starship --version
starship 1.20.1
tag:v1.20.1
commit_hash:f505324da
build_time:2024-07-27 12:27:58 +00:00
build_env:rustc 1.80.0 (051478957 2024-07-21) (Arch Linux rust 1:1.80.0-1),
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

$ yay -Si ttf-cica | grep "Version"
Version                       : 5.0.3-1
Version                       : 5.0.3-1

$ starship --version
starship 1.20.1
tag:v1.20.1
commit_hash:f505324da
build_time:2024-07-27 12:27:58 +00:00
build_env:rustc 1.80.0 (051478957 2024-07-21) (Arch Linux rust 1:1.80.0-1),
```

## 感想

- Starship をインストールするまでがめちゃ大変だった
    - Nerd Font のインストールが大変だった
    - *yak shaving*
- 少し触った感触はかなり良い
- カスタマイズ項目多すぎて大変そう
- 

## 参考

- [Guide #Installation | Starship](https://starship.rs/ja-JP/guide/)
- [Starship](https://starship.rs/ja-JP/)
- [starship/README.md at master #Installation · starship/starship](https://github.com/starship/starship/blob/d50d0e35dde42a9d5e3b11385ee36ed636b6ef35/README.md#-installation)
