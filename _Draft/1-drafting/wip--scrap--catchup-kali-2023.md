---
mymetag_version:
id: c96c5c01-4297-43d5-962b-89136426361f
type: Scrap
drafted_at: 2024-08-10T18:52
created_at: 2024-08-14T01:06
last_updated_at:
last_reviewed_at:
categories: ["series::catchup", "OS::Kali"]
tags: ["pip (Pip Installs Packages)", "venv (python)", "desktop-environment::Xfce", "i3 (window manager)", "NVIDIA", "tool::Cyber​​Chef"]
keywords: ["Kali Linux::Kali Purple", "defensive security", "SOC (Security Operations Center)", "Python", "Kali Linux::Kali Autopilot", "Thunar (file manager)", "kernel", "kali-tweaks", "PulseAudio", "PipeWire", "tools::Trivy"]
title: "catchup::kali］v2023.1 - v2023.4 のキャッチアップ（2023-01 - 2023-12"
aliases: ["catchup::kali］Catch up on v2023.1 - v2023.4（2023-01 - 2023-12]
---

## まとめ

- TODO:

## 目的と方針

See: [purpose-and-policy］`catchup` シリーズの目的・方針（v2024-08](./72b2608e-8b0f-4ccd-a366-9093a8d48f2a.md)

## v2023.1

### リリース情報の入手先

- [Kali Linux 2023.1 Release (Kali Purple & Python Changes) | Kali Linux Blog](https://www.kali.org/blog/kali-linux-2023-1-release/)

### まとめ

- [10 周年記念のブログ記事](https://www.kali.org/blog/10-years/) が公開された
- Kali Purple 始めました
- python の更新に伴い、pip まわりに罠があるので、モジュールインストール時には注意が必要
    - 注：これよくわからなかった
- いくつか気になるツールがある
    - Cyber​​Chef など
- カーネルのデフォルト設定の一部について
    - 1024 以下のポートを使用するのに root 権限が不要になった
    - `dmesg` を実行するのに root 権限が不要になった
    - これらの設定は `kali-tweaks` から簡単に変更できる

### website: Kali の 10 周年記念の記事が公開

- Kali の 10 周年記念のブログ記事が公開された
    - RL: [Happy 10th anniversary & Kali's story ...so far | Kali Linux Blog](https://www.kali.org/blog/10-years/)
        - Kali の歴史とか名前の由来とかこれからの話とか色々書いてあって面白い

### Kali Purple

- Kali は攻撃的なセキュリティ（offensive security）だけでなく、防衛的なセキュリティ（defensive security）という新しい分野に進出し始めた
    - 10 年前に Kali Linux が始まって、今では攻撃的なセキュリティ（offensive security）は広く普及した。これを防衛的なセキュリティ（defensive security）でも実現したい
- Purple?
    - "Red team" も "Blue team" もこれを使えばOK!を目指すから
- まだ実験段階！
- 主な用途：
    - 学習
    - SOC 分析と脅威ハンティングの実践
    - セキュリティ・コントロールの設計とテスト
    - ブルー/レッド/パープルのチーム編成演習
    - カリのスパイ対スパイの対戦（素手のブルー対レッド）
    - 小規模から中規模の環境の保護
- [Home · Wiki · Kali Linux / kali-purple / Documentation · GitLab](https://gitlab.com/kalilinux/kali-purple/documentation/-/wikis/home)
- 防御ツールの勉強に良さそう？防御系ツール全然知らないから興味ある

### Python の更新と PIP の動作

- まとめ：
    - pip まわりに罠があるので、モジュールインストール時には注意が必要
- Python 3.11 が Debian に導入された。よって Python が更新された
- 問題は pip の動作で、「python モジュールをインストールする際のコマンドを誤ると（それらが衝突して） `apt` (Advanced Package Tool) が壊れる可能性がある」らしい
- pip (python) をまともに使ったことがないせいか、この項の内容がよくわからなかった
- とりあえず pip まわりに罠があり、モジュールインストール時に注意が必要なことだけはわかった

### desktop&theme: 2023 テーマリフレッシュ

- テーマの更新:
    - 年に一度のテーマ更新
    - 10周年ということで、過去の象徴的なリリースを参照したものになっている
    - 追加バージョンを含めた壁紙はパッケージ `kali-wallpapers-legacy` から入手できる
        - [kali-wallpapers | Kali Linux Tools](https://www.kali.org/tools/kali-wallpapers/#kali-wallpapers-legacy)
        - [Kali Linux / Packages / kali-wallpapers · GitLab](https://gitlab.com/kalilinux/packages/kali-wallpapers)
- デスクトップの更新:
    - Xfce:
        - ファイルマネージャー Thunar に機能追加（分割ビューなど）
        - インポート/エクスポート機能を備えたパネル プロファイルのサポート
            - デスクトップ パネルを好みに変更し、保存 (または共有) が可能に。アプリに含まれているすべてのビルド済みレイアウトとは別に、次の 2 つのプロファイルが追加されている。デフォルトの設定用プロファイル `Kali` と、小型ディスプレイ用の `Kali compact` プロファイル

### カーネルのデフォルト設定の一部を更新

- カーネルのデフォルト設定の一部を更新された
    - 使いやすさ向上のためのちょっとした変更
- 変更内容：
    - 特権ポートの廃止：1024 以下のポートを使用するプログラムを実行するのに root 権限が不要になった
        - この変更は [Kali 2021.2](https://www.kali.org/blog/kali-linux-2021-2-release/#disabled-privileged-ports) で行われていて、今回はそれの再掲
    - `dmesg` に対する制限の廃止：`dmesg` を実行するのに root 権限が不要になった
- これらの設定は `kali-tweaks` から簡単に変更できる
- カーネルの変更点についての詳細は次リンクを参照:
    - [Kernel Configuration | Kali Linux Documentation](https://www.kali.org/docs/general-use/kernel-configuration/#dmesg-unrestricted-sysctl)
    - [Kali Linux 2021.2 Release #Disabled Privileged Ports | Kali Linux Blog](https://www.kali.org/blog/kali-linux-2021-2-release/#disabled-privileged-ports)

### Nvidia に関するトラブル

- Nvidia ドライバーの 525 シリーズは、一部の GPU モデルで動作しないことが知られている
- どのモデルが該当するか正確なところは不明だが、基本的にすべての Linux ディストリビューションからさまざまな報告がある
    - 当然 Kali Linux も含まれる
- 症状：
    - システムが遅くなったり、応答しなくなったり、完全にフリーズしたりする
- 対処：
    - Nvidia ドライバーをアンインストールして再起動する
        - `sudo apt purge "*nvidia*" && sudo reboot -f`
            - ターミナルが開けない場合はリカバリ モードとかを使う

### WSL アプリケーションのリポジトリを公開

- Link: [Kali Linux / Build-Scripts / kali-wsl-app · GitLab](https://gitlab.com/kalilinux/build-scripts/kali-wsl-app)
    - 公開されたらしいので一応メモっておくが、特に読む機会はなさそう

### tools: 新しいツール

- Arkime - 大規模、オープンソース、インデックス付きパケットキャプチャおよび検索ツール
- Cyber​​Chef - サイバースイスアーミーナイフ
    - 逆に今まで入っていなかったのか
        - まあ基本は Web 版で十分と言えば十分かも
- Kubernetes-Helm - チャートの管理
- Redeye - 最も効率的かつ整理された方法で、ペンテスト・オペレーション中のデータを管理できる

## v2023.2

### リリース情報の入手先

- [Kali Linux 2023.2 Release (Hyper-V & PipeWire) | Kali Linux Blog](https://www.kali.org/blog/kali-linux-2023-2-release/)

### まとめ

- デスクトップまわりの更新：
    - Xfce:
        - オーディオスタックが PulseAudio から PipeWire に変更された
            - ユーザー視点では特に変更なし
        - ファイル マネージャー（Thunar）に拡張機能 GtkHash がプリインストールされた
            - GUI で簡単にハッシュ計算できるように
                - ファイルを右クリックして "Checksums" タブを開くだけ！
    - i3:
        - オーバーホール（i3-gaps が i3 と統合された）
- いくつか気になるツールがある
    - Trivy など

### desktop&theme: 2024 テーマリフレッシュ

- Xfce:
    - Xfce オーディオ スタックのアップデート：
        - Kali のデフォルトのデスクトップオーディオスタックが変更され、PulseAudio が PipeWire に置き換えられた
            - PipeWire は「Linux 上でオーディオ、ビデオ ストリーム、ハードウェアを処理するためのサーバー」
            - 現在ほぼすべての Linux ディストリビューションで事実上のサウンド サーバーとなり、PulseAudio に取って代わろうとしている
            - ユーザー視点では特に変更なし
            - Related: [No sound on Kali 2023.2 | Kali Linux Documentation](https://www.kali.org/docs/troubleshooting/no-sound/)
    - GUI での簡単なハッシュ計算：
        - Xfce ファイル マネージャー用の便利な拡張機能 GtkHash がプリインストールされる。この拡張機能は、「ファイルを右クリックして "Checksums" タブを開くだけで、チェックサムをすばやく計算する」機能を提供する
        - 便利そう
- i3:
    - i3 デスクトップのオーバーホール
        - i3-gaps が i3 と統合された
        - ずっと i3 試したいと思いつつ試せてない
- アイコンとメニューの更新

### tools: 新しいツール

- GoPhish - オープンソースのフィッシングツールキット
- Terraform - 安全かつ予測可能なインフラストラクチャの作成、変更、改善
- Trivy - コンテナ、Kubernetes、コードリポジトリ、クラウドなどの脆弱性、構成ミス、シークレット、SBOM を見つける

### website: Kali Documentation のアップデート

- いくつかのページが更新：
  - デュアルブートの修正 ([Fixing Dual Boot](https://www.kali.org/docs/troubleshooting/dual-boot/))
  - APT まわりのよくある問題への対処 ([Handling common APT problems](https://www.kali.org/docs/troubleshooting/handling-common-apt-errors/))

## v2023.3

### リリース情報の入手先

- [Kali Linux 2023.3 Release (Internal Infrastructure & Kali Autopilot) | Kali Linux Blog](https://www.kali.org/blog/kali-linux-2023-3-release/)

### まとめ

- TODO:

### Internal Infrastructure

- Update packaging Tools (to have a peek at some back-end development)
- TODO:

### new sub-domain, mirror-traces.kali.org

- TODO:
- https://mirror-traces.kali.org/
    - site src: https://gitlab.com/kalilinux/tools/mirror-status
    - 面白い。存在を知っておくと便利そうかも？

### Kali Autopilot

- TODO:

## v2023.4

### リリース情報の入手先

- TODO:

### まとめ

- TODO:

### Vagrant が Hyper-V をサポートするようになりました

- TODO:

## 感想

- TODO:

## 関連リンク

- [Blogs | Kali Linux Blog](https://www.kali.org/blog/)
- [Releases History | Kali Linux](https://www.kali.org/releases/)
- [Change Log - Kali Linux Bug Tracker](https://bugs.kali.org/changelog_page.php)

## TODO

- [ ] Update `mymetag_version` in the frontmatter
  - 先に mymetag の (v2.1.0 あたりの) リリースが必要。早くリリースすること
