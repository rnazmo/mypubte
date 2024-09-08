---
mymetag_version: v3.1.0
id: 414b8325-1711-45fe-8223-a22096cee414
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-07T01:37
created_at: 2024-09-07T01:37
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::installed", "tool::Alacritty"]
tags:
keywords: ["pacman"]
title: "installed］Alacritty：インストールした（Manjaro Linux にて）（v2024-09"
aliases: ["installed］Alacritty：Installed（on Manjaro Linux）（v2024-09"]
---

## まとめ

- `$ sudo pacman -S alacritty`

## 経緯

- 開発環境（特にターミナル周り）を試行錯誤中

## インストール方法の選定

- [Cargo 使って自分でビルドする](https://github.com/alacritty/alacritty/blob/b125b99dd3886a3517f8ecf91dc6cae1ca5378fb/INSTALL.md)：
    - 結構面倒そうだったのでナシ
    - この方法だとサジェストとかが入らないのも辛い
        - > If you're just interested in the Alacritty binary and you don't need the terminfo file, desktop entry, manual page or shell completions, you can install it directly through cargo:
            - Source: [alacritty/INSTALL.md at master "Cargo Installation" · alacritty/alacritty](https://github.com/alacritty/alacritty/blob/b125b99dd3886a3517f8ecf91dc6cae1ca5378fb/INSTALL.md)
- [Snap 経由](https://snapcraft.io/alacritty)：
    - トラブル起こしやすい印象だからナシ
        - 以前（2 年前くらい？）に snap でインストールしたとき、細かいトラブルがちょくちょくあって面倒だった
            - うろ覚えだが、OS のメニューに Alacritty が追加されないとかそういうの
- [pacman 経由](https://wiki.archlinux.jp/index.php/Alacritty#.E3.82.A4.E3.83.B3.E3.82.B9.E3.83.88.E3.83.BC.E3.83.AB)：
    - pacman は不慣れだが楽そうなので、今回はこれを試した

## 手順（やったこと）

### 1. インストール

```sh
$ sudo pacman -S alacritty
```

### 2. バージョン確認

```sh
$ alacritty --version
alacritty 0.13.2 (bb8ea18e)
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

$ alacritty --version
alacritty 0.13.2 (bb8ea18e)
```

## 感想

- pacman で楽にインストールできて良かった
- Alacritty 自体はだいぶ安定しつつある雰囲気？
- 2 年前くらい？に触ったときには日本語周りで苦労した印象ある

## 参考

- [Alacritty #インストール - ArchWiki](https://wiki.archlinux.jp/index.php/Alacritty#.E3.82.A4.E3.83.B3.E3.82.B9.E3.83.88.E3.83.BC.E3.83.AB)
- [Arch Linux - Package Search](https://archlinux.org/packages/?name=alacritty)

## 関連リンク

- [alacritty/alacritty: A cross-platform, OpenGL terminal emulator.](https://github.com/alacritty/alacritty)
- [Alacritty - A cross-platform, OpenGL terminal emulator](https://alacritty.org/)
- [Alacritty - ArchWiki](https://wiki.archlinux.jp/index.php/Alacritty)
