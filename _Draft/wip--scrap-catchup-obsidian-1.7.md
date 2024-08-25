---
mymetag_version: v2.1.0
id: cee95e3d-0693-4fb5-a188-23ba2c92cd08
type: Scrap
drafted_at: 2024-08-18T20:17
created_at: 2024-08-25T20:03
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::catchup", "tool::Obsidian"]
tags:
keywords: ["RTL言語", "LTR言語"]
title: "catchup］Obsidian v1.6.2 - v1.6.7 のキャッチアップ（2024-06-07 - 2024-07-18"
aliases: ["catchup］Catch up on Obsidian v1.6 - v1.6.7（2024-06-07 - 2024-07-18"]
---

## まとめ

- 今回の範囲 (v1.6.2 - v1.6.7) において大きな変更があるのはほぼ `v1.6.2` だけ。他は読み飛ばして良い
- 主な変更点：
    - RTL 言語のサポートが大幅強化されたが、私が使うのは英語と日本語なので関係無い
    - 脚注まわりがかなり快適になった
    - 使用中の Vault 名がプライマリサイドバーに常時表示されるようになり、vault の切り替えが容易になった
    - その他、細かい仕様変更（改善）が非常にたくさんある
    - `v1.6.5 Desktop (2024-06-25)` にてアプリのインストーラーがアップデートされたため、[Obsidian のダウンロードページ](https://obsidian.md/download) から Obsidian を再インストールすること

## 目的と方針

- See: [catchup］catchup シリーズのテキストを書く目的・方針（v2024-08](./72b2608e-8b0f-4ccd-a366-9093a8d48f2a.md)
- ここでは　`public` 版の更新情報だけ追う：
    - [Obsidian アプリの public 版と catalyst 版について](TODO:記事を書いてリンクをここへ)
- v1.6 (?) は v1.6.2 として扱う：
    - リリースノートを見ていく前に注意点をメモしておく
    - ChangeLog のタイトル表記は `1.6` となっているが、ブログの URL を見る限りこれは正確には `1.6.2` ぽい
        - Ref: `[Obsidian 1.6 Desktop (Public) - Obsidian](https://obsidian.md/changelog/2024-06-07-desktop-v1.6.2/)`
        - GitHub の [Releases](https://github.com/obsidianmd/obsidian-releases/releases) を見ても `1.6` などというものはなく、[`1.6.2`](https://github.com/obsidianmd/obsidian-releases/commit/07a8ba29f771c7d266c05159a630ef3cf61bafad) しか確認できない
    - よってここでは `1.6` ではなく `1.6.2` として扱う
- TODO: 上記あたりを Refine する

## v1.6.2 Desktop (2024-06-07)

### リリース情報の入手先

- [Obsidian 1.6 Desktop (Public) - Obsidian](https://obsidian.md/changelog/2024-06-07-desktop-v1.6.2/)

### まとめ

- RTL 言語のサポートが大幅強化：
    - RTL 言語って何？
        - right-to-left (RTL) languages, 右横書き言語
        - 右から左方向、かつ上から下方向に書く文字体系のこと
        - 例：アラビア語
        - 日本語は RTL 言語？
            - 違う。LTR 言語
            - > "RTL" は「上から下、右から左 (TB-RLまたはTBRL)」言語のことも意味する場合がある。これは古代の中国語、日本語、韓国語などの言語だが、現代では一般的に「左から右」言語で書かれる。
                - source: [右横書き言語 - Wikipedia](https://ja.wikipedia.org/wiki/%E5%8F%B3%E6%A8%AA%E6%9B%B8%E3%81%8D%E8%A8%80%E8%AA%9E)
        - Ref: [右横書き言語 - Wikipedia](https://ja.wikipedia.org/wiki/%E5%8F%B3%E6%A8%AA%E6%9B%B8%E3%81%8D%E8%A8%80%E8%AA%9E)
    - 上述の通り、日本語は RTL 言語ではないのでほぼ関係無い。よって RTL 言語関係は読み飛ばす
- 脚注：
    - `[^]` を使った脚注の参照にオートコンプリートを追加
    - エディターでの脚注の解析とレンダリングが改善された
    - インライン脚注のホバープレビューが可能になった
    - 脚注 ID にカーソルを合わせると、対応する脚注のポップアップが表示されるようになった
    - まとめると全体的にかなり書きやすく＆読みやすくなった。嬉しい
- プロパティ：
    - 「プロパティ」(properties, property) って何？
        - v1.4.0 で追加された機能。いわば拡張 front matter. その詳細についてはここでは触れない
        - これを書いている時点（2024-08-26）では私はプロパティ機能のことをよく知らない
            - 調べてから別の場所 ("catchup Obsidian v1.4.0" とか？) に書くかも？
    - プロパティをマージすると、グローバルプロパティリストに新しいプロパティ名が表示されるようになった
        - グローバルプロパティリスト (global property list) がよくわからない
    - リストの項目をダブルクリックで編集できるようになった
    - 開いているファイルに無効なフロントマターがある場合、プロパティビューに編集ボタンが追加される
- Obsidian Sync:
    - 同期対象とかが色々と変わった
    - 私は Obsidian Sync を使ってないので読み飛ばす
- 検索：
    - 引用符で囲まれた文字列を入力したときは、検索サジェストが表示されなくなった
    - カーソルが検索候補の末尾にあるか、次の文字がスペースでない限り、検索サジェストが表示されなくなった
    - 「クリア」("clear") ボタンをクリックしても、検索入力のフォーカスが外れなくなった
- リーディングモード:
    - スペースを含む脚注参照は表示されなくなった
        - これよくわからない
    - インライン脚注のレンダリングを修正
- 開発者向け：
    - テーマやプラグインを [RTL インターフェイスに対応させるためのガイド](https://docs.obsidian.md/Plugins/User+interface/Right-to-left) が公開された
- テーマ：
    - Windows のデフォルトの等幅フォントが Cascadia Code から Cascadia Mono になった
    - テキストの太字は現在のテキストウェイトに基づいて計算されるようになったため、見出し内の太字は太字のまま表示されるようになった
        - CSS の `font-weight` プロパティ（フォントの太さを指定するプロパティ）まわりの話っぽい
- パフォーマンス：
    - ワークスペース（workspace）の読み込みが高速化された
    - 長い Markdown ファイルの解析が高速化された
- その他：
    - 現在使用中の Vault 名がプライマリサイドバー (左側に出てくる一番良く使うサイドバー) の下あたりに常時表示されるようになり、vault の切り替えが容易になった
        - これ良い。便利
    - 文字数と単語数が現在のテキスト選択に基づいて更新されるようになった
        - 元がどういう仕様だったのか知らないけど、テキスト選択しても特にカウントしなかったっぽい？
        - わりと便利そうな機能
        - とはいえ、日本語まわりのカウントは不安かも
    - 非常にたくさんのバグが修正された
    - 非常にたくさんの細かい仕様変更（改善）があった

## v1.6.2 Mobile (2024-06-07)

### リリース情報の入手先

- [Obsidian 1.6 Mobile (Public) - Obsidian](https://obsidian.md/changelog/2024-06-07-mobile-v1.6.2/)
- 先述の `v1.6.2 Desktop` と同様。`1.6.2` として扱う

### まとめ

- 基本は Desktop 版と同様
- サイドバーのデザインが若干変更
    - また、「フルスクリーン」ボタンを削除
- 通知の表示場所を変更
- その他いくつかの細かな変更点がある
- いくつかの細かなバグが修正された

## v1.6.3 Desktop (2024-06-08)

### リリース情報の入手先

- [Obsidian 1.6.3 Desktop (Public) - Obsidian](https://obsidian.md/changelog/2024-06-08-desktop-v1.6.3/)

### まとめ

- いくつかの細かなバグが修正された

## v1.6.3 Mobile (2024-06-08)

### リリース情報の入手先

- [Obsidian 1.6.3 モバイル (パブリック) - Obsidian](https://obsidian.md/changelog/2024-06-08-mobile-v1.6.3/)

### まとめ

- Desktop 版と同様

## v1.6.5 Desktop (2024-06-25)

### リリース情報の入手先

- [Obsidian 1.6.5 Desktop (Public) - Obsidian](https://obsidian.md/changelog/2024-06-25-desktop-v1.6.5/)

### まとめ

- 大きな変更はない
- インストーラーが Electron v30.1.2 にアップデートされた。そのためアップグレードするときは、[Obsidian のダウンロードページ](https://obsidian.md/download) からインストールし、Obsidian を再インストールすること
- いくつかの細かなバグが修正された

## v1.6.5 Mobile (2024-06-25)

### リリース情報の入手先

- [Obsidian 1.6.5 Mobile (Public) - Obsidian](https://obsidian.md/changelog/2024-06-25-mobile-v1.6.5/)

### まとめ

- 基本は Desktop 版と同様
- コンテキストメニューに若干の変更あり

## v1.6.7 Desktop (2024-07-18)

### リリース情報の入手先

- [Obsidian 1.6.7 Desktop (Public) - Obsidian](https://obsidian.md/changelog/2024-07-18-desktop-v1.6.7/)

### まとめ

- いくつかの細かなバグが修正された

## v1.6.7 Mobile (2024-07-18)

### リリース情報の入手先

- [Obsidian 1.6.7 Mobile (Public) - Obsidian](https://obsidian.md/changelog/2024-07-18-mobile-v1.6.7/)

### まとめ

- Desktop 版と同様

## 感想

- 疲れた
- Obsidian を追うのちょっと疲れるかも
    - まず更新頻度高めっぽい
    - また細かい仕様・バグ修正がめちゃ多く、読むコストが大きい
    - その割に影響の大きな変更（新機能追加や破壊的変更）が少ない
    - あとリリースノートまわりが読みづらい

## 関連リンク

- [Obsidian Changelog - Obsidian](https://obsidian.md/changelog/)
- [obsidianmd/obsidian-releases: Community plugins list, theme list, and releases of Obsidian.](https://github.com/obsidianmd/obsidian-releases)
