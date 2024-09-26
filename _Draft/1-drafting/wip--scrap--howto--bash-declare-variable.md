---
mymetag_version: v3.1.0
id: 0b7abb9a-9f87-40aa-9ef0-aaa416361c97
type: Scrap
status: ["visibility::public", "workflow::drafting"]
drafted_at: 2024-09-26T10:51
created_at: 2024-09-26T10:51
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::howto"]
tags: ["tool::Bash"]
keywords: ["変数", "変数宣言", "shell_script"]
title: "howto］Bash：変数を宣言する方法（v2024-09"
aliases: ["howto］Bash：How to decrare variable（v2024-09"]
---

## まとめ

- TODO:

## この記事の目的・方針

- See: [purpose-and-policy］`how_to` シリーズの目的・方針（v2024-09](TODO.md)

## やりたいこと

- Bash (シェルスクリプト) において、変数を宣言したい

## 注意事項

- 変数の命名規則について
    - Bash では、変数の命名規則に厳密なルールはない (慣習的なルールはある)
    - この記事では「変数であること」をわかりやすくするために、変数は全てアッパースケークケースとした

## 前提知識・関連知識の説明

Bash における用語などの説明。

### 変数の種類について

- **シェル変数**：現在実行中のシェルセッション内でのみ有効
- **環境変数**：シェル変数のうち、エクスポート属性が与えられたもの。現在のシェルだけでなく、そのシェルから起動された子プロセス（他のシェルやプログラム）でも有効
- See: [Bash：変数の種類について調べた（シェル変数・環境変数）（v2024-09](07fa69d1-2266-4981-a596-75a188277129.md)

### シェル変数のスコープについて

- **グローバルスコープ**：**スクリプト全体**で参照可能
- **ローカルスコープ**：**関数内でのみ**参照可能

### 「読み取り専用」について

- 読んで字のごとく、一度値を設定すると変更できない
- 読み取り専用の変数の値を変更しようとすると、エラーになる

### 関連する組み込みコマンドについて

- **declare**
    - オプションで属性を付与しつつ、変数を宣言するコマンド
    - 関数内外で使用可能。ただし、挙動が変わる
        - 関数外：デフォルト (オプション無し) の場合、グローバル変数として宣言される
        - 関数内：デフォルト (オプション無し) の場合、ローカル変数として宣言される
- **readonly**
    - 変数を読み取り専用として宣言するコマンド
    - 関数内外で使用可能
- **local**
    - 関数内でローカル変数を宣言するコマンド
    - 関数内でのみ使用可能

## シェル変数の宣言方法

- 最初に注意点として、`=` の左右にスペースを入れてはいけない[^2]
- 上述の通り、`declare` はデフォルト (オプション無し) では関数の内外で挙動が変わることに注意する

### グローバルスコープ、かつ非読み取り専用

```sh
MY_VAR="global value"

# または

# 関数外で
declare MY_VAR="global value"

# 関数内で
foo() {
    declare -g MY_VAR="global value"
}
```

- 注意：`declare` の `-g` オプションは、関数内でのみ使用可能

<details>

<summary>例</summary>

#### example.sh

```sh
#!/bin/bash

MY_VAR_1="MY_VAR_1 is global"
echo $MY_VAR_1

foo() {
    declare -g MY_VAR_2="MY_VAR_2 is global"
}
foo
echo $MY_VAR_2
```

#### 結果

```sh
# TODO:
```

</details>

### グローバルスコープ、かつ読み取り専用

```sh
readonly MY_VAR="global-readonly value"

# または

declare -r MY_VAR="global-readonly value"
```

<details>

<summary>例</summary>

#### example.sh

```sh
#!/bin/bash

readonly MY_VAR="MY_VAR is readonly"
echo $MY_VAR

MY_VAR="new value" # エラーになる
echo $MY_VAR
```

#### 結果

```sh
# TODO:
```

</details>

### ローカルスコープ、かつ非読み取り専用

```sh
foo() {
    local MY_VAR="local value"

    # または

    declare MY_VAR="local value"
}
```

<details>

<summary>例</summary>

#### example.sh

```sh
#!/bin/bash

foo() {
    local MY_VAR="MY_VAR is local"
    echo $MY_VAR
}
foo
echo $MY_VAR # 参照できない
```

#### 結果

```sh
# TODO:
```

</details>

### ローカルスコープ、かつ読み取り専用

```sh
foo() {
    local -r MY_VAR="local-readonly value"

    # または

    declare -r MY_VAR="local-readonly value"
}
```

<details>

<summary>例</summary>

#### example.sh

```sh
#!/bin/bash

foo() {
    local -r MY_VAR="MY_VAR is local-readonly"
    echo $MY_VAR
}
foo
MY_VAR="new value" # エラーになる
```

#### 結果

```sh
# TODO:
```

</details>

### 変数のエクスポート (環境変数の宣言方法)

```sh
export MY_VAR="environment value"

# または

declare -x MY_VAR="environment value"
```

## 特殊なシェル変数の宣言方法

- あまり使うことは無いと思うが、一応メモしておく

### 名前参照

- 名前参照 (name reference) とは？
    - Bash の機能
    - ファイルのシンボリックリンクみたいなもの
- Ref:
    - [【 unset 】コマンド――変数や関数を削除する：Linux基本コマンドTips（307） - ＠IT](https://atmarkit.itmedia.co.jp/ait/articles/1905/24/news015.html)

```sh
declare -n REF=ORIGINAL_VAR

# または

foo() {
    local -n REF=ORIGINAL_VAR
}
```

<details>

<summary>例</summary>

#### example.sh

```sh
# TODO:
```

#### 結果

```sh
# TODO:
```

</details>

## データ型ごとの変数宣言方法

### 文字列

```sh
MY_NAME="John"
```

### 整数

```sh
MY_NUM=5

# または、declare を使って明示的に型を指定することも可能

declare -i MY_NUM=5
```

### 配列

```sh
MY_FRUITS=("apple" "banana" "cherry")

# または、declare を使って明示的に型を指定することも可能

declare -a MY_FRUITS=("apple" "banana" "cherry")
```

### 連想配列

```sh
MY_COLORS=(["red"]="FF0000" ["green"]="00FF00" ["blue"]="0000FF")

# または、declare を使って明示的に型を指定することも可能

declare -A MY_COLORS=(["red"]="FF0000" ["green"]="00FF00" ["blue"]="0000FF")
```

## 上述の各宣言方法はどのバージョンから使えるか

- `declare`, `readonly`, `local`, `export`：Bash の初期バージョンから
- `local` コマンドの `-r` オプション：Bash 4.2 (リリース日：2011-02-13) 以降
- 名前参照：Bash 4.3 (リリース日：2014-02-26) 以降
- 連想配列：Bash 4.0 以降

## どれを使えばよいのか

- 基本全部読み取り専用で良い。その上で、なるべくローカルスコープにする
    - ローカルな変数は `local -r`
        - ローカル変数を定義するときは、暗黙的にローカルになる `declare` よりも、明示的にローカルにする `local` の方が良い
        - [Google Style Guides](https://google.github.io/styleguide/shellguide.html#use-local-variables) でもそうなってる
    - グローバルな変数は `readonly`

## 環境

```sh
$ proper7y
TODO:

$ foo --version
TODO:
```

## 感想

- 今まであまり使っていなかったが、`declare` コマンド便利そうだな

## 脚注

[^1]: =の前後にスペースがある場合、それは変数宣言ではなく「コマンドとその引数たち」として解釈される。Ref: [bashの変数代入の=の前後にスペースを入れてはいけない理由 - mollifier delta blog](https://mollifier.hatenablog.com/entry/20081002/1222954180)

## 参考

- Bash の変数宣言方法：
    - [シェルスクリプトにおける変数定義 ＃ShellScript - Qiita](https://qiita.com/take_o/items/56ef2469e8648c08f118)
    - [Bashでは'readonly'より'local -r'を使っていきたい - MPのご利用は計画的に](https://footaku.hatenablog.com/entry/2018/09/03/140000)
    - [How to create a local read-only variable in bash? - Stack Overflow](https://stackoverflow.com/a/34011707)
    - [【 declare 】コマンド――変数を宣言する、変数などの内容を表示する：Linux基本コマンドTips（308） - ＠IT](https://atmarkit.itmedia.co.jp/ait/articles/1905/30/news017.html)
    - [Bash Reference Manual #declare](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#index-declare)
    - [Bash Reference Manual #local](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#index-local)
    - [Bash Reference Manual #readonly](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#index-readonly)
- 名前参照：
    - [【 declare 】コマンド――変数を宣言する、変数などの内容を表示する：Linux基本コマンドTips（308） - ＠IT](https://atmarkit.itmedia.co.jp/ait/articles/1905/30/news017.html)
    - [【 unset 】コマンド――変数や関数を削除する：Linux基本コマンドTips（307） - ＠IT](https://atmarkit.itmedia.co.jp/ait/articles/1905/24/news015.html)
    - [Bash 5.0の新機能：namerefの挙動の変更 ＃Bash - Qiita](https://qiita.com/emasaka/items/3cc1541d9eed5d7a5f6c)
- Bash のシェル変数と環境変数の違い：
    - [シェル変数と環境変数の違い（bash） - Qiita](https://qiita.com/Kotabrog/items/144e6e314ce82fb3f683)
- Bash のデータ型について：
    - [シェルスクリプト 変数の型を確認したい。](https://teratail.com/questions/46809)

## 関連リンク

- [Bash Reference Manual](https://www.gnu.org/software/bash/manual/bash.html)
- [とほほのBash入門 - とほほのWWW入門](https://www.tohoho-web.com/ex/shell.html#variables)
- [styleguide | Style guides for Google-originated open-source projects](https://google.github.io/styleguide/shellguide.html)
-[GoogleのShell Style Guideの邦訳 ＃Linux - Qiita](https://qiita.com/yabeenico/items/72b904d4bb0b6d732a86)
- [Shell scripting standards and style guidelines | GitLab](https://docs.gitlab.com/ee/development/shell_scripting_guide/)
- [Shell Command Language](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html)
- [変数を使用する | UNIX & Linux コマンド・シェルスクリプト リファレンス](https://shellscript.sunone.me/variable.html)

## TODO

- 「変数を宣言する」と「変数を定義する」のどちらが正しいの？
    - Bash の場合
- POSIX シェルのドキュメントを軽く読む
    - これ [Shell Command Language](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html)
