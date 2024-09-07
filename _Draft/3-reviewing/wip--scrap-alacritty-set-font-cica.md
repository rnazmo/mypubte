---
mymetag_version: v3.1.0
id: 7e9776ab-cfcb-4426-aec9-7dccd53d5245
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-07T06:33
created_at: 2024-09-07T06:33
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::customize-config", "tool::Alacritty"]
tags: ["font::Cica", "TOML", "configuration"]
keywords: ["config file", "alacritty.toml"]
title: "customize-config］Alacritty：フォントを Cica に設定した"
aliases: ["customize-config］Alacritty：Set font to Cica"]
---

## まとめ

- 設定ファイルである `alacritty.toml` に以下を書く：

```toml
[font]
normal.family = "Cica"
normal.style = "Regular"
bold.family = "Cica"
bold.style = "Bold"
italic.family = "Cica"
italic.style = "Italic"
bold_italic.family = "Cica"
bold_italic.style = "Bold Italic"
```

## 経緯

- Starship 試したい
- <- Nerds Fonts を設定したターミナルが必要
- Cica (Nerds Fonts 含んでる) と Alacritty でやってみよう (今ココ)

## 前提

- Cica をインストール済みである

## 作業（やったこと）

### Cica の状態を確認した

```sh
$ yay -Si ttf-cica | grep "Version"
Version                       : 5.0.3-1

$ fc-list | grep -i cica
/usr/share/fonts/TTF/Cica-RegularItalic.ttf: Cica:style=Italic
/usr/share/fonts/TTF/Cica-BoldItalic.ttf: Cica:style=Bold Italic
/usr/share/fonts/TTF/Cica-Bold.ttf: Cica:style=Bold
/usr/share/fonts/TTF/Cica-Regular.ttf: Cica:style=Regular
```

- Cica には Regular, RegularItalic, Bold, BoldItalic の 4 つが用意されているようだ
- これを設定してあげる

### Alacritty の設定ファイルの書き方を確認した

- v0.13.0 から設定ファイルが YAML から TOML へ変更された
  - `alacritty.yml` -> `alacritty.toml`
- TOML は同じ構造を数通りの書き方で表現できるが、どう書くか？
  - See: [Alacritty,TOML：設定ファイル (`alacritty.toml`) の TOML の書き方どうするか問題](./7ed73067-19bc-4c6e-b218-2147736859a8.md)
- 以前あった設定ファイルのサンプルは無くなっている
  - See: [Alacritty：デフォルトの設定ファイル（サンプルファイル）は無くなった](23b8da9a-66c9-47a7-a355-aae3630fa382.md)
- 公式の情報とググって出てきた `alacritty.toml` を参考に自分の設定ファイルを作る
  - 参考になったのは主にこのへん:
    - [Example configuration file for Alacritty and simple guide](https://gist.github.com/ritog/76081f97681e7079d11ec163a5bd4141)
    - ["cica path:**/alacritty.toml" - GitHub Code search results](https://github.com/search?q=cica+path%3A**%2Falacritty.toml&type=code&ref=advsearch)
    - [Configuration | Alacritty](https://alacritty.org/config-alacritty.html)
    - [alacritty/extra/man/alacritty.5.scd at master · alacritty/alacritty](https://github.com/alacritty/alacritty/blob/b125b99dd3886a3517f8ecf91dc6cae1ca5378fb/extra/man/alacritty.5.scd)

### フォントを Cica に指定する設定を書いた

- できた設定は次の通り。これを `alacritty.toml` に書けばOK：

```toml
[font]
normal.family = "Cica"
normal.style = "Regular"
bold.family = "Cica"
bold.style = "Bold"
italic.family = "Cica"
italic.style = "Italic"
bold_italic.family = "Cica"
bold_italic.style = "Bold Italic"
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

## 関連リンク

- [Alacritty,TOML：設定ファイル (`alacritty.toml`) の TOML の書き方どうするか問題](./7ed73067-19bc-4c6e-b218-2147736859a8.md)
- [Alacritty - ArchWiki](https://wiki.archlinux.jp/index.php/Alacritty)
