
===


## おまけ：mise から Golang をインストールしてみる

### 1. 利用可能な Golang のバージョンを確認する

```sh
$ mise ls-remote go
...
1.22.6
1.23rc1
1.23rc2
1.23.0
```

Ref: [Commands #ls-remote | mise-en-place](https://mise.jdx.dev/cli/#mise-ls-remote-options-tool-version-prefix)

### 2. 特定のバージョンのGolang をインストールする

```sh
$ mise use -g go@1.23
```

Ref: [Commands #use | mise-en-place](https://mise.jdx.dev/cli/#mise-use-options-tool-version)

### 3. グローバルで設定（有効化）する

```sh
$ mise use -g go@1.23
```
### 2. インストールの確認（バージョンを表示する）

```console
$ go version
go version go1.23.0 linux/amd64
```

無事動いている。おわり。

===

- [ ] 例えば、最新版の Golang をインストールしたいときに `$ mise use -g go@latest` ではできないっぽい？どうすればできる？
    - `$ mise latest` コマンドは関連する？
