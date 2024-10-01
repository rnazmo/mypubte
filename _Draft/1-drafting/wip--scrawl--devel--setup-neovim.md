---
mymetag_version: v3.1.0
id: 60fd3412-5a3d-45e3-8f37-79633ad2d2e0
type: Scrawl
status: ["visibility::public", "workflow::drafting"]
drafted_at: 2024-10-01T14:15
created_at: 2024-10-01T14:15
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::devel", "project::my_web_tools"]
tags:
keywords:
title: "devel］myenv-v3：Neovim の設定を整える作業メモ（2024-10-01"
aliases:
---

## 2024-10-01

### モチベ

- [フレームワークをやめて 1 から neovim をセットアップしたら理解がとても進んだという話](https://zenn.dev/ganariya/articles/setup-neovim-from-scratch-instead-of-framework)

### 何やるか

- 最低限の設定を整えることを目標にする
- VS Code ぽい機能が欲しい

### AstroNvim ? -> x

- AstroNvim はかなり良さそうだったが、導入が上手く行かなかった
    - ここでの導入はインストール作業のことではなく、身体に染み込ませることの意
- 何となく思ってたことがこの記事で言語化されてた
    - [フレームワークをやめて 1 から neovim をセットアップしたら理解がとても進んだという話](https://zenn.dev/ganariya/articles/setup-neovim-from-scratch-instead-of-framework)
- AstroNvim (などの Neovim フレームワーク) は、無しの方向性で
- 手書きで AstroNvim のクローンを作るイメージ？でいく
- Neovim のカスタマイズに十分習熟した後に、楽をするためにフレームワーク (AstroNvim, LazyVim) を採用するのはアリかもね

### フレームワークを使わない場合、まず何をすれば良い？

- [ ] 設定ファイルのディレクトリ構造はどうするのがスタンダード？
- [ ]`init.lua` みたいなところに、超基本的な設定を書く
    - 行番号の表示とか、インデントサイズとかそういうの
    - 前の `setup`(= myenv-v1) で使っていた設定ファイルが使えるんじゃない？
- [ ] プラグインマネージャー `lazy.nvim` の導入
    - 今回の設定のコアというか、中心部分
- [ ] 追加するプラグインを選定し、一つ一つ追加していく
    - ここだいぶ苦戦しそう
    - 選択肢が多すぎて、何もわからない
    - これ良さそう：[Table of Contents | my-neovim-pluginlist](https://yutkat.github.io/my-neovim-pluginlist/go.html)
        - 神では
        - [Neovimプラグインをまともに選定できるリストを作った](https://zenn.dev/yutakatay/articles/neovim-pluginlist)

### lazy.nvim と LazyVim は違う；LazyVim -> x

- これ気が付くまで時間が掛かってだいぶ混乱した
- 違い：
    - lazy.nvim：プラグインマネージャー
    - LazyVim：フレームワーク
        - フレームワークって言い方であってるのか？
- 名前がややこしすぎる
    - と思ったが、作者が同じっぽい
        - なら仕方ないか…
    - [PSA: LazyVim is different from lazy.nvim : r／neovim](https://www.reddit.com/r/neovim/comments/12y8to6/psa_lazyvim_is_different_from_lazynvim/)
- 当然今回は LazyVim は使わない

### プラグインマネージャーは lazy.nvim を使う

- 今はプラグインマネージャーはこれ一択っぽい空気感（たぶん）。とても良さそう

### 設定ファイルのディレクトリ構造はどうする？

TODO:

### 超基本的な設定を書く

TODO:

### プラグインマネージャー lazy.nvim の導入

TODO:

### 以降はプラグインを試しつつ導    入していく

TODO:

### lualine.nvim

TODO:

### gpanders/editorconfig.nvim

TODO:
