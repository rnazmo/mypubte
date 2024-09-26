---
mymetag_version: v3.1.0
id: 07fa69d1-2266-4981-a596-75a188277129
type: Scrap
status: ["visibility::public", "workflow::drafting"]
drafted_at: 2024-09-26T14:57
created_at: 2024-09-26T14:57
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::research"]
tags: ["tool::Bash"]
keywords: ["変数", "shell_script"]
title: "Bash：変数の種類について調べた（シェル変数・環境変数）（v2024-09"
aliases:
---

シェル変数、環境変数、ユーザー定義変数、システム定義変数
あたりがよくわからん。
日本語の記事はあるけど、一次ソースが見つからない


- 「シェル変数 (shell variable)」と「環境変数 (environment variable」という用語の定義がよくわからない
    - 日本語で書かれた記事はたくさんあったものの、信頼性の高そうな一次情報が見つからなかった
    - Bash の Manual をチラッと見る限り、"shell variable" ∋ "environment variable" っぽい印象を受けるんだけど、どうなんだろう
    - Bash 独自の仕様と POSIX の仕様を区別する必要ありそう
        - Ref: [シェルスクリプト 変数の型を確認したい。](https://teratail.com/questions/46809)


- Ref:
    - [Shell Command Language #export](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html#export)
        - > export - set the export attribute for variables
        - > The shell shall give the export attribute to the variables corresponding to the specified names, which shall cause them to be in the environment of subsequently executed commands.
    - [Shell Command Language #2.5.3-Shell-Variables](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html#tag_18_05_03)
        - > Variables shall be initialized from the environment (as defined by XBD Environment Variables and the exec function in the System Interfaces volume of POSIX.1-2017) and can be given new values with variable assignment commands. If a variable is initialized from the environment, it shall be marked for export immediately; see the export special built-in.
- 上記を参照して、次のような理解
    - 「環境変数 (environment variable)」：エクスポート属性 (export attribute) が与えられた「シェル変数 (shell variable)」
    - つまり、概念的には「**シェル変数 ∋ 環境変数**」
        - そして内部の実装的には「シェル変数 ∈ 環境変数」ということなのかな
- 正直あまり自信は無い





## まとめ

- TODO:
- Bash の変数には、主にシェル変数と環境変数がある
    - これも要はスコープの違いではある
- **シェル変数**：
    - 現在実行中のシェルセッション内でのみ有効
- **環境変数**：
    - シェル変数のうち、エクスポート属性が与えられたもの
    - 現在のシェルだけでなく、そのシェルから起動された子プロセス（他のシェルやプログラム）でも有効
    - つまり、他のプログラムやスクリプトでもその値が利用可能






## この記事の目的・方針

TODO:

<!-- - See: [purpose-and-policy］`how_to` シリーズの目的・方針（v2024-09](TODO.md) -->


## 注意事項

- TODO:

## foo


## 環境

```sh
$ proper7y
TODO:

$ foo --version
TODO:
```

## 感想

- 一次情報探したけど見つからない。よくわからん。
    - Bash 独自の仕様と POSIX の仕様を区別する必要ありそう
        - Ref: [シェルスクリプト 変数の型を確認したい。](https://teratail.com/questions/46809)
- TODO:

## 脚注

[^1]: foobarbaz


## 参考

- [とほほのBash入門 #5.シェル変数と環境変数 - とほほのWWW入門](https://www.tohoho-web.com/ex/shell.html#variables)


## 関連リンク

- TODO:

## ChangeLog

- 2027-08-05 TODO:

## TODO

- [ ] TODO:
