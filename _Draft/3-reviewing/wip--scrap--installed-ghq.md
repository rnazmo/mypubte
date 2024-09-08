---
mymetag_version: v3.1.0
id: 8b91318a-0b9a-4b18-b336-bcb00a62df43
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-09T01:49
created_at: 2024-09-09T01:49
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::installed", "tool::ghq"]
tags: ["tool::Golang", "tool::mise"]
keywords:
title: "installed］ghq：インストールした（Manjaro Linux にて）（v2024-09"
aliases: ["installed］ghq：Installed（on Manjaro Linux）（v2024-09"]
---

## まとめ

- インストール方法を検討した結果「自分で GitHub Releases からバイナリ取ってくる」ことになった
- インストール用の Bash スクリプトを書いたので、これを走らせれば `~/bin` にバイナリが用意される

## この記事の目的・方針

- See: [purpose-and-policy］`installed` シリーズの目的・方針（v2024-09](ed0f0a63-51e1-43b0-8cd6-3bb77de060fb.md)

## 経緯

- 開発環境を全面的に見直している

## インストール方法の選定

### 候補

- **yay (AUR)**：
    - 更新がかなり遅そうなので無し
    - 2024-09-09 時点でこんなかんじ：
        - 最新版：`v1.6.2` (最終更新：2024-07-12)
        - AUR 版：`v1.6.1` (最終更新：2024-04-26)
- **go install**：
    - 信頼性も安全性も高い、はず
        - インストール後に `GOPATH` 周りでトラブることはありそう
    - ghq のインストール前に **Golang のインストールが必要**になるのが難点
        - Golang は mise でインストールするつもり
    - 一度、試しに `go install` でインストールしてみた
        - バイナリは以下の場所に置かれた
            - `/home/toor/.local/share/mise/installs/go/1.23.0/bin/ghq`
        - golang を mise でインストールしたせいか、**ghq のバイナリがかなり深いところに位置してる**のが気になる
            - これ後々トラブル起こしそうでちょっと嫌だな
        - 一時的に使うツールならまだしも、ghq はかなりヘビーに使いたいので安定して動いてほしい
        - トラブルシューティングも面倒になりそう。ghq なのか golang なのか mise なのか切り分けるの面倒そう
- **mise**：
    - 一番便利そうではある
    - コミュニティプラグインを利用することになる
        - 規模が小さめの**コミュニティプラグインを使うのはセキュリティ的にちょっと怖い**
    - 常に最新版を使うだろうから、**mise (バージョン管理ツール) である必要性はかなり薄い**かも
- **自前ビルド**：
    - できれば他のやり方で楽したい
    - 最終手段
    - [`make install` は内部的には `go install` している](https://github.com/x-motemen/ghq/blob/d79add20f26e7c079295e79496310ce3b6eabed1/Makefile#L32) ので、結局 `go install` と変わらん
- **自分で GitHub Releases からバイナリ取ってくる**：
    - かなり有力
    - 適当な Bash スクリプト書けばいける
    - 置き場所は `~/bin` あたりが候補

### 検討

- 一番楽なのは mise だが、できるだけコミュニティプラグインは避けたい
- 自前ビルドは (Makefile の内部で `go install` してるから) `go install` と変わらん
- go install は ghq のバイナリが変なところいくからちょっと怖い
- 結局自分で GitHub Releases からバイナリ取ってくるのが一番いいか
    - Bash スクリプト書くの面倒だけど、一度書けばずっと使えるし
- => 「**自分で GitHub Releases からバイナリ取ってくる**」を採用

## 手順（やったこと）

### 1. インストール用の Bash スクリプト `install-ghq.sh` を作った

汚いけどとりあえず作った：

```bash
#!/bin/bash
set -eu

main() {
  local -r APPNAME="ghq"
  local -r CMDNAME="ghq"
  local -r VERSION="v1.6.2"
  local -r FNAME="ghq_linux_amd64"
  local -r FNAMEZIP="${FNAME}.zip"
  local -r EXECFILE="${FNAME}/ghq"
  local -r URL="https://github.com/x-motemen/ghq/releases/download/${VERSION}/${FNAMEZIP}"
  local -r DEST="${HOME}/bin"

  echo "========== Checking if $APPNAME is installed..."
  if command -v "$CMDNAME" &>/dev/null; then
    echo "========== $APPNAME is already installed!!"
  else
    echo "========== $APPNAME does not installed. Installing..."
  
    cd "$(mktemp -d)"
    curl -OL "$URL"
    ls -alFh
    unzip "$FNAMEZIP"
    mkdir -pv "$DEST"
    mv -fv "$EXECFILE" "$DEST"
  
    echo "========== $APPNAME was installed successflly!!"
  fi
}

main
```

### 2. インストール

```sh
./install-ghq.sh
========== Checking if ghq is installed...
========== ghq does not installed. Installing...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 3616k  100 3616k    0     0  3592k      0  0:00:01  0:00:01 --:--:-- 5029k
total 3.6M
drwx------  2 toor toor   60  9月  9 05:05 ./
drwxrwxrwt 21 root root  560  9月  9 05:05 ../
-rw-r--r--  1 toor toor 3.6M  9月  9 05:05 ghq_linux_amd64.zip
Archive:  ghq_linux_amd64.zip
   creating: ghq_linux_amd64/
  inflating: ghq_linux_amd64/CHANGELOG.md
  inflating: ghq_linux_amd64/CREDITS
  inflating: ghq_linux_amd64/LICENSE
  inflating: ghq_linux_amd64/README.adoc
  inflating: ghq_linux_amd64/ghq
   creating: ghq_linux_amd64/misc/
   creating: ghq_linux_amd64/misc/bash/
  inflating: ghq_linux_amd64/misc/bash/_ghq
   creating: ghq_linux_amd64/misc/zsh/
  inflating: ghq_linux_amd64/misc/zsh/_ghq
copied 'ghq_linux_amd64/ghq' -> '/home/toor/bin/ghq'
removed 'ghq_linux_amd64/ghq'
========== ghq was installed successflly!!
```

### 3. バージョン確認

まだ `~/bin` にパスを通していないので、直接叩く：

```sh
$ ~/bin/ghq --version
ghq version 1.6.2 (rev:d79add2)
```

無事動いた。一応ディレクトリはこんなかんじ：

```sh
$ ls -alFh ~/bin
total 8.1M
drwxr-xr-x  2 toor toor 4.0K  9月  9 05:05 ./
drwx------ 17 toor toor 4.0K  9月  9 03:47 ../
-rwxr-xr-x  1 toor toor 8.1M  7月 12 12:19 ghq*
-rwxr-xr-x  1 toor toor 7.5K  9月  9 03:47 proper7y*
```

## 環境

```sh
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

$ ~/bin/ghq --version
ghq version 1.6.2 (rev:d79add2)
```

不要だと思うが一応以下も載せとく：

```sh
$ mise --version
2024.8.14 linux-x64 (2ed1258 2024-08-27)

$ go version
go version go1.23.0 linux/amd64
```

## 感想

- 思ったより大事になってしまった
- Bash スクリプト自体は以前使ってたものをほぼそのまま流用できたのでそこは良かった

## 参考

- [ghq/README.adoc at master #INSTALLATION · x-motemen/ghq](https://github.com/x-motemen/ghq/blob/d79add20f26e7c079295e79496310ce3b6eabed1/README.adoc#installation)
- [Releases · x-motemen/ghq](https://github.com/x-motemen/ghq/releases)
- 検討したけど採用しなかったインストール方法に関するもの：
    - [AUR (en) - ghq-bin](https://aur.archlinux.org/packages/ghq-bin)
    - [Plugins | mise-en-place](https://mise.jdx.dev/plugins.html)
    - [mise-en-place](https://mise.jdx.dev/registry.html)
    - [mise-plugins](https://github.com/mise-plugins)
    - [mise-plugins/registry: Convenience shortname repository for mise plugins](https://github.com/mise-plugins/registry/tree/main)
    - [registry/plugins/ghq at main · mise-plugins/registry](https://github.com/mise-plugins/registry/blob/59f725bb521397cfa44a6623d3cbfebdccc47579/plugins/ghq)
    - [kajisha/asdf-ghq: ghq plugin for asdf version manager](https://github.com/kajisha/asdf-ghq)

- TODO:

## 関連リンク

- [x-motemen/ghq: Remote repository management made easy](https://github.com/x-motemen/ghq)
- [Songmu/ghq-handbook](https://github.com/Songmu/ghq-handbook)

## TODO

- [ ] mise のプラグイン (≒ asdf の) セキュリティ周りを深堀りしたい
- [ ] GitHub Releases にあるバイナリをよしなに取ってきてくれるツールほしい
