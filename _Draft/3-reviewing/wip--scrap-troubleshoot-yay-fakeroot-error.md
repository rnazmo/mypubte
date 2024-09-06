---
mymetag_version: v3.1.0
id: eebe837c-5090-4d63-b0a3-aeb3d58c5c76
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-07T05:21
created_at: 2024-09-07T05:21
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::troubleshoot", "tool::yay"]
tags:
keywords:
title: "troubleshoot］yay：エラー `ERROR: Cannot find the fakeroot binary.` が出てパッケージのインストールに失敗した"
aliases: ["troubleshoot］yay：Failed to install package with error `ERROR: Cannot find the fakeroot binary.`"]
---

## まとめ

- yay をインストールする際は正しいコマンドを使ってインストールしよう
    - x: `$ sudo pacman -S yay`
    - o: `$ sudo pacman -S --needed git base-devel yay`

## 経緯・流れ

- Cica (フォント) を aur で入れるのが楽そう
- -> yay をインストールする (`$ sudo pacman -S yay`)
- -> yay で `ttf-cica` をインストールしようとするもエラーで失敗 (`ERROR: Cannot find the fakeroot binary.`)
- -> yay を消してインストールし直す (一度`$ sudo pacman -S --needed git base-devel yay`)

## 経緯・やりたかったこと

- ある aur パッケージ (`ttf-cica`) を yay 使ってインストールしたい

## 症状

下記の通りエラーが出てパッケージのインストールに失敗する

```sh
$ yay -S ttf-cica
AUR Explicit (1): ttf-cica-5.0.3-1
:: (1/1) Downloaded PKGBUILD: ttf-cica
  1 ttf-cica                                 (Build Files Exist)
==> Packages to cleanBuild?
==> [N]one [A]ll [Ab]ort [I]nstalled [No]tInstalled or (1 2 3, 1-3, ^4)
==> n
  1 ttf-cica                                 (Build Files Exist)
==> Diffs to show?
==> [N]one [A]ll [Ab]ort [I]nstalled [No]tInstalled or (1 2 3, 1-3, ^4)
==> N
==> Making package: ttf-cica 5.0.3-1 (2024年09月07日 05時03分42秒)
==> Retrieving sources...
  -> Downloading Cica_v5.0.3.zip...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 22.3M  100 22.3M    0     0  10.6M      0  0:00:02  0:00:02 --:--:-- 12.4M
==> WARNING: Skipping verification of source file PGP signatures.
==> Validating source files with md5sums...
    Cica_v5.0.3.zip ... Passed
:: (1/1) Parsing SRCINFO: ttf-cica
==> Making package: ttf-cica 5.0.3-1 (2024年09月07日 05時03分45秒)
==> Checking runtime dependencies...
==> Checking buildtime dependencies...
==> Retrieving sources...
  -> Found Cica_v5.0.3.zip
==> Validating source files with md5sums...
    Cica_v5.0.3.zip ... Passed
==> Removing existing $srcdir/ directory...
==> Extracting sources...
  -> Extracting Cica_v5.0.3.zip with bsdtar
==> Sources are ready.
==> ERROR: Cannot find the fakeroot binary.
 -> error making: ttf-cica-exit status 15
 -> Failed to install the following packages. Manual intervention is required:
ttf-cica - exit status 15
```

## 原因

- yay をインストールする際、間違ったコマンドでインストールしてしまったため、yay の依存パッケージ (fakeroot) が不足していた
    - x: `$ sudo pacman -S yay`
    - o: `$ sudo pacman -S --needed git base-devel yay`

### 対処

- 一度 yay をアンインストールして、正しいコマンドで再度インストールし直した

```sh
# パッケージ削除
$ sudo pacman -Rs yay

# キャッシュ削除
$ sudo pacman -Scc

$ sudo reboot
```

```sh
# 正しいコマンドで再インストール
$ sudo pacman -S --needed git base-devel yay
```

その後、再び

```sh
$ yay -S ttf-cica
```

で Cica をインストールしてみたところ、無事成功した。

## 環境

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

$ yay --version
yay v12.3.5 - libalpm v14.0.0
```

## 感想

- ちゃんと公式ドキュメントに書いてある通りのコマンドでインストールしようね、という教訓

## 参考

- [yay/README.md at next #Installation · Jguer/yay](https://github.com/Jguer/yay/blob/675f0ba3f3d4bbc006a12c29e273df0f4f533edc/README.md#other-distributions)
- [Pacmanの使い方 - Qiita](https://qiita.com/MoriokaReimen/items/dbe1448ce6c0f80a6ac1)
- [WSL上のArchLinuxでyayを使う方法 #archLinux - Qiita](https://qiita.com/Hayao0819/items/1d647683bf458d10351a)
