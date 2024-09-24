---
mymetag_version: v3.1.0
id: 637a5fb7-d26e-4c49-9e4b-8bfeb9dfc9d7
type: Discussion
status: ["visibility::public", "workflow::drafting", "open"]
drafted_at: 2024-09-24T12:14
created_at: 2024-09-24T12:14
last_updated_at:
last_reviewed_at: TODO:
categories: ["my-web-tools"]
tags:
keywords: ["技術選定", "フロントエンド"]
title: "2024-09］my-web-tools：色々と技術選定"
aliases:
---

## この記事の目的と方針

- See: [purpose-and-policy］`Discussion` タイプの目的・方針（v2024-09](ab5688e9-81ef-4e3e-902f-205f5b1900d3.md)

## 議題

### 要求

- my-web-tools で使う技術を決めたい

### 経緯

- my-web-tools を作り始めた
- なので、まずはその技術選定から

### 所感など

- フロントエンド何もわからないので、手探り状態

### 注意事項

- 一次ソースを調べれてないものが多い
    - 全部確かめていると時間が掛かり過ぎるので、今回はあまり気にしないことにした

### TODO

- [ ] foo

## ChangeLog

- 2024-09-24 Open

## 議論

### 2024-09-24 フロントエンドの全体像の把握

- まずは概観を掴む
- Ref:
    - [フロントエンドのスピードに置いていかれたので、よく聞く技術を調べて分類してみた](https://zenn.dev/raru_ex/articles/eb3aa038b38771)
        - 非常にわかりやすかった
    - [Web技術全体把握ガイド - フロントエンド ＃プログラミング - Qiita](https://qiita.com/furu_39/items/c96b16a2559fb884bdc6)

### 2024-09-24 JavaScript フレームワーク (React.js vs Vue.js)

- 候補：React.js, Vue.js
- そもそもこれらをフレームワークと言って良いのかはわからない
- フロントエンドの学習が大きな目的の一つなので、React.js, Vue.js 以外 (jQuery など) の採用は無い
- フロントエンド何もわからないので、直感で React.js にする
    - ここを決めないと何も決まらない
    - フロントエンド初心者なので、どうせ適切な技術選定は無理
    - 悩んでいる時間で手を動かすべき
    - 一応、判断材料は下記
        - 少し前ではあるがそれぞれ Hello World 程度したことがある。その際、何となくだが React.js の方がしっくりきた
        - React.js が先頭で、Vue.js がそれを追っているイメージある
        - コミュニティの大きさが React.js の方が大きそう
        - 実際の様々な Web サイトのうち、React.js で作られたものと Vue.js で作られたものを比べたとき、前者の方が印象の良い・使いやすい Web サイトであることが多い
            - これは単に「開発リソースが大きなところでは React.js の採用が多い」というだけでは？サイトの印象が良いのは React.js だからではなく、開発リソースが大きいから、かもしれない
- **結論：React.js**

### 2024-09-24 言語 (JavaScript vs TypeScript)

- 候補：
    - JavaScript or TypeScript
- TypeScript 試したい
- 静的型付け言語の方が好き
- TypeScript は必須っぽい？
- **結論：TypeScript**

### React フレームワーク (Next.js, Gatsby.js, ...)

- Ref:
    - [React プロジェクトを始める – React](https://ja.react.dev/learn/start-a-new-react-project)
        - > React だけで新しいアプリやウェブサイトを作りたい場合は、コミュニティで人気のある React フレームワークから、ひとつを選ぶことをおすすめします。フレームワークなしで React を使うことも可能ですが、ほとんどのアプリやサイトにおいては、コード分割、ルーティング、データ取得、HTML 生成といった問題に対処するための開発が必要であることが分かっています。
        - > フレームワークなしで React を使うことは可能？ React をフレームワークなしで使うことも確かに可能です。既存のページに React を追加する場合はそのようにします。しかし、新しいアプリやサイトをフルで React を使って構築する場合は、フレームワークを使用することをお勧めします。
- 学習目的だからシンプルに、薄く始めたい
- **結論：とりあえず何も無し**

### 2024-09-24 JavaScript ランタイム (開発環境)

- 候補：Node.js, Bun, Deno
- Deno や Bun も良さそうだが、新しいものばかり採用すると大変そうなので、少しでも安定感のある Node.js で
- **結論：Node.js**
    - ただし、そのうち他のも試したいかも
- Ref:
    - [Node.js, Deno, Bunの比較 - どれを使うべきか？ - uki00a](https://scrapbox.io/uki00a/Node.js,_Deno,_Bun%E3%81%AE%E6%AF%94%E8%BC%83_-_%E3%81%A9%E3%82%8C%E3%82%92%E4%BD%BF%E3%81%86%E3%81%B9%E3%81%8D%E3%81%8B%EF%BC%9F)
    - [JavaScript Runtimes (Node.js, Deno, Bun)](https://zenn.dev/mryhryki/articles/2023-09-24-javascript-runtimes)

### 2024-09-24 パッケージマネージャ

- 候補：npm, yarn, pnpm
- とりあえず npm でいい
- **結論：npm**
    - ただし、そのうち他のも試したいかも

### 2024-09-24 ビルドツール・トランスパイラ・モジュールバンドラ

- ビルドツール・トランスパイラ・モジュールバンドラの違いは？
    - トランスパイラ：
        - コードを変換するやつ
            - 例：ES6+ → ES5, TypeScript → JavaScript, ...
        - Babel, (esbuild), SWC, ...
    - モジュールバンドラ：
        - ファイルをまとめるやつ
        - webpack, Turbopack, esbuild, (Vite), Rollup
    - ビルドツール：
        - トランスパイルやバンドリングを含む、様々なプロセスを管理するやつ
        - Vite, webpack
    - 語の境界は割と曖昧らしい
        - 特にビルドツールとモジュールバンドラ
        - ビルドツールが、トランスパイルやバンドリングの機能を内包していたりする
        - そもそも「ビルド」＝「トランスパイル＋バンドリング＋その他の作業」らしい
- Vite はトランスパイルやバンドリングの機能があるっぽい
    - Vite は内部で esbuild を利用してバンドルしている
    - 開発用と本番用でビルドで方法が違い、開発用では esbuild、本番用では Rollup を使っているらしい
- create-react-app はどうなの？Vite の方がいいの？
    - create-react-app はもう非推奨らしい
    - [Create React Appは役割を終えました](https://zenn.dev/nekoya/articles/dd0f0e8a2fa35f)
        - > 長らくReactの入門キットとして使われてきたCreact React App（CRA）。2023年春に正式版になった新しいReactの公式ドキュメントでは、選択肢として紹介されていません。
        - > いずれにせよ、このPRでのコメントの流れを見れば見るほど「CRAの時代は終わったのだなぁ」との思いが強くなってきます。
        - > なお、先のPRでは「フレームワークだけでなく最初の一歩としてはシンプルなVite構成がCRAの後継として適切だろう」みたいな声も多く見られますが、結局のところ（少なくとも現時点では）Viteは一段下の扱いを受けています。
            - [React プロジェクトを始める – React](https://ja.react.dev/learn/start-a-new-react-project)
    - [create-react-appからviteへの移行](https://zenn.dev/kachuno/articles/f4a82b40c9d5e3)
        - > 私がReactを学び始めた頃はcreate-react-appでプロジェクトを作成するのがベストプラクティスだったのですが、最近はcreate-react-appはメンテナンスされていないようで徐々にアンチパターンとされているみたいです。
- **結論：Vite**
- Ref:
    - [フロントエンドのスピードに置いていかれたので、よく聞く技術を調べて分類してみた](https://zenn.dev/raru_ex/articles/eb3aa038b38771)
    - [2024年第1四半期ビルドツール探訪](https://zenn.dev/ssssota/articles/e59cf5adaf97ce)
    - [トランスパイラ／バンドラーなどについて調査](https://zenn.dev/levena_evenas/scraps/a011308ad8350b)
    - [Webpack?Create React App?No、Vite!! ~ ①コンパイル、バンドル、ビルドを理解しよう ~ ＃webpack - Qiita](https://qiita.com/yuppe-namura/items/fbe8c1af9779e7ba8f87)
    - [Viteはなぜesbuildを本番環境のバンドラとして使わないのか ＃vite - Qiita](https://qiita.com/yuppe-namura/items/771ee8a4fb153730270a)
    - [Vite ってよく聞くけど何なんですか？ あれは](https://zenn.dev/comm_vue_nuxt/articles/what-is-vite)
    - [Vite (ヴィート) で1分環境構築【React + TypeScript】](https://zenn.dev/reasemi/articles/6869cebde469aa)

### 2024-09-24 CSS (スタイリング方法) どうするか問題

- 何もわからない
- Tailwind CSS ?
- React の UI コンポーネントライブラリを使うのが良さそう？
    - React-Bootstrap が学習コスト低くて良さそう？
- Ref:
    - [ReactにおけるCSSの利用はどうしたら？自分なりに結論出してみた](https://zenn.dev/yuki_tu/articles/38c8df79522563)
    - [ReactでCSSを使いこなす：6つの方法とそのメリット👍・デメリット👎](https://zenn.dev/kazu1/articles/3f7c6b8b1d3479)
    - [ReactのCSSの選択肢を比較してみた](https://zenn.dev/irico/articles/d0b2d8160d8e63)
    - [React で CSS のあて方（モジュール・styled-jsx・styled-components・Emotion）](https://zenn.dev/aono/articles/30cf46b2ac31e8)
    - [Reactのスタイリング手法まとめ in 2023 - Qiita](https://qiita.com/MasanoriIwakura/items/157aecd290e334a8c78a#tailwind-css)
    - [【CSS】ReactにおけるCSSの利用はどうしたら？自分なりに結論出してみた - Qiita](https://qiita.com/Yuki-TU/items/93e7b4f1c759a17f19d1)
    - [Tailwind CSSはCSS設計に何をもたらすか](https://zenn.dev/junseinagao/articles/efde96dc22e1de62d649)

### 静的解析ツールLinter/Formatter

TODO:

### テスティングフレームワーク

- viteset vs jest
- viteset 良さそう
    - Ref: [Vite は使ってないけど Jest を Vitest に移行する](https://zenn.dev/sa2knight/articles/migrating_vitest_from_jest#%E3%81%AA%E3%81%9C-vitest-%E3%82%92%E9%81%B8%E3%82%93%E3%81%A0%E3%81%AE%E3%81%8B)
        - > Jest を長らく使い続けていると、職人技や歴史的経緯がプロジェクト上に現れてしまい、何か触れてはいけないもののようになってしまいます。
- Ref:
    - [Vite は使ってないけど Jest を Vitest に移行する](https://zenn.dev/sa2knight/articles/migrating_vitest_from_jest)

### その他

storybook???

[React + Storybook + MSW + Vitestで作る堅牢なフロントエンド開発術](https://zenn.dev/kenfdev/articles/755ae0f65e9dec)
