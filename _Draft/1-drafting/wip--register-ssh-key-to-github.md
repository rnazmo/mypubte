---
mymetag_version: v3.0.0
id: f585a709-fde5-47d8-80ab-ee079d5b99ef
type: Scrap
status: ["visibility::public", "workflow::drafting"]
drafted_at: 2024-08-30T04:11
created_at: 2024-08-31T00:52
last_updated_at:
last_reviewed_at: TODO:
categories: ["Git", "GitHub", "GitLab"]
tags: ["SSH"]
keywords: ["tool::GitHub CLI", "公開鍵暗号", "RSA"]
title: "GitHub（または GitLab）に SSH の公開鍵を登録する"
aliases: ["Register SSH key with GitHub（or GitLab）", "Connect Git to GitHub（or GitLab）with SSH"]
---

## まとめ

- 手順：
    1. `ssh-keygen -t ed25519`
    2. `xclip -selection clipboard < ~/.ssh/id_ed25519.pub`
    3. [https://github.com/settings/ssh/new](https://github.com/settings/ssh/new) or [https://gitlab.com/-/profile/keys](https://gitlab.com/-/profile/keys) に追加する
    4. `ssh -T git@github.com` or `ssh -T git@gitlab.com` で接続を確認

## 経緯

- マシンのセットアップ時にここらへんの手順を毎回忘れるのでメモっておく

## 手順

### 1. 新しい SSH キーを生成する

- TODO:

```console
$ ssh-keygen -t ed25519
```

### 2. GitHub（または GitLab） に SSH の公開鍵を登録する

- TODO:

```console
- TODO:
```

### 3. 接続できることを確認する

- TODO:

```console
- TODO:
```

## 環境

- Git の初期設定（ユーザー名とメールアドレスの設定）は既にやってある
- Git から GitHub リポジトリに接続する場合は、HTTPS または SSH の 2 通りがあるが、今回は SSH のみを扱う
- 今回は GitHub CLI は使っていない（GitHub CLI を使って認証することもできる）

```console
- TODO:
```

## その他

- Git の初期設定：
    - 「Git の初期設定」∋「GitHub に SSH の公開鍵を登録する」、「Git にユーザー名とメールアドレスを設定する」

## 感想

- foo

## 脚注

[^1]: foobarbaz

## 参考

- GitHub に SSH の公開鍵を登録する：
    - [Git のセットアップ - GitHub ドキュメント](https://docs.github.com/en/get-started/getting-started-with-git/set-up-git#authenticating-with-github-from-git)
    - [新しい SSH キーを生成して ssh-agent に追加する - GitHub Docs](https://docs.github.com/ja/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- GitLab に SSH の公開鍵を登録する：
    - TODO:

## 関連リンク

- foo

## TODO

- [ ] GitHub CLI を使って認証することも可能らしいので、試す

## ChangeLog

- 2021 年頃
    - この記事は 2021 年頃に `setup` などに書き散らかしたメモを切り出して整えたものでる
