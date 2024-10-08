---
mymetag_version:
id:
type: scrap
drafted_at: 2024-08-10T18:55
created_at:
last_updated_at:
last_reviewed_at:
categories: ["catchup", "Kali Linux"]
tags: ["series:catchup", "Kali Linux", "OS"]
keywords:
title: "［catchup］Kali Linux：v2021.1 - v2021.4 のアップデート情報に追いつく (2021-01 - 2021-12）"
aliases: ["Catch up on Kali Linux v2021.1 - v2021.4 updates (2021-01 - 2021-12）"]
---

TODO:

### v2021.1
- TODO:
- Desktop:
    - Xfce:
        - 何かしらのアップデートが合ったらしい（調整程度）
- ターミナルの調整
    - mate-terminal, terminator and tilix それらすべてでさまざまな作業が実施されました
    - デスクトップ環境のオプションでは、ターミナルに関しても選択肢があります(使用するシェルも同様)。私たちは、さまざまなターミナル(xfce4-terminal, tmux, tilix, konsole, qterminal, and mate-terminal) を「Kali化」するために取り組んできました。
- Finding Commands That Didn’t Want To Be Found
    - プログラムをインストールする必要があるかどうかを伝える手助けします
    - デフォルトで `command-not-found` が含まれるようになった。これは「オプション」パッケージであり、`kali-linux-default` をすべて削除しなくても削除できます。
    - これめちゃいいね！コマンドが見つからなかったときに、インストール方法とか typo の修正とかを提案してくれる
- ツール作成者とのパートナーシップ
    - BC SecurityとJoohoiは素晴らしいツールを制作しており、私たちは彼らをサポートしたいと考えています。
    - BC Security - maintaining team of Empire/Starkiller
    - Joohoi - The creator of “Fuzz Faster U Fool (ffuf)”
        - ffuf 良さそうかも？
    - パートナーシップを結ぶことでKaliは早期アクセス権を持っているらしい
    - ツール作成者とパートナーシップを結んでるの知らなかった
- 新しいツール
    - Airgeddon - ワイヤレスネットワークの監査
    - AltDNS - サブドメインの順列、変更、変異を生成し、解決します
    - DNSGen - 提供された入力からドメイン名の組み合わせを生成します
    - DumpsterDiver - さまざまなファイルタイプの秘密を検索
    - GitLeaks - Gitリポジトリの履歴から秘密と鍵を検索
    - WordlistRaider - 既存の単語リストの準備
- Kali’s Website
    - kali.orgがリニューアルされた
    - WordPressからHugoに移行しました。
    - aliと同様に、Webサイトもローリングディストリビューションになります。
- Wallpapers
    - ちょっとした変更ですが、壁紙パッケージを微調整しました。
    - kali-wallpapers-2020.4 - 2020.4以降のKaliの壁紙（当面の間）
    - kali-wallpapers-2019.4 - 2019.4 から 2020.3 までの Kali の壁紙。
    - kali-wallpapers-legacy - BackTrack & Kali のノスタルジックな背景
    - kali-wallpapers-all - すべての壁紙
    - kali-community-wallpapers - コミュニティによって作成され、提出されました

### v2021.2
- TODO:
- Kaboxer v1.0 のリリース
    - Kali Applications Boxer v1.0 のご紹介! コンテナ内のアプリケーション
    - Kaboxer v1.0 のご紹介(再び)
    - 見逃した方のために、Kaboxer については以前専用のブログ記事で取り上げており、私たちが Kaboxer を気に入っている理由についてさらに詳しく説明しています。さらに詳しく知りたい場合は、これについて取り上げたブログ投稿、またはこれに関するドキュメントをご覧ください。
        - RL:
            - https://www.kali.org/blog/introducing-kaboxer/
            - https://www.kali.org/docs/development/packaging-apps-with-kaboxer/
    - すでに投稿されている内容を繰り返すつもりはありませんが、このテクノロジーにより、複雑な依存関係やレガシーなプログラムとライブラリなどを含むプログラムを、正しくパッケージ化できるようになります(以前は困難でした)。
    - Kaboxer のリリースに伴い、Kaboxer を使用した 3 つのパッケージをリリースしました。
        - Firefox (開発者版) - 大きな GUI デスクトップ アプリケーション
        - Zenmap - レガシーライブラリ( Python 2 )アプリケーション
    - Kaboxer はまだ初期段階ですので、優しく忍耐強くお使いください。
- Kali-Tweaks v1.0 をリリース
    - Kali Linux を好みに合わせて簡単に設定できるようにする方法
    - これは、Kali を自分の好みに合わせて素早く、簡単に、正しい方法でカスタマイズできるようにするための、Kali ユーザーのための小さな手助けです。これにより、繰り返しの作業をやめることができます。
    - 現在、Kali-Tweaks は次のことに役立ちます:
        - メタパッケージ-インストーラーイメージを使用しなかった場合、Kali のインストール時に利用できなかった可能性のあるツールのグループをインストール/削除します。
        - ネットワークリポジトリ- 「最先端」および「実験的」ブランチの有効化/無効化
            - https://www.kali.org/docs/general-use/kali-branches/
        - シェルとプロンプト- 2行または1行のプロンプトを切り替えたり、プロンプトの前の余分な行を有効/無効にしたり、BashまたはZSHをデフォルトのシェルとして設定したりします。
            - https://www.kali.org/docs/general-use/kali-branches/
            - https://www.kali.org/blog/kali-linux-2020-3-release/
        - 仮想化- Kali をゲスト VMとして使用していますか?いくつかの操作を実行すれば、エクスペリエンスを簡単にできます。
    - > 私たちの哲学は、実行する前に何を実行しているのかを常に理解することです。そうすることで、望ましくない厄介な驚きの可能性を減らすことができます。そのため、自動化する前に手動でアクションを実行することを常に推奨しています。そうすれば、裏で何が起こっているかを理解できます。その一方で、覚えておくべきことがたくさんあることも理解しています。
    - kali-tweaksは「必須」ではなく「推奨」としてマークされています。
    - デフォルトのログインシェルを変更する場合は、変更を有効にするためにログアウトして再度ログインしてください （グラフィカルまたはリモートコンソールのいずれか）。
    - Kali-Tweaks はまだ初期段階ですので、優しく忍耐強くお使いください。
- 刷新されたBleeding-Edge ブランチ
    - Kali の Bleeding-Edge ブランチは2013 年 3 月から存在していましたが、最近バックエンドを完全に再構築しました。
    - Bleeding-Edge とは？
        - TODO:
    - https://www.kali.org/blog/bleeding-edge-kali-repositories/
- 特権ポートの無効化
    - ポート 1024/TCP-UDP 以下のリスナーを開くのにスーパーユーザー アクセスは不要になりました
    - 1024 未満の TCP および UDP ポート(つまり 0/TCP-UDP <= 1023/TCP-UDP) を使用するために特権許可を必要とするという制限を削除するためにカーネルにパッチを適用しました。
    - これは次の理由で行われました:
        - 私たちはKaliをサーバーではなくデスクトップOSとして考えています
        - TODO: etc...
- 新しいツール
    - VSCode
    - TODO:
- テーマの強化
    - コマンドライン
        - 最新の Kali プロファイルを適用した ZSH を使用している場合は、CTRL + p (同時に)を押すことで、2 行プロンプトと 1 行プロンプトを切り替えることができます。これは、現在のセッションにのみ影響します。永続的に設定する場合は、kali-tweaks を参照してください。
    - ターミナルプロンプトを2行と1行の間で素早く切り替える方法を追加し、Xfce4クイック起動+ファイルマネージャーの調整を行いました。
    - Xfc4 (<- "Xfc4" って何だ？ "Xfce" か "Xfce4" の誤記か？)
        - 左上のクイック起動トレイを次のように変更しました。
            - TODO:
    - これらのテーマの変更は、 Kali をアップグレードすると取得できない場合があります。これは、ユーザーが最初に作成されたときにテーマ設定がホーム フォルダーにコピーされるためです。Kali をアップグレードすると、オペレーティング システムがアップグレードされるため、アップグレードによって個人ファイルは変更されません(システム ファイルのみ)。そのため、これらのテーマの調整を取得するには、次のいずれかを行う必要があります。
        - Kaliを新規インストールする
        - 新しいユーザーを作成して切り替える
        - 現在のユーザーのXfceプロファイルを削除し、強制的に再起動します
- デスクトップの壁紙とログイン背景
    - 壁紙についてですが、気づいていないかもしれませんが、以前は約6 か月ごとに更新サイクルを実施していました。今後は、20xx.1 リリースごとにデフォルトを変更することを目指しています (つまり、毎年初めに行われます)。したがって、6 か月後にまた変更されますが、これが最後になります。6 か月ごとに追加の壁紙を追加することを目指していますが、デフォルトの変更は 1 年に1 回のみです。
- その他の改良点
    - Win-KeXv2.10がリリースされ、マルチスクリーンがサポートされました
    - Kali のロゴがnerd-fontsプロジェクトに含まれるようになったため、次のリリースではドラゴン でターミナルをカスタマイズできるようになります。今すぐ試してみたい場合は、これらの新しい変更を加えたパッチを適用した Fira-Code フォントを作成しました(ロゴのコードは です\uF32B)。

### v2021.3
- TODO:
- OpenSSL: デフォルトで幅広い互換性を実現 #kali-tweaks
    - Kali Linux 2021.3以降では、OpenSSLはより幅広い互換性のために構成され、Kaliが可能な限り多くのサービスと通信できるようになりました。つまり、レガシープロトコル（TLS 1.0やTLS 1.1など）と古い暗号がデフォルトで有効になっています。
    - これは、これらの古いプロトコルをまだ使用している古いシステムやサーバーと通信するKaliの能力を高めるために行われます。
    - これは汎用オペレーティングシステムには適した構成ではありませんが、Kaliにとっては理にかなっています。
    - この設定はコマンドライン ツール kali-tweaks を使用して簡単に変更できます
        - 詳細については、ドキュメントを参照してください: kali.org/docs/general-use/openssl-configuration/
- 新しい Kali-Tools サイト- Kali-Docs に続いて、Kali-Tools が完全にリフレッシュされました
    - 2019.4では、ドキュメントを更新された/docs/ページに移動しました。いよいよKali-Toolsサイトの番です!
    - これらのサイトがすべての変更から落ち着き、少し成熟したら、これらをパッケージ化して、オフラインで読めるようにする予定です。
- 仮想化: あらゆる面での改善
    - ライブイメージセッションでの VM サポートの改善- マシンから Kali VM へのコピー & ペーストとドラッグ & ドロップがデフォルトで可能
    - Kali Live イメージにいくつかの改良が加えられました
    - 仮想化環境で Live イメージを実行する人たちがよりスムーズに使用できるようにするため
    - ホストとゲスト間のコピー＆ペーストやドラッグ＆ドロップのような基本的な機能は、すぐに使えるようになりました。
- 新しいツール
    - RouterKeygenPC - デフォルトの WPA/WEP Wi-Fi キーを生成する
- Kali NetHunter Watch
    - 世界初の Kali NetHunter スマートウォッチ、TicHunter Pro
    - まだ実験段階なので、機能は USB 攻撃といくつかの基本機能に限定されています。
    - 詳細：　https://www.kali.org/docs/nethunter/installing-nethunter-on-the-ticwatch-pro/
- Desktop & Theme Updates
    - 少しだけ。

### v2021.4
- TODO:
- Samba クライアントの拡張互換性 #kali-tweaks
    - Kali Linux 2021.4から、Sambaクライアントは、使用されているプロトコルのバージョンに関係なく、ほとんど全てのSambaサーバーに接続できるように、Wide Compatibilityに設定されている。この変更により、Kaliを設定することなく、"すぐに "脆弱なSambaサーバーを発見しやすくなるはずである。
    - この設定は、コマンドラインツールkali-tweaksで簡単に変更できる。Hardening セクションでは、Sambaの通常のデフォルトに戻し、最新のバージョンのSambaプロトコルのみを使うことを許可する
    - これは 2021.3 リリースの「OpenSSL: デフォルトで幅広い互換性を実現」と同様の変更が Samba クライアントにも行われた、と考えればOK
- 楽にパッケージマネージャーミラーを構成 #kali-tweaks
    - デフォルトでは、Kali システムが更新されると、パッケージ マネージャー ( APT ) は近くのコミュニティ ミラーからパッケージをダウンロードします。しかし 2019.3 以降、Cloudflare CDNからパッケージを取得するように Kali を構成することもできることをご存知でしたか? 
        - https://www.kali.org/docs/general-use/kali-linux-sources-list-repositories/
        - https://www.kali.org/blog/kali-linux-2019-3-release/
    - 今回のリリースでは、kali-tweaks を使用して、APT がコミュニティ ミラーを使用するか、Cloudflare CDN を使用するかをすばやく構成できるようになった
    - では、コミュニティ ミラーと Cloudflare CDN のどちらがベストでしょうか? 良い答えはありません。Kali の更新に実際にかかる時間は大きく異なり、インターネット接続の速度、場所、さらにはラッシュアワー時にインターネット トラフィック ジャムが発生する場所に住んでいる場合は時間帯など、多くの要因によって異なります。要点は、Kali の更新が遅い場合は、コミュニティ ミラーから Cloudflare CDN に切り替えて (またはその逆に)、自分に最適なものを見つけることです。その際 kali-tweaks が役に立つでしょう
- Kaboxer の外観を改良
    - 見やすくなった。詳細略
- 新しいツール
    - Maryam - オープンソースインテリジェンス (OSINT) フレームワーク
    - Name-That-Hash - ハッシュの種類がわかりませんか? Name That Hash がそのハッシュの種類に名前を付けます!
    - Proxmark3 - Proxmark3とRFIDハッキングに興味があるなら
    - truffleHog - Git リポジトリを検索して、エントロピーの高い文字列と秘密を探し、コミット履歴を深く掘り下げます。
- Desktop & Theme Updates
    - Xfce
        - UI の様々な改善
        - いずれかのウィジェットについて以前の設定を希望する場合は、Ctrl + Right-Clickそのウィジェットをクリックして変更または削除できます。
        - 仮想デスクトップに関するボーナスのヒント!
            - ショートカットを使用してワークスペースを追加または削除できます: Alt + Insert/Alt + Delete
            - ショートカットを使用してワークスペース間を移動できます。
            - Ctrl + Alt + <ARROW_KEY>矢印キーの方向に移動します。
                - （追加すると、Shift現在フォーカスされているウィンドウが移動します）
            - Ctrl + Alt + <WORKSPACE_NUM>番号に基づいて特定のワークスペースに移動します。
            - Ctrl + Super + <WORKSPACE_NUM>ウィンドウをその番号に基づいて特定のワークスペースに移動します。
- Kaliテーマをアップグレードする方法
    - これらのテーマの変更は、 Kali をアップグレードすると取得できない場合があります。これは、ユーザーが最初に作成されたときにテーマ設定がホーム フォルダーにコピーされるためです。Kali をアップグレードすると、オペレーティング システムがアップグレードされるため、アップグレードによって個人ファイルは変更されません(システム ファイルのみ)。そのため、これらのテーマの調整を取得するには、次のいずれかを行う必要があります。
        - Kaliを新規インストールする
        - 新しいユーザーを作成して切り替える
        - 現在のユーザーのデスクトップ環境プロファイルを削除し、強制的に再起動します。
- Miscellaneous (その他
    - Pythonコマンド
        - pythonコマンドはもう使えない！ 代わりにpython3を使う必要があります。 あるいは、python-is-python3をインストールして、python3のエイリアスとしてpythonを復元することもできます。
