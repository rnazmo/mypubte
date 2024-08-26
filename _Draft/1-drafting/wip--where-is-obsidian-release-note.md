---
mymetag_version: v2.1.0
id: 0b871265-1e8c-4746-89f7-5a315ed7cbc1
type: Scrap
drafted_at: 2024-08-27T05:09
created_at: 2024-08-27T05:09
last_updated_at:
last_reviewed_at: TODO:
categories: ["tool::Obsidian"]
tags:
keywords: ["release-note"]
title: "Obsidian］Obsidian のリリースノートの場所"
aliases: ["catchup］Catch up on Hoge v2027.1 - v2027.2（2027-01 - 2027-07"]
---

## まとめ

- リリースノートは無い。替わりに ChangeLog がある
- [公式サイト](https://obsidian.md/changelog/) またはアプリのコマンドパレットにて `Show release notes` から見れる

## リリースノート（ChangeLog）の場所

- 2 通りで見れる
    - 公式ブログのこのページ：[Obsidian Changelog - Obsidian](https://obsidian.md/changelog/)
    - またはアプリのコマンドパレットから `Show release notes`

## リリースノートは存在せず ChangeLog のみ存在する？

- （この項は蛇足）
- Obsidian においてそもそも「リリースノート (release note)」は存在せず "ChangeLog" だけ存在する？
    - 公式サイト [https://obsidian.md](https://obsidian.md/) では、公式側による "release note" という記述が (軽く探した限りでは) 見つからない。"ChangeLog" で統一しているっぽい
- しかし例外として、 Obsidian アプリで直近の更新内容が表示されるとき、タブのタイトルは `Release Notes`
    - TODO: 画像を撮ってここに貼る？
    - 更新内容が表示されるのはたぶんアプリの更新後、最初にアプリを起動したタイミング
        - コマンドパレットから `Show release notes` でも見れる
    - その内容は公式サイトで読める ChangeLog と全く同じ
    - [この記事](https://medium.com/obsidian-observer/obsidian-quick-tip-show-release-notes-8247914b53a3) によると、過去にはフォーラムの最新アナウンスにてリリースノートを投稿していたっぽいからそれの名残か？
- よって事実上リリースノートは存在せず ChangeLog のみ存在するということだろう
    - ただしこのへんは "ChangeLog" や "Release Note" という語の解釈によりそうだが
        - "ChangeLog" = "Release Note" かも知れない？
- 重要度はかなり低いことなのでこれ以上は深追いしない

## 感想

- リリースノート（ChangeLog）を探しづらい＆見づらい
    - もうちょっと読みやすいと仕様の変化を追いやすくて嬉しいのだけれど
    - ソースコードがクローズドだから仕方ない部分はあるか
- TODO:

## 脚注

[^1]: foobarbaz

## 参考

- [Obsidian Quick Tip: Show Release Notes | by TfTHacker | Obsidian Observer | Medium](https://medium.com/obsidian-observer/obsidian-quick-tip-show-release-notes-8247914b53a3)

## 関連リンク

- [ChangeLog と Release Note の違い](./a8becb2e-7e98-44c1-9663-d2035e3893ee.md)
- [obsidianmd/obsidian-releases: Community plugins list, theme list, and releases of Obsidian.](https://github.com/obsidianmd/obsidian-releases)
- [Obsidian Roadmap - Obsidian](https://obsidian.md/roadmap/)

## TODO

- 「Obsidian アプリを開いたときに `Release Notes` というタイトルで直近更新内容が表示されることがある」←これの画像を撮って貼る
