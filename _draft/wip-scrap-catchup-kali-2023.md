---
mymetag_version:
id:
type: scrap
drafted_at: 2024-08-10T18:52
created_at:
last_updated_at:
last_reviewed_at:
categories: ["catchup", "Kali Linux"]
tags: ["series:catchup", "Kali Linux", "OS"]
keywords:
title: "［catchup］Kali Linux：v2023.1 - v2023.4 のアップデート情報に追いつく (2023-01 - 2023-12）"
aliases: ["Catch up on Kali Linux v2023.1 - v2023.4 updates (2023-01 - 2023-12）"]
---

TODO:

### v2023.1
- TODO:
- Kali Purple
    - 新しい時代の幕開け。カリは攻撃だけでなく、防御にもなり始めています
    - 長年にわたり、私たちは攻撃的なセキュリティという専門分野を完璧にしてきました。そして今、防御的なセキュリティという新しい分野に進出し始めています。
    - Kali Purple は概念実証として始まり、目標は、エンタープライズ グレードのセキュリティを誰もが利用できるようにすることです。
    - Red team と Blue team の中間で Purple なの
    - まだ実験段階っぽい。
    - 防御ツールの勉強に良さそう。防御ツールにも興味あるんだよね
    - [Kali Purple wiki](https://gitlab.com/kalilinux/kali-purple/documentation/-/wikis/home)
- Python Updates & Changes
    - Python のパッケージ マネージャー pip のコマンド周りが変わるため、そこだけ注意が必要らしい？
- 2023 Theme Refresh
    - 年に一度のテーマ更新
- Desktop Updates
    - Xfce
        - ファイルマネージャー Thunar に機能追加
        - インポート/エクスポート機能を備えたパネル プロファイルのサポート
            - これで、デスクトップ パネルを好みに合わせて変更し、安全な場所に保存 (または共有) できます。アプリに含まれるすべての事前構築済みレイアウトとは別に、デフォルトKali設定のプロファイルと、小型ディスプレイに適した新しいKali compactプロファイルを追加しました
- WSL アプリケーションリポジトリを公開
- 新しいツール
    - Cyber​​Chef - サイバースイスアーミーナイフ
    - Kubernetes-Helm - チャートの管理
    - Redeye

### v2023.2
- TODO:
- Desktop
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

### v2023.3
- TODO:
- Internal Infrastructure
    - Update packaging Tools (to have a peek at some back-end development)
- new sub-domain, mirror-traces.kali.org
    - https://mirror-traces.kali.org/
        - site src: https://gitlab.com/kalilinux/tools/mirror-status
    - 面白い。存在を知っておくと便利そうかも？
- Kali Autopilot

### v2023.4
- TODO:
- Vagrant が Hyper-V をサポートするようになりました
