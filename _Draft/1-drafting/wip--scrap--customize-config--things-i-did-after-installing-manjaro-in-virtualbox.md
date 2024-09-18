---
mymetag_version: v3.1.0
id: 8ea5cc93-38f5-4255-b6dd-1b2d1f354c27
type: Scrap
status: ["visibility::public", "workflow::drafting"]
drafted_at: 2024-09-17T04:04
created_at: drafted_at: 2024-09-17T04:04
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::customize-config", "tool::Manjaro"]
tags: ["tool::VirtualBox", "desktop_environment::Xfce", "configuration"]
keywords:
title: "customize-config］Manjaro：Manjaro 24.0（Xfce 版）を VirtualBox 7.0 にインストールした後にやったこと（v2024-09"
aliases: ["customize-config］Manjaro：Things I did after installing Manjaro 24.0（Xfce edition）in VirtualBox 7.0（v2024-09"]
---

## まとめ

- 多すぎてまとめられない。手順の項を参照のこと

## 経緯

- 前回 (下記リンク) はインストールまでやったので、次は最低限の設定を行っていく
    - [installed］Manjaro：VirtualBox 7.0 に Manjaro 24.0（Xfce 版）をインストールした（v2024-09](7404b72d-2f50-47eb-aa8f-1bf8b31aec81.md)

## やりたかったこと

- 仮想マシンの Manjaro に対し、最低限の設定を行う

## やったこと・手順

### 前提

- マシンは[前回](7404b72d-2f50-47eb-aa8f-1bf8b31aec81.md)作ったやつであり、かつ作った直後の状態である

### 01. ミラーサーバーの変更をした

```sh
sudo pacman-mirrors --fasttrack
```

少し時間がかかる (3-4 分くらい)

### 02. システム（パッケージ）の更新をした

```sh
sudo pacman -Syy
```

### 03. 日本語入力の設定をした

1. fcitx-mozc のインストール
    1. スタートメニューから `Manjaro Hello` アプリを再度起動する
    2. 真ん中の下あたりにある `Applications` を選択する
    3. `Extended language support` > `Manjaro Asian Input Support Fcitx` にチェックを入れ、右上の `UPDATE SYSTEM` を選択する
    4. `Choose optional depdendencies for manjaro-asian-input-support-fcitx` というウィンドウが出てくるので、`fcitx-mozc: 日本語 | Japanese` にチェックを入れ、次へ
    5. 確認画面が出てくるので、`Apply` を選択して次へ進む
    6. 少し待つ
    7. おわり
2. 言語パッケージ (？) の追加インストール
    1. スタートメニューから `Manjaro Setting Manager` アプリを起動する
    2. `Language Packages` を選択する
    3. 右上の `Install Packages` を選択する
3. マシンを再起動する
4. 英語・日本語の入力切り替えにショートカットを割り当てる (注：私の今のキーボードには**半角・全角キーが無い**)：
    1. スタートメニューから、`Fcitx Configuration` アプリを起動する
    2. 最初の画面 (＝ `Input Method` タブ) の左下の `+` を選択する
    3. `Add input method` ウィンドウが開くので、**`Only Show Current Languages` のチェックを外し**、`Mozc` を探して選択する
        - Input Method の順序は特に弄らないで良い (`Keyboard-English (US)` => `Mozc`)
    4. Optional：`Global Config` タブを開き、`Trigger Input Mehtod` の `Ctrl+Space` を `Alt+\`` (など) に**上書き**する
        - NOTE: **`Ctrl+Space` は VS Code の「サジェストのトグル」みたいなショートカットキーと被って**て、後々困るので変更した
            - 今までは `Ctrl+Space` でやっていたが、丁度良い機会ということで変えた
            - 私の今のキーマップ的に Alt は誤動作しやすく、かなり使いづらいけどどうしようこれ…
5. スタートメニューから、**メモ帳アプリ `Mousepad`** を起動して、日本語入力ができることを試す
    - ここまででで、日本語入力ができるようになっているはずである
    - 切り替えのショートカットキーは、先程変更した通り**`Alt+\``** である
6. おわり

- 日本語入力周りの設定、全然よくわからん。
- TODO: fcitx から fcitx5 に乗り換えた方が良さそう

### 04. 日本語フォントをインストールした

```sh
sudo pacman -S noto-fonts-cjk
```

- システムのフォントを (日本語対応フォントに) 変更する必要ある？
    - -> システムの言語を英語で使ってるから、無い
    - システムの言語を日本語で使いたいなら、必要かも
- だが、それはそれとして noto-fonts-cjk はインストールしておいた

### 05. 時刻同期とタイムゾーンの設定をした

1. スタートメニューから `Manjaro Setting Manager` アプリを起動する
2. `Time and Date` を選択する
3. `Set time and date automatically` にチェックが入っていることを確認する
4. `Time zone` が `Asia/Tokyo` であることを確認する
5. おわり

時刻同期はトラブると結構面倒な印象。Manjaro は GUI でできて楽で良いね。

### 06. ロケールの設定を確認した（がよくわからないのでスルーした）

もうだいぶ疲れてきて、かなり適当になっている。

1. スタートメニューから `Manjaro Setting Manager` アプリを起動する
2. `Locale Settings` を選択する
3. よくわからないが、何となく大丈夫そうなことを確認する
4. おわり

### 07. ファイアウォールの設定をした

1. スタートメニューから、ファイアウォールアプリ `Gufw` 起動する
2. `Status` を on にトグルする
3. おわり

注：細かい設定についてはここでは触れない

### 08. パネルをデスクトップ下段から上段に移動した

- パネル ＝ Windows で言うタスクバー

1. パネル上で右クリックし、`Panel Preferences` を選択し、`Panel Preferences` ウィンドウを出す
    - スタートメニューから `panel` で検索して起動しても良い
2. 上部のメニューの `Display` タブの、`Lock panel` のチェックを外す
3. パネルの左右の端をマウスで掴んで上端まで移動させる
4. `Lock panel` のチェックを付け直す
5. おわり

### 09. Thunar で隠しファイルを表示するように設定した

1. スタートメニューから、ファイルマネージャーアプリ `Thunar` 起動する
2. 上部のメニューの `View` を選択する
3. `Show Hiden Files` にチェックを入れる
4. おわり

### 10.　一旦、仮想マシンのスナップショットを作成しておいた

1. 一度、仮想マシンをオフにする
2. メニューから `スナップショット` > `作成` を選択する
3. 名前と説明を適当に入力して、作成する
4. おわり

### 11. パネルを更に弄った

パネルの設定をもうちょいやり直す。

1. パネル上で右クリックし、`Panel Preferences` を選択し、`Panel Preferences` ウィンドウを出す
    - スタートメニューから `panel` で検索して起動しても良い
2. 上部のメニューの `Display` タブを選択する
    - `Measurements` の `Row size (pixels):` の値を `30` にしてみた
3. 上部のメニューの `Appearance` タブを選択する
    - `Icons` の `Adjust size automatically` にチェックを入れる
    - `Icons` の `Adjust size automatically` にチェックを入れる
4. 上部のメニューの `Items` タブを選択する
    - `System Load Monitor` を追加し、設定を弄る
        - `Network monitor`：チェックを外す
        - `Uptime monitor`：チェックを外す
            - 開発用仮想マシンなら不要でしょう
    - `Network Monitor` を追加し、設定を弄る
        - `Text to display`：チェックを外す
        - `Network device`：良い感じのやつを選択する
        - `Update interval`：`0.50`s
        - `Present data as`：`Bars and values`
        - `Colorize values`：チェックを入れる
        - `Digits number`：`1`
    - 順番は適当に良い感じに変更する (各アイテムをドラッグアンドドロップで順序を変えれる)
5. おわり

### 12. 最低限のパッケージ（git, curl, vim, base-devel, yay）のインストールをした

```sh
sudo pacman -S --needed git curl vim base-devel yay
```

注：yay を pacman でインストールできるのは Manjaro だから。(Arch Linux はダメ)

### 13. Git の初期設定をした

1. グローバル設定の登録
    - `git config --global user.name "rnazmo"`
    - `git config --global user.email "rnazmo@gmail.com"`
2. GitLab, GitHub への SSH 接続設定
    - See: [Git：GitHub（または GitLab）に SSH キーを登録する手順（GitHub CLI 無し）（v2024-09](f585a709-fde5-47d8-80ab-ee079d5b99ef.md)
    - 要点のみメモ：
        - `ssh-keygen -t ed25519`
        - `xclip -sel c < ~/.ssh/id_ed25519.pub`
        - [https://github.com/settings/ssh/new](https://github.com/settings/ssh/new)
        - [https://gitlab.com/-/user_settings/ssh_keys](https://gitlab.com/-/user_settings/ssh_keys)
        - `ssh -T git@github.com`
        - `ssh -T git@gitlab.com`

### 14. myenv-v3 を適用した

```sh
$ /bin/bash -c "$(curl -fsSL https://gitlab.com/rnazmo/myenv-v3/-/raw/main/init.bash)"

$ cd ~/.myenv-v3 && ./setup.bash "soba"

# Then reboot your machine
```

- myenv-v3 = dotfiles 含むプロビジョニング用スクリプト

### 15. この後やるべきことのメモ

ここまでで大体の設定がおわり。

- 今回やっていないが、やり残したこと：
    - スクリーンセーバーの設定を弄る
    - 再度スナップショットを作成
    - など

## 環境

### ゲスト (= VirtualBox の仮想マシン)

```sh
$ ~/bin/proper7y 
proper7y v0.4.2 - A tiny Bash script to get OS and other
software version info. https://github.com/rnazmo/proper7y
============================================================
OS NAME      : Manjaro Linux
OS VERSION   : 24.0.8
Current Shell: Bash
Bash VERSION : 5.2.32(1)-release (x86_64-pc-linux-gnu)
Zsh VERSION  : 5.9 (x86_64-pc-linux-gnu)
CPU ARCH     : x86_64
============================================================

$ vboxmanage --version
7.0.20r163906
```

### ホスト

```sh
$ ~/bin/proper7y 
proper7y v0.4.2 - A tiny Bash script to get OS and other
software version info. https://github.com/rnazmo/proper7y
============================================================
OS NAME      : Manjaro Linux
OS VERSION   : 24.0.8
Current Shell: Bash
Bash VERSION : GNU bash, バージョン 5.2.32(1)-release (x86_64-pc-linux-gnu)
Zsh VERSION  : 5.9 (x86_64-pc-linux-gnu)
CPU ARCH     : x86_64
============================================================

$ vboxmanage --version
7.0.20r163906
```

## 感想

- 疲れて途中で集中切れた
- この記事書くの面倒だったが、これで次からは (これを見ながら作業すれば良いので) 楽になる。はず
- **出来上がった仮想マシンはかなり良い感じ**
- TODO:

## 参考

- 「インストール直後にすること」全体：
    - [Manjaro Linux 最初の一歩 #インストール後に最初にしておくとよいこと。 - Qiita](https://qiita.com/phoepsilonix/items/b287aacf2de0ee89681b#%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E5%BE%8C%E3%81%AB%E6%9C%80%E5%88%9D%E3%81%AB%E3%81%97%E3%81%A6%E3%81%8A%E3%81%8F%E3%81%A8%E3%82%88%E3%81%84%E3%81%93%E3%81%A8)
    - [Manjaro Linuxでしあわせ環境を構築する](https://zenn.dev/calloc134/articles/0a9eae7c8df0d3#%E5%9F%BA%E6%9C%AC%E7%9A%84%E3%81%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB)
    - [Manjaro Linux (Xfce Desktop) インストール手順 – ロハスな生き方に憧れて！　温泉、Open Source、･･･](https://fanofdido.blog/manjaro-linux-xfce-desktop/)
    - [（備忘録）Manjaro Linux 初期設定手順 - Qiita](https://qiita.com/zono_0/items/dc09a77ca70a6d52d3a8)
    - [Manjaro Linux (Gnome Desktop) インストール手順 – ロハスな生き方に憧れて！　温泉、Open Source、･･･](https://fanofdido.blog/manjaro-linux-gnome-install/)
    - [manjaro linux インストール後にする事 - Qiita](https://qiita.com/kxkx5150/items/16b2d5ee6cdea916ef44)
    - [Manjaro Linux Xfceインストール後の基本設定 | プログラミングって大変だ](https://kotetsu1701.com/note/basic-settings-after-installing-manjarolinux-xfce/)
    - [Manjaro インストール直後にやること12選 - In my mind](https://in-my-mind.hatenablog.jp/entry/12things-to-do-after-installing-manjaro-2020-04-18)
- ミラーサーバーの変更：
    - [Manjaro Linux のアップデートが遅いのでミラーサーバーを変更した - turtlechanのブログ](https://turtlechan.hatenablog.com/entry/2019/08/25/194849)
    - [ミラー - ArchWiki](https://wiki.archlinux.jp/index.php/%E3%83%9F%E3%83%A9%E3%83%BC)
- 日本語入力の設定：
    - [朗報！ついに Manjaro Linux で 日本語入力を簡単に導入 できるようになった！！](https://gae-fan.blogspot.com/2020/06/manjaro-linux.html)
    - [朗報！ついに Manjaro Linux で 日本語入力を簡単に導入 できるようになった！！](https://gae-fan.blogspot.com/2020/06/manjaro-linux.html)
- TODO:

## 関連リンク

- TODO:

## ChangeLog

- 2027-08-05 TODO:

## TODO

- [ ] 日本語入力は fcitx から fcitx5 に乗り換えた方が良さそう
    - これは別記事 (Scrap) かな
    - Ref:
        - [Arch Linuxの日本語入力をfcitxからfcitx5に切り替える | クロの思考ノート](https://note.kurodigi.com/archlinux-fcitx5/)
        - [Fcitx - ArchWiki](https://wiki.archlinux.jp/index.php/Fcitx)
        - [Fcitx5 - ArchWiki](https://wiki.archlinux.jp/index.php/Fcitx5)
- [ ] SSD Trim?
    - via: [Manjaro Linux (Xfce Desktop) インストール手順 – ロハスな生き方に憧れて！　温泉、Open Source、･･･](https://fanofdido.blog/manjaro-linux-xfce-desktop/#ssd-trim)
- [ ] foo
