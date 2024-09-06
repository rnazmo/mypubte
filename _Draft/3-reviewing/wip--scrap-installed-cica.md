---
mymetag_version: v3.1.0
id: eea5ee28-42d6-4ab6-8495-e7660e001fdc
type: Scrap
status: ["visibility::public", "workflow::reviewing"]
drafted_at: 2024-09-07T04:39
created_at: 2024-09-07T04:39
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::installed", "font::Cica"]
tags:
keywords: ["tool::yay"]
title: "Cica：インストールした（v2024-09"
aliases: ["Cica：Installed（v2024-09"]
---

## まとめ

- `$ yay -S ttf-cica`

## 経緯

- Starship 試したい
- <- Nerds Fonts が必要
- <- Cica (Nerds Fonts が含まれている) が良さそう。試したい (今ココ)
- *yak shaving :)*


## インストール方法の選定

- 手動インストール：
    - 面倒そう
- AUR 経由：
    - 楽そうなのでこちらでいく

## 手順（やったこと）

### 1. インストール

```sh
$ yay -Ss cica
aur/ttf-cica 5.0.3-1 (+6 0.00) 
    A Japanese monospace font for programming
aur/cicada-bin 0.1.50-1 (+1 0.00) (Orphaned) 
    Write CI/CD Pipelines in TypeScript
aur/cicada-shell 0.9.38-1 (+2 0.00) 
    A bash-like Unix shell written in Rust
aur/cicada-git 2015.06.24-1 (+3 0.00) 
    programming language with the following features 1. threaded code based 2. aggressively developed 3. never provide backward compatibility [github git version]
aur/cicada 2015.06.24-1 (+1 0.00) (Out-of-date: 2023-12-05) 
    programming language with the following features 1. threaded code based 2. aggressively developed 3. never provide backward compatibility [github zip version]

$ yay -Si ttf-cica
Repository                    : aur
Name                          : ttf-cica
Version                       : 5.0.3-1
Description                   : A Japanese monospace font for programming
URL                           : https://github.com/miiton/Cica
Licenses                      : custom
Groups                        : None
Provides                      : None
Depends On                    : None
Optional Deps                 : None
Make Deps                     : None
Check Deps                    : None
Conflicts With                : None
Replaces                      : None
AUR URL                       : https://aur.archlinux.org/packages/ttf-cica
First Submitted               : Fri 21 Oct 2016 03:08:59 AM JST
Keywords                      : None
Last Modified                 : Tue 29 Mar 2022 11:47:38 AM JST
Maintainer                    : azon
Popularity                    : 0.000003
Votes                         : 6
Out-of-date                   : No

$ yay -S ttf-cica
AUR Explicit (1): ttf-cica-5.0.3-1
:: PKGBUILD up to date, skipping download: ttf-cica
  1 ttf-cica                                 (Installed) (Build Files Exist)
==> Packages to cleanBuild?
==> [N]one [A]ll [Ab]ort [I]nstalled [No]tInstalled or (1 2 3, 1-3, ^4)
==> A
:: Deleting (1/1): /home/toor/.cache/yay/ttf-cica
HEAD is now at 713734f Updated to 5.0.3
Removing Cica_v5.0.3.zip
Removing ttf-cica-5.0.3-1-any.pkg.tar.zst
  1 ttf-cica                                 (Installed) (Build Files Exist)
==> Diffs to show?
==> [N]one [A]ll [Ab]ort [I]nstalled [No]tInstalled or (1 2 3, 1-3, ^4)
==> N
==> Making package: ttf-cica 5.0.3-1 (2024年09月07日 05時54分50秒)
==> Retrieving sources...
  -> Downloading Cica_v5.0.3.zip...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 22.3M  100 22.3M    0     0  13.1M      0  0:00:01  0:00:01 --:--:-- 30.0M
==> WARNING: Skipping verification of source file PGP signatures.
==> Validating source files with md5sums...
    Cica_v5.0.3.zip ... Passed
:: (1/1) Parsing SRCINFO: ttf-cica
==> Making package: ttf-cica 5.0.3-1 (2024年09月07日 05時54分52秒)
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
==> Making package: ttf-cica 5.0.3-1 (2024年09月07日 05時54分54秒)
==> Checking runtime dependencies...
==> Checking buildtime dependencies...
==> WARNING: Using existing $srcdir/ tree
==> Entering fakeroot environment...
==> Starting package()...
==> Tidying install...
  -> Removing libtool files...
  -> Purging unwanted files...
  -> Removing static library files...
  -> Stripping unneeded symbols from binaries and libraries...
  -> Compressing man and info pages...
==> Checking for packaging issues...
==> Creating package "ttf-cica"...
  -> Generating .PKGINFO file...
  -> Generating .BUILDINFO file...
  -> Generating .MTREE file...
  -> Compressing package...
==> Leaving fakeroot environment.
==> Finished making: ttf-cica 5.0.3-1 (2024年09月07日 05時55分12秒)
==> Cleaning up...
[sudo] password for toor:
loading packages...
warning: ttf-cica-5.0.3-1 is up to date -- reinstalling
resolving dependencies...
looking for conflicting packages...

Packages (1) ttf-cica-5.0.3-1

Total Installed Size:  44.61 MiB
Net Upgrade Size:       0.00 MiB

:: Proceed with installation? [Y/n] Y
(1/1) checking keys in keyring                                  [###################################] 100%
(1/1) checking package integrity                                [###################################] 100%
(1/1) loading package files                                     [###################################] 100%
(1/1) checking for file conflicts                               [###################################] 100%
(1/1) checking available disk space                             [###################################] 100%
:: Processing package changes...
(1/1) reinstalling ttf-cica                                     [###################################] 100%
:: Running post-transaction hooks...
(1/3) Arming ConditionNeedsUpdate...
(2/3) Updating fontconfig cache...
(3/3) Updating X fontdir indices...
```

### 2. インストールできたことを確認する

```sh
$ fc-list | grep -i cica
/usr/share/fonts/TTF/Cica-RegularItalic.ttf: Cica:style=Italic
/usr/share/fonts/TTF/Cica-BoldItalic.ttf: Cica:style=Bold Italic
/usr/share/fonts/TTF/Cica-Bold.ttf: Cica:style=Bold
/usr/share/fonts/TTF/Cica-Regular.ttf: Cica:style=Regular
```

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

```sh
$ yay -Si ttf-cica
Repository                    : aur
Name                          : ttf-cica
Version                       : 5.0.3-1
Description                   : A Japanese monospace font for programming
URL                           : https://github.com/miiton/Cica
Licenses                      : custom
Groups                        : None
Provides                      : None
Depends On                    : None
Optional Deps                 : None
Make Deps                     : None
Check Deps                    : None
Conflicts With                : None
Replaces                      : None
AUR URL                       : https://aur.archlinux.org/packages/ttf-cica
First Submitted               : Fri 21 Oct 2016 03:08:59 AM JST
Keywords                      : None
Last Modified                 : Tue 29 Mar 2022 11:47:38 AM JST
Maintainer                    : azon
Popularity                    : 0.000003
Votes                         : 6
Out-of-date                   : No
```

## 参考

- [AUR (en) - ttf-cica](https://aur.archlinux.org/packages/ttf-cica)
- [Arch Linux 快適デスクトップ環境の構築 2019 - Qiita](https://qiita.com/xorphitus/items/d543931ecd2c441e462f#%E6%97%A5%E6%9C%AC%E8%AA%9E%E3%83%95%E3%82%A9%E3%83%B3%E3%83%88%E3%81%AE%E5%B0%8E%E5%85%A5)

## 関連リンク

- [日本語対応の等幅フォントを集めてみた（コーディング・コンソール向け） #Cica - Qiita](https://qiita.com/udoP_/items/286dc6c8ea6ff7845b28#cica)
- [miiton/Cica: プログラミング用日本語等幅フォント Cica(シカ)](https://github.com/miiton/Cica)
