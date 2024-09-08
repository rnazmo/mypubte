---
mymetag_version: v3.1.0
id: 27915af7-b982-482e-9195-8ba1fb96c69e
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-08T08:59
created_at: 2024-09-08T08:59
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::customize-config", "tool::Alacritty"]
tags:
keywords: ["theme", "color"]
title: "customize-config］Alacritty：テーマを導入してみた（v2024-09"
aliases: ["customize-config］Alacritty：customized theme（v2024-09"]
---

## まとめ

- テーマを色々試した結果、"zenburn" にした
- 導入方法は `alacritty.toml` に以下を追記するだけ：

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
```

## 経緯

- デフォルトでも問題なかったが、導入楽そうだったので何となく試してみた

## 導入方法

- テーマの導入方法は 2 通りある
  - Ref: [alacritty-theme/README.md at master · alacritty/alacritty-theme](https://github.com/alacritty/alacritty-theme/blob/e759dafb8e2e00abb428592979ce006da7fba4a7/README.md#installation)
- 今回は A で色々試して、決まったら B で導入した

### A. インポート

#### 1. alacritty-theme リポジトリをダウンロードする

```sh
mkdir -p ~/.config/alacritty/themes
git clone https://github.com/alacritty/alacritty-theme ~/.config/alacritty/themes
```

#### 2. 設定ファイルからインポートする

`alacritty.toml` に下記を書く：

```toml
import = [
    "~/.config/alacritty/themes/themes/{theme}.toml"
]
```

### B. 手動でコピペ

- [ここ](https://github.com/alacritty/alacritty-theme/tree/e759dafb8e2e00abb428592979ce006da7fba4a7/themes) から好きなテーマを選んで、自分の設定ファイル `alacritty.toml` にコピペするだけ。


## どのテーマにするか

- 色々試した
- 候補：
  - one_dark
    - 他のツールとかでもよく使ってるカラーテーマ
    - 悪くない
  - github_dark
    - 良い
  - github_dark_colorblind
    - 良い
  - pastel_dark
    - 良い
  - zenburn
    - Starship の今のテーマ（Gruvbox Rainbow）と合っててとても良い感じ
    - 淡い感じの色、好き
- 結論：
  - zenburn

## zenburn を採用する

zenburn はこんな色：

![zenburn](./media/82177c4c-cf65-454b-b59b-40dd8df0eee2.png)

以下を自分の設定ファイルに追記すれば良い：

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

- かなり気軽に試せて良かった。導入も変更も簡単かつ即反映される
- そもそも Starship 使うからテーマはあまり関係無さそうかと思ったが、背景とかが多少変わった
  - なので一応意味はある

## 参考

- [alacritty-theme/README.md at master · alacritty/alacritty-theme](https://github.com/alacritty/alacritty-theme/blob/e759dafb8e2e00abb428592979ce006da7fba4a7/README.md)

## 関連リンク

- [jnurmine/Zenburn: Zenburn is a low-contrast color scheme for Vim.](https://github.com/jnurmine/Zenburn)
