---
mymetag_version: v3.1.0
id: 859b1c37-feb7-4442-8490-05febeb320d3
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-07T02:25
created_at: 2024-09-07T02:25
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::installed", "Alacritty"]
tags:
keywords:
title: "Alacritty：設定ファイルの場所（v2024-09"
aliases: ["Alacritty：Location of configuration file（v2024-09"]
---

## まとめ

- `~/.config/alacritty/alacritty.toml` がおすすめ

## 設定ファイルの場所

- UNIX：
    1. `$XDG_CONFIG_HOME/alacritty/alacritty.toml`
    2. `$XDG_CONFIG_HOME/alacritty.toml`
    3. `$HOME/.config/alacritty/alacritty.toml`
    4. `$HOME/.alacritty.toml`
- Windows：
    - `%APPDATA%alacrittyalacritty.toml`
- 注意点：
    - Alacritty はインストール時には設定ファイルを作成しない
    - v0.13.0 にて設定ファイルが YAML ではなく TOML に変更された [^1]
        - バージョン 0.12 以前の設定ファイルは `alacritty.yml`

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

$ alacritty --version
alacritty 0.13.2 (bb8ea18e)
```

## 参考

- [Alacritty - Configuration #LOCATION](https://alacritty.org/config-alacritty.html#location)
- [alacritty/README.md at master #Configuration · alacritty/alacritty](https://github.com/alacritty/alacritty/blob/b125b99dd3886a3517f8ecf91dc6cae1ca5378fb/README.md#configuration)
- [Alacritty #設定 - ArchWiki](https://wiki.archlinux.jp/index.php/Alacritty#.E8.A8.AD.E5.AE.9A)

## 注釈

[^1]: [alacritty/CHANGELOG.md at master · alacritty/alacritty](https://github.com/alacritty/alacritty/blob/b125b99dd3886a3517f8ecf91dc6cae1ca5378fb/CHANGELOG.md#changed-3)
