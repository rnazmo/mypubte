---
frontmatter_version: TODO
id: "fe3d42f4-afc9-45ab-bfbc-49b197cbe513"
type: Scrap
drafted: 2024-07-06T04:31
created: 2024-07-06T04:41
updated: N/A
checked: 2024-07-06T06:26
title: "［Bash］Bashのバージョン番号が一定以上であることをチェックする"
title_en: TODO
tags: ["bash", "bash_script"]
categories: ["bash"]
---

## TL;DR

- 組み込み変数 `$BASH_VERSINFO` を利用する
    - これには解析済みのバージョン情報が格納されている

## 要求

- Bash スクリプトにおいて、「現在実行中の Bash のバージョンが 4.2 以上であるかどうか」で処理を分岐させるコードがほしい。


## コード

```bash
check_bash_version() {
    # Bashのバージョンを取得
    local major_version=${BASH_VERSINFO[0]}
    local minor_version=${BASH_VERSINFO[1]}

    # バージョンが4.2以上かどうかをチェック
    if (( major_version > 4 )) || (( major_version == 4 && minor_version >= 2 )); then
        echo "Bashのバージョンは4.2以上です。"
    else
        echo "Bashのバージョンは4.2未満です。"
    fi
}
```

## 解説

- `$BASH_VERSINFO`: バージョン情報が格納されている組み込み変数。
そこからメジャーバージョンとマイナーバージョンを取り出し、これを比較している。

### `BASH_VERSINFO` について詳しく

- Bash の組み込み変数（配列）。現在実行中の Bash のバージョン情報が、解析済みの状態で格納されている。
- この配列には次の要素が含まれている：
    - $BASH_VERSINFO[0]: メジャーバージョン番号
    - $BASH_VERSINFO[1]: マイナーバージョン番号
    - $BASH_VERSINFO[2]: パッチレベル
    - $BASH_VERSINFO[3]: ビルド番号
    - $BASH_VERSINFO[4]: リリースステータス（例: "release"）
    - $BASH_VERSINFO[5]: マシンタイプ（例: "x86_64-pc-linux-gnu"）

#### 例

```text
BASH_VERSINFO=([0]="5" [1]="2" [2]="26" [3]="1" [4]="release" [5]="x86_64-pc-linux-gnu")
```

```bash
$ echo ${BASH_VERSINFO[@]}
5 2 26 1 release x86_64-pc-linux-gnu
```

### その他の方法について

- `bash --version` コマンドや `BASH_VERSION` 変数もバージョン情報を出力する。しかし、これらが出力する情報は冗長で未解析である。なので `BASH_VERSINFO` を使ったほうが良い。

```bash
$ bash --version
GNU bash, version 5.2.26(1)-release (x86_64-pc-linux-gnu)
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

This is free software; you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

$ echo $BASH_VERSION
5.2.26(1)-release
```

## 実行例

### スクリプト

```bash
$ cat ./check_bash_version.sh 
#!/bin/bash
set -eu

check_bash_version() {
    # Bashのバージョンを取得
    local major_version=${BASH_VERSINFO[0]}
    local minor_version=${BASH_VERSINFO[1]}

    # バージョンが4.2以上かどうかをチェック
    if (( major_version > 4 )) || (( major_version == 4 && minor_version >= 2 )); then
        echo "Bashのバージョンは4.2以上です。"
    else
        echo "Bashのバージョンは4.2未満です。"
    fi
}

check_bash_version
```

### 結果

```bash
$ ./check_bash_version.sh 
Bashのバージョンは4.2以上です。
```

### 環境

```bash
$ ./proper7y/proper7y 
proper7y v0.4.2 - A tiny Bash script to get OS and other
software version info. https://github.com/rnazmo/proper7y
============================================================

OS NAME      : Manjaro Linux
OS VERSION   : 24.0.3
Current Shell: Bash
Bash VERSION : 5.2.26(1)-release (x86_64-pc-linux-gnu)
Zsh VERSION  : 5.9 (x86_64-pc-linux-gnu)
CPU ARCH     : x86_64
============================================================
```
