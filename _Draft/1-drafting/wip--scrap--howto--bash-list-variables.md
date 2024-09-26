---
mymetag_version: v3.1.0
id: 345f67d1-22ee-4cd9-8ccd-8c93ce1057d9
type: Scrap
status: ["visibility::public", "workflow::drafting"]
drafted_at: 2024-09-26T15:09
created_at: 2024-09-26T15:09
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::howto"]
tags: ["tool::Bash"]
keywords: ["変数", "shell_script"]
title: "howto］Bash：変数を一覧する方法まとめ（v2024-09"
aliases: ["howto］Bash：How to list variables（v2024-09"]
---

## まとめ

- TODO:

## この記事の目的・方針

- See: [purpose-and-policy］`how_to` シリーズの目的・方針（v2024-09](TODO.md)

## やりたいこと

- Bash (シェルスクリプト) において、変数を一覧したい

## 前提知識

- 「**変数の種類**」について：
    - See: [Bash：変数の種類について調べた（シェル変数・環境変数）（v2024-09](07fa69d1-2266-4981-a596-75a188277129.md)

## 変数の一覧方法

### シェル変数

```sh
set

declare?
```

現在のシェルで定義されているすべてのシェル変数が表示される。

#### 例

```sh
TODO:
```

### 環境変数


```sh
export -p

# または

env

# または

printenv
```

#### 例

```sh
TODO:
```

## 環境

```sh
$ proper7y
TODO:

$ foo --version
TODO:
```

## 感想

- 特に無し

## 参考

- [とほほのBash入門 #5.シェル変数と環境変数 - とほほのWWW入門](https://www.tohoho-web.com/ex/shell.html#variables)

## 関連リンク
