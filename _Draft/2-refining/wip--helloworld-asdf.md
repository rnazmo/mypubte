---
mymetag_version: v2.1.0
id: 2e138b3d-d904-4140-93aa-d4ddc8c8a540
type: Scrap
drafted_at: 2024-08-27T23:16
created_at: 2024-08-27T23:16
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::helloworld", "tool::asdf"]
tags:
keywords: ["version manager"]
title: "helloworld］asdf に Hello World する（v2024-08"
aliases: ["helloworld］Hello World in asdf（v2024-08"]
---

## まとめ

- 手順：
    1. 依存である git と curl を適当に入れる
    2. asdf 本体を git clone する
    3. シェル (Zsh) にパスを追記する。おわり。

## 目的と方針

See: [helloworld］helloworld シリーズのテキストを書く目的・方針（v2024-08](./a8edd76c-963b-4cd1-affc-fc8be160ca11.md)

## asdf とは何か

- プログラミング言語やツールのバージョン管理を行う CLI ツール
- 詳細はここでは触れない

## 今回やること

- asdf をインストールする
- おまけ：それを使って特定のバージョンの Golang をインストールする

## 手順

### 1. asdf をインストールする

#### 1-1. 依存関係のインストール

`git` と `curl` が必要なので入れる：

```console
$ sudo pacman -S curl git
```

#### 1-2. asdf 本体のダウンロード

```console
$ cd

$ git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.14.1
```

```console
$ ls -alFhd ./.asdf
drwxr-xr-x 10 toor toor 4.0K  8月 27 22:19 ./.asdf/
```

#### 1-3. asdf 本体のインストール

Zsh に下記を追加する：

```zsh
. "$HOME/.asdf/asdf.sh"
```

PATHの変更が有効になるように、シェルを再起動する。ターミナルのタブを一旦閉じて開き直せばOK。（たぶん `source` するのでもいけるはず）

### 2. Hello World する

Hello World とは表示できないので、代わりにバージョンを表示してみる：

```console
$ asdf --version
version: v0.14.1-f00f759
```

無事、インストールができた。

## おまけ：asdf から Golang をインストールしてみる

### 1. Golang のプラグインをインストールする

```console
$ asdf plugin add golang https://github.com/asdf-community/asdf-golang.git
```

### 2. Golang のバージョンをインストールする

まずはインストール可能なバージョンの一覧を確認：

```console
$ asdf list-all golang
...
1.23.0
1.23rc1
1.23rc2
```

```console
$ asdf install golang 1.22.0
```

最新バージョンをインストールしたい場合、次のコマンドでもよい：

```console
$ asdf install golang latest
```

インストールした Golang のバージョン一覧を確認：

```console
$ asdf list golang
  1.22.0
  1.23.0
```

### 3. Golang のバージョンを有効化する

インストールした Go のバージョンをグローバルまたはローカルで有効化するコマンドは次の通り：

```console
$ asdf global golang 1.23.0  # グローバル設定
# または
$ asdf local golang 1.23.0   # プロジェクトごとの設定
```

今回はグローバルでの有効化を試してみる：

```console
$ asdf global golang 1.23.0

$ go version
go version go1.23.0 linux/amd64
```

バージョンを変えてみる：

```console
$ asdf global golang 1.22.0

$ go version
go version go1.22.0 linux/amd64
```

以上でおわり。

## 環境

- OS: Manjaro
- shell: Zsh
- oh-my-zsh などの Zsh フレームワークは使っていない
- package manager: pacman (, pamac)

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

$ asdf --version
version: v0.14.1-f00f759

$ git --version
git version 2.45.2

$ curl --version | head -n1
curl 8.8.0 (x86_64-pc-linux-gnu) libcurl/8.8.0 OpenSSL/3.3.1 zlib/1.3.1 brotli/1.1.0 zstd/1.5.6 libidn2/2.3.7 libpsl/0.21.5 libssh2/1.11.0 nghttp2/1.62.1 nghttp3/1.4.0
```

## 感想

- asdf 本体のインストールがややこしくて面倒
- asdf 自体はかなり良さそう

## 脚注

[^1]: foobarbaz

## 参考

- [asdf | asdf](https://asdf-vm.com/)
- TODO:

## 関連リンク

- [asdf-vm/asdf: Extendable version manager with support for Ruby, Node.js, Elixir, Erlang & more](https://github.com/asdf-vm/asdf)

## TODO

- [ ] foo
