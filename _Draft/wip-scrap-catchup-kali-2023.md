---
mymetag_version:
id: c96c5c01-4297-43d5-962b-89136426361f
type: Scrap
drafted_at: 2024-08-10T18:52
created_at: 2024-08-14T01:06
last_updated_at:
last_reviewed_at:
categories: ["series::catchup::kali", "OS::Kali"]
tags: ["pip (Pip Installs Packages)", "venv (python)", "desktop-environment::Xfce", "i3 (window manager)"]
keywords: ["Kali Linux::Kali Purple", "defensive security", "SOC (Security Operations Center)", "Python", "Kali Linux::Kali Autopilot"]
title: "catchup::kali］v2023.1 - v2023.4 のキャッチアップ（2023-01 - 2023-12"
aliases: ["catchup::kali］Catch up on v2023.1 - v2023.4（2023-01 - 2023-12]
---

## まとめ

- TODO:

## 目的と方針

See: [catchup］catchup シリーズのテキストを書く目的・方針（v2024-08](./72b2608e-8b0f-4ccd-a366-9093a8d48f2a.md)

## v2023.1

### リリース情報の入手先

- [Kali Linux 2023.1 Release (Kali Purple & Python Changes) | Kali Linux Blog](https://www.kali.org/blog/kali-linux-2023-1-release/)

### まとめ

- [10 周年記念のブログ記事](https://www.kali.org/blog/10-years/) が公開された
- Kali Purple 始めました
- python の更新に伴い、pip まわりに罠があるので、モジュールインストール時には注意が必要
    - 注：これよくわからなかった
-TODO:

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

-TODO:
- Theme Refresh:
    - 年に一度のテーマ更新
- Desktop Updates:
    - Xfce
        - ファイルマネージャー Thunar に機能追加
        - インポート/エクスポート機能を備えたパネル プロファイルのサポート
            - これで、デスクトップ パネルを好みに合わせて変更し、安全な場所に保存 (または共有) できます。アプリに含まれるすべての事前構築済みレイアウトとは別に、デフォルトKali設定のプロファイルと、小型ディスプレイに適した新しいKali compactプロファイルを追加しました
        
### WSL アプリケーションリポジトリを公開

-TODO:

### tools: 新しいツール

-TODO:
- Cyber​​Chef - サイバースイスアーミーナイフ
- Kubernetes-Helm - チャートの管理
- Redeye

## v2023.2

### リリース情報の入手先

-TODO:

### まとめ

-TODO:

### desktop&theme: 2024 テーマリフレッシュ

-TODO:
- Xfce:
    - Xfce オーディオ スタックのアップデート
        - Kali のデフォルト デスクトップのオーディオ スタックが変更され、 PulseAudio がPipeWireに置き換えられました。
    - GUI での簡単なハッシュ計算
        - このリリースでは、Xfce ファイル マネージャー用の便利な拡張機能GtkHashがプリインストールされています。この拡張機能は、ファイルを右クリックして[チェックサム]タブを開くだけで、チェックサムをすばやく計算するオプションを提供します。
- i3:
    - i3 デスクトップのオーバーホール
        - i3-gaps が i3 と統合されました
        - 試したいな
- アイコンとメニューの更新

## v2023.3

### リリース情報の入手先

-TODO:

### まとめ

-TODO:

### Internal Infrastructure

- Update packaging Tools (to have a peek at some back-end development)
-TODO:

### new sub-domain, mirror-traces.kali.org

-TODO:
- https://mirror-traces.kali.org/
    - site src: https://gitlab.com/kalilinux/tools/mirror-status
    - 面白い。存在を知っておくと便利そうかも？

### Kali Autopilot

-TODO:

## v2023.4

### リリース情報の入手先

-TODO:

### まとめ

-TODO:

### Vagrant が Hyper-V をサポートするようになりました

-TODO:

## 感想

-TODO:

## 関連リンク

- [Blogs | Kali Linux Blog](https://www.kali.org/blog/)
- [Releases History | Kali Linux](https://www.kali.org/releases/)
- [Change Log - Kali Linux Bug Tracker](https://bugs.kali.org/changelog_page.php)

## TODO

- [ ] Update `mymetag_version` in the frontmatter
  - 先に mymetag の (v2.1.0 あたりの) リリースが必要。早くリリースすること
