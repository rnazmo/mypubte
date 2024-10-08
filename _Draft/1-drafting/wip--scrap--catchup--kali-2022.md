---
mymetag_version:
id:
type: scrap
drafted_at: 2024-08-10T18:48
created_at:
last_updated_at:
last_reviewed_at:
categories: ["catchup", "Kali Linux"]
tags: ["series:catchup", "Kali Linux", "OS"]
keywords:
title: "［catchup］Kali Linux：v2022.1 - v2022.4 のアップデート情報に追いつく (2022-01 - 2022-12）"
aliases: ["Catch up on Kali Linux v2022.1 - v2022.4 updates (2022-01 - 2022-12）"]
---

TODO:

### v2022.1
- TODO:
- ビジュアルリフレッシュ: テーマの更新
    - Kali 2021.2で約束したとおり、このリリース (2022.1) 以降、毎年の 20xx.1 バージョンのみが主要なビジュアル更新を含むリリースとなります。
    - この更新には、最近更新した場合に表示されている可能性のある更新されたインストーラー テーマに加えて、デスクトップ、ログイン、およびブート ディスプレイ用の新しい壁紙が含まれています。
    - さらに、ISO イメージのブート メニューの機能、テーマ、レイアウトも改善されました。これらの変更により、全体的に一貫性が保たれています。以前は、UEFI とBIOSのブート メニューのメニューには異なるオプション、デザインがあり、記述も異なっていたため、混乱を招いていました。さらに、「インストーラー」、「ライブ」、「ネットインストール」、および「ミニ」オプション間にも複数の違いがありました。これらの問題はすべて解決され、今ではすべてに普遍的な感覚が備わっているのです。
- シェルプロンプトの変更- コードをコピーする際の読みやすさを向上させる視覚的な改善
    - 皆様の声に耳を傾けました。2020.4 の最後のプロンプト更新以降、皆様の作業が楽になることを願って、いくつかの調整を加えました。この問題の例として、専門的なペネトレーションテスト レポートの作成時や、コードのデバッグでの共同作業、ターミナルの共有時に、右側のプロンプト (終了コードとバックグラウンド プロセスの数が表示されていた)が邪魔になることがあります。そのため、右側のプロンプトはデフォルトのシェルであるZSH から削除されました。これに伴い、ルート プロンプトのドクロがシンプルなシンボルに置き換えられました
- ブラウザのランディングページを一新- FirefoxとChromiumのホームページがリニューアルされ、Kaliに必要なすべての情報にアクセスしやすくなりました。
    - Kali に同梱されているデフォルトのランディング ページの外観が新しくなりました。更新されたドキュメント サイト( Kali-DocsおよびKali-Tools )を使用すると、検索機能によって、Kali Linux の使用に必要なほぼすべてのものを検索できます。
- Kali Everything Image - オールインワンのソリューションがダウンロード可能になりました
    - 新しいフレーバーである「kali-linux-everything」イメージが採用されます。これにより、 Kali のすべてのツールを事前にインストールする必要があるユーザー向けに、完全なオフライン スタンドアロン イメージ(ISO)が可能になります。以前とは異なり、Kali のセットアップ中にネットワーク ミラー経由で「kali-linux-everything」パッケージをダウンロードする必要はありません。
    - ただし、このため、最初にダウンロードするイメージのサイズは大幅に大きくなります。サイズの増加 (約 2.8 GB から約 9.4 GB) により、これらのイメージは当初、トラフィックを処理するように設計されたテクノロジである BitTorrent を使用してのみ提供されます。
- Kali-Tweaks: レガシー SSH を簡単に- 従来の SSH プロトコルと暗号を使用して古い SSH サーバーに接続する
    - Kali の SSH クライアントを幅広い互換性に設定できるようになりました。つまり、古いアルゴリズムと暗号が有効になります。そのおかげで、それらを使用する古いサーバーへの接続が簡単になり、コマンドラインで追加のオプションを明示的に渡す必要がなくなりました。
    - この設定の目的は、脆弱な SSH サーバーをより簡単に発見できるようにすることです。前述のように、これにより、潜在的な攻撃対象領域がさらに広がります(これが起こった理由です。最近の侵入テストにより、無停電電源装置がネットワークを完全に乗っ取るための足がかりとなりました)。
    - OpenSSLやSambaとは異なり、この弱体化された動作はデフォルトでは有効になっていません。SSHは非常に機密性の高いコンポーネントであるため、デフォルトでセキュアにしておくことが望ましいからです。したがって、この設定に関心がある場合は、 を実行しkali-tweaks、Hardeningセクションに入ってそこで有効にする必要があります。
- アクセシビリティ機能- 音声合成が Kali インストーラーに戻ってきました
    - 視覚障害のあるユーザーを支援するために、音声合成が Kali セットアップに戻ってきました
- 新しいツール- ProjectDiscovery からのさまざまな新しいツールが追加されました。
    - dnsx - 高速で多目的な DNS ツールキットで複数の DNS クエリを実行できます
    - email2phonenumber - メールアドレスだけでターゲットの電話番号を取得できるOSINTツール
    - naabu - 信頼性とシンプルさを重視した高速ポートスキャナ
    - nuclei- テンプレートに基づいたターゲットスキャン
    - proxify - 外出先で HTTP/HTTPS トラフィックをキャプチャ、操作、再生するためのスイスアーミーナイフプロキシツール

### v2022.2
- TODO:
- Desktop:
    - Xfce:
        - たくさんの調整！
        - マルチモニター設定のデフォルトの壁紙を設定する
    - VirtualBox 共有フォルダーのサポート強化
        - VirtualBox を使用している場合、ユーザー アカウントが作成されると、デフォルトでグループに自動的に追加されるようになりました。つまり、VirtualBox を使用している場合、共有フォルダーを使用するための手順が 1 つ減りました
- ターミナルの調整
    - Enhanced Zsh syntax-highlighting, inclusion of Python3-pip and Python3-virtualenv by default
- Hollywood mode
    - エイプリルフールの素晴らしいスクリーンセーバー
    - `$ sudo apt -y install kali-screensaver`
    - ターミナルからすぐに起動できるように hollywood-activate コマンドをインストールして、スクリーンセーバーが起動するのを待たずに済むようにすることもできます。
- Kali Unkaputtbar - Kali の BTRFS スナップショット サポート
    - 昨年 3 月に、Kali Linux でBTRFS スナップショットの公式サポートを導入しました。これをKali Unkaputtbarと呼んでいます。 
    - Unkaputtbar は、仮想マシン (VM) のスナップショット機能をベアメタルに導入し、いくつかの強化を施します。
    - 重要な顧客レポートを削除した後や、役員会議に向かう直前に壊れたドライバー (Nvidia など) をインストールした後、時間を遡りたいと思ったことはありませんか? では、読み進めてください。今ならそれが可能です!
- Win-KeX 3.1 - GUI アプリの sudo サポート
    - このアップデートにより、GUIアプリケーションをrootとして実行することを妨げる制限がなくなりました。これで、sudoを使用して任意のGUIアプリケーションを起動できます。
- 新しいツール
    - Hakrawler
    - Sparrow-wifi
    - wifipumpkin3
- Kali ドキュメントの更新
    - RDP で Xfce にアクセスする

### v2022.3
- TODO:
- Kali is on Discord
- テストラボ環境- ツールを学習、練習、ベンチマークし、その結果を比較するためのテストベッドをすばやく作成します
    - 私たちは、テスト ラボの構築を少しでも簡単にしようとしています。そのため、次のものをパッケージ化しました。
        - DVWA - 非常に脆弱な Web アプリケーション
        - ジュースショップ- OWASP ジュースショップ
    - このリストは、今後の Kali リリースで増えていきます。
- 仮想マシン向け Kali
    - 私たちは当初からVMwareとVirtualBox用の Kali Linux イメージを提供してきました。今回のリリースでは、注目に値する変更点がいくつかあります。
    - 現在、VirtualBox イメージは VDI ディスクと.vboxメタデータ ファイルとして配布されています。簡単に言うと、VirtualBox イメージのネイティブ フォーマットです。これらのイメージは、以前提供していた OVA イメージに比べて圧縮率が高いため、ダウンロードが少し速くなります。また、使い方も少し簡単になり、VirtualBox フォルダーにイメージを解凍して実行するだけです。
    - さらに、 VM イメージの週次ビルドの提供を開始しました。これらのイメージはkali-rolling ブランチからビルドされるため、最新のパッケージが含まれていますが、四半期ごとのリリースほどテストは行われません。
    - 最後になりましたが、これらのイメージを構築するために使用するスクリプトがGitLab で利用できるようになりました。カスタム Kali VM イメージを構築する必要がある場合は、ここが最適です。
- Kali ドキュメントの更新
    - 色々面白そうなのあった
- Kali ツール リポジトリの開設- Kali ツール リポジトリを開設し、皆様からの提出を受け付けています。
    - Kali-docs は、オペレーティング システムとしての Kali に関するドキュメントです。Kali-tools は、Kali 内部のツールに関するドキュメントです。また、kali-tools リポジトリも公開し、コミュニティからの貢献も可能にしました。
    - 定期的に更新していきます。しかし、皆さんの協力があれば、更新が早くなります。私たちの目標は、すべてのツールに関する一般的な情報、使用されているツールの例、ツールの使用方法を提供することです。Kali Linux に参加したい場合、これは素晴らしい方法です。
    - 私たちは、テキスト、画像、ビデオなど、あらゆるメディア形式を求めています(ビデオの場合、Vimeo/YouTube よりもasciinema が推奨されます)。

### v2022.4
- TODO:
- Press Pack
    - ここでは、使用できるすべての製品メディア リソースを見つけることができます。これにはロゴマーク（弊社ドラゴンロゴ）などが含まれます。
- Recent Kali Blog Posts
    - Kali Community Themes
