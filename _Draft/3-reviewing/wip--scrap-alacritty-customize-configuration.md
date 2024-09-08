---
mymetag_version: v3.1.0
id: 7e9776ab-cfcb-4426-aec9-7dccd53d5245
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-08T08:26
created_at: 2024-09-08T08:26
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::customize-config", "tool::Alacritty"]
tags: ["configuration"]
keywords: ["config file", "alacritty.toml"]
title: "customize-config］Alacritty：設定を色々弄った（v2024-09"
aliases: ["customize-config］Alacritty：Tweaked configuration（v2024-09"]
---

## まとめ

TODO:

## 経緯

- Alacritty 試してみたい
- -> Alacritty のインストールをした
- -> Alacritty にフォントの Cica を設定をした（Starship に Nerd Fonts が必要なため）
- -> フォント以外の設定も弄ってみよう (今ココ)

## 前提

- Cica をインストール済みである

## alacritty.toml

- 設定ファイルの場所は `~/.config/alacritty/alacritty.toml`
- ググって出てきた `alacritty.toml` と、公式の説明を参考に書いた
- 設定項目に一通り目を通したが**ほとんどはデフォルトで十分**そう
    - なので、設定ファイルの記述はわりと小さなものとなった
- 最終的な設定ファイルは以下の通り：

```toml
# ================================================
# Theme (Color Scheme)
#
# Theme Name:
#   Zenburn
# Source:
#   https://github.com/alacritty/alacritty-theme/blob/e759dafb8e2e00abb428592979ce006da7fba4a7/themes/zenburn.toml
# What is Zenburn?
#   Orginally color scheme for Vim designed by jnurmine.


[colors.primary]
background = '#3A3A3A'
foreground = '#DCDCCC'

[colors.normal]
black   = '#1E2320'
red     = '#D78787'
green   = '#60B48A'
yellow  = '#DFAF8F'
blue    = '#506070'
magenta = '#DC8CC3'
cyan    = '#8CD0D3'
white   = '#DCDCCC'

[colors.bright]
black   = '#709080'
red     = '#DCA3A3'
green   = '#C3BF9F'
yellow  = '#F0DFAF'
blue    = '#94BFF3'
magenta = '#EC93D3'
cyan    = '#93E0E3'
white   = '#FFFFFF'
# ================================================

[window]
opacity = 0.9

[cursor]
style.shape = "Block"
style.blinking = "On"

[font]
size = 13.0
normal.family = "Cica"
normal.style = "Regular"
bold.family = "Cica"
bold.style = "Bold"
italic.family = "Cica"
italic.style = "Italic"
bold_italic.family = "Cica"
bold_italic.style = "Bold Italic"

```

- 上記設定の解説：
  - テーマ：
    - デフォルトでも十分だったが、導入楽そうだったので設定してみた
    - 正直無くても良い
    - 詳細はここでは触れない。別記事にて
      - See: [customize-config］Alacritty：テーマを導入してみた（v2024-09](27915af7-b982-482e-9195-8ba1fb96c69e.md)
  - ウィンドウ透明度とカーソルスタイルは好み
  - フォントサイズは適当
  - フォント指定は Starship 使う関係で Nard Font が必要だから変更必須
    - See: [customize-config］Alacritty：フォントを Cica に設定した](7e9776ab-cfcb-4426-aec9-7dccd53d5245.md)
- その他注意事項：
  - See: [Alacritty,TOML：設定ファイル (`alacritty.toml`) の TOML の書き方どうするか問題](./7ed73067-19bc-4c6e-b218-2147736859a8.md)
  - See: [Alacritty：デフォルトの設定ファイル（サンプルファイル）は無くなった](23b8da9a-66c9-47a7-a355-aae3630fa382.md)

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
```

```sh
$ alacritty --version
alacritty 0.13.2 (bb8ea18e)
```

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

## 参考

- 設定ファイル (`alacritty.toml`) の書き方：
  - [Configuration | Alacritty](https://alacritty.org/config-alacritty.html)
  - [alacritty/extra/man/alacritty.5.scd at master · alacritty/alacritty](https://github.com/alacritty/alacritty/blob/b125b99dd3886a3517f8ecf91dc6cae1ca5378fb/extra/man/alacritty.5.scd)
- 設定ファイル (`alacritty.toml`) の例：
  - [Example configuration file for Alacritty and simple guide](https://gist.github.com/ritog/76081f97681e7079d11ec163a5bd4141)
  - ["cica path:**/alacritty.toml" - GitHub Code search results](https://github.com/search?q=cica+path%3A**%2Falacritty.toml&type=code&ref=advsearch)
  - ["path:**/alacritty.toml" - GitHub Code search results](https://github.com/search?q=path%3A**%2Falacritty.toml&type=code&ref=advsearch)

## 関連リンク

- [customize-config］Alacritty：フォントを Cica に設定した](7e9776ab-cfcb-4426-aec9-7dccd53d5245.md)
- [customize-config］Alacritty：テーマを導入してみた（v2024-09](27915af7-b982-482e-9195-8ba1fb96c69e.md)
- [Alacritty,TOML：設定ファイル (`alacritty.toml`) の TOML の書き方どうするか問題](./7ed73067-19bc-4c6e-b218-2147736859a8.md)
- [Alacritty：デフォルトの設定ファイル（サンプルファイル）は無くなった](23b8da9a-66c9-47a7-a355-aae3630fa382.md)
- [Alacritty - ArchWiki](https://wiki.archlinux.jp/index.php/Alacritty)