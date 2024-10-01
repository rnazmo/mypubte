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

### myenv-v3 で Neovim 設定周りをやるブランチを切る

- `feat(neovim)/setup-config`
- ブランチ切らなくても良くない？


### どのディレクトリにinit.luaを置けばよいのか

> どのディレクトリにinit.luaを置けばよいのか、どこのinit.luaが読みこまれるのか

[lazy.nvimのインストール方法とその使い方](https://zenn.dev/siteyo/articles/980b6205e93914#init.lua)

```sh
$ nvim -V1 -es -c "echo stdpath('config') . '/init.vim'" -cq
/home/toor/.config/nvim/init.vim
```

### 設定ファイルのディレクトリ構造はどうする？

- Ref:
    - [How I Setup Neovim To Make It AMAZING in 2024: The Ultimate Guide - YouTube](https://www.youtube.com/watch?v=6pAG3BHurdM&t=183s)
    - [How I Setup Neovim On My Mac To Make it AMAZING in 2024](https://www.josean.com/posts/how-to-setup-neovim-2024)
    - [dev-environment-files／.config／nvim at main · josean-dev／dev-environment-files](https://github.com/josean-dev/dev-environment-files/tree/cb670e8890ca9d8baf978b38ed75987b742032e6/.config/nvim)
    - [dotfiles／dot_config／nvim at main · ganyariya／dotfiles](https://github.com/ganyariya/dotfiles/tree/cee57f4349f524b4d73b1fa3394363ea4549312f/dot_config/nvim)

```sh
$ mkdir -p ~/.config/nvim/lua/rnazmo/core
$ mkdir -p ~/.config/nvim/lua/rnazmo/plugins
$ touch ~/.config/nvim/init.lua
$ touch ~/.config/nvim/lua/rnazmo/lazy.lua
$ touch ~/.config/nvim/lua/rnazmo/core/init.lua
$ touch ~/.config/nvim/lua/rnazmo/core/keymaps.lua
$ touch ~/.config/nvim/lua/rnazmo/core/options.lua

$ tree ~/.config/nvim
/home/toor/.config/nvim
├── init.lua
└── lua
    └── rnazmo
        ├── core
        │   ├── init.lua
        │   ├── keymaps.lua
        │   └── options.lua
        ├── lazy.lua
        └── plugins

5 directories, 5 files
```

### 超基本的な設定を書く

- 上記の動画を見ながら作業する
    - 少し脇道にそれるが、上記の動画でやってる便利そうな操作のメモ
        - `$ nvim .` で編集するファイルを良い感じに選択できる
        - (nvim 中で) `:Explore` コマンドで、そのまま別のファイルを編集できる
        - (nvim 中で) `:e foo/bar/baz.txt` コマンドで、そのまま別のファイルを編集できる
        - neovim の設定ファイルを編集中に、(nvim 中で) `source %` でその設定を適用
        - `:h autoindent`
- `vim.cmd("let g:netrw_liststyle = 3")`
    - この設定は何？
- `vim.g.mapleader = " "`
    - この設定は何？
    - leaderキー とは何？
        - 私のキーボード配列だと何か衝突しそうじゃない？
            - Space 長押しで Ctrl にしてる
            - 動く？
        - [VimのLeaderキーの設定｜かつお](https://note.com/noabou/n/n8b6cd0ced53e)
            - > デフォルトでは \ を押すと、○○する。という状態。

### 設定ファイル -> myenv-v3 のシンボリックリンクを貼る

TODO:

### プラグインマネージャー lazy.nvim の導入

TODO:

### 以降はプラグインを試しつつ導入していく

TODO:

### lualine.nvim

TODO:

### gpanders/editorconfig.nvim

TODO:
