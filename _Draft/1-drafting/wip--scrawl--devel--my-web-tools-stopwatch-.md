---
mymetag_version: v3.1.0
id: 7b644933-3652-4c4f-9c40-9720545dc286
type: Scrawl
status: ["visibility::public", "workflow::drafting"]
drafted_at: 2024-09-24T15:56
created_at: 2024-09-24T15:56
last_updated_at:
last_reviewed_at: TODO:
categories: ["series::devel", "project::my_web_tools"]
tags:
keywords:
title: "devel］my-web-tools：「stopwatch アプリ」の開発作業メモ（v2024-09-24"
aliases:
---

## 2024-09-24 「stopwatch アプリ」を作り始める経緯のメモ

- フロントエンド (React.js) の練習がしたい
- → my-web-tools を作っていく
- → まずは stopwatch アプリから

## 2024-09-24 作業予定リストを作ろうとしたが無理だった

- [ ] 0. 作業前の準備
    - [x] 0-1. 作業予定リスト (仮) の作成
    - [x] 0-2. 技術選定
    - [x] 0-3. 要件定義
- [ ] 1. プロジェクトのセットアップ
    - [x] 1-1. Node.js と npm をインストール
    - [x] 1-2. 新規 GitHub リポジトリの作成とローカルへのクローン
    - [x] 1-3. Vite を使用して新規 React+TypeScript プロジェクトを作成
    - [x] 1-4. `.editorconfig`, `.gitignore` ファイルなどの設定
- [ ] 2. 開発環境の構築
    - [ ] 2-1. ESLint, Prettier のインストールとセットアップ
        - [ ] 2-1-1. ESLint, Prettier, および関連パッケージのインストール
        - [ ] 2-1-2. ESLint の設定ファイル (`.eslintrc.js`) の編集
        - [ ] 2-1-3. Prettier の設定ファイル (`.prettierrc`) の編集
        - [ ] 2-1-4. `package.json` の編集
    - [ ] 2-2. Vitest のインストールとセットアップ
        - [ ] 2-2-1. Vitest, および関連パッケージのインストール
        - [ ] 2-2-2. Vitest の設定ファイル `vite.config.ts` の編集
        - [ ] 2-2-3. テストのセットアップファイル `src/test/setup.ts` の編集
        - [ ] 2-2-4. TypeScriptの設定ファイル `tsconfig.json` の編集
        - [ ] 2-2-5. `package.json` の編集
    - [ ] 2-3. React-Bootstrap のインストール
        - [ ] 2-3-1. React-Bootstrap, および関連パッケージのインストール
        - [ ] 2-3-2. `src/main.tsx` の編集
- [ ] 3. コンポーネントの設計
    - [ ] 3-1. 親コンポーネント `Stopwatch.ts` を設計
    - [ ] 3-2. 子コンポーネント `Display.ts` (時間表示部分) を設計
    - [ ] 3-3. 子コンポーネント `Controls.ts` (ボタン部分) を設計
- [ ] 4. 各コンポーネントの実装 (テスト駆動開発サイクル)
    - [ ] 4-1. Stopwatch コンポーネント
        - [ ] 4-1-1. 時間表示のテストを作成
        - [ ] 4-1-2. テストが失敗することを確認
        - [ ] 4-1-3. 最小限の実装を行い、テストをパス
        - [ ] 4-1-4. リファクタリング
    - [ ] 4-2. Display コンポーネント
        - [ ] 4-2-1. 時間表示のテストを作成
        - [ ] 4-2-2. テストが失敗することを確認
        - [ ] 4-2-3. 最小限の実装を行い、テストをパス
        - [ ] 4-2-4. リファクタリング
    - [ ] 4-3. Controls コンポーネント
        - [ ] 4-3-1. 時間表示のテストを作成
        - [ ] 4-3-2. テストが失敗することを確認
        - [ ] 4-3-3. 最小限の実装を行い、テストをパス
        - [ ] 4-3-4. リファクタリング

- ここまで作って思ったが、現時点で作業リストを作るのは無理だ
    - 全部を見通さないといけない
    - React.js 何もわからないのに、先のことを見通せるわけがない
- というわけで、途中で諦め

## 2024-09-24 技術選定をした

- my-web-tools 全体での技術選定を下記でやっているのでそれで良い
    - -> React.js, TypeScript, Vite, Vitest, React-Bootstrap, GitHub Actions, GitHub Pages
    - See: [2024-09］my-web-tools：色々と技術選定 (my-web-tools 全体の技術選定)](637a5fb7-d26e-4c49-9e4b-8bfeb9dfc9d7.md)

## 2024-09-24 要件定義をした

- とりあえず最低限で
- ストップウォッチの基本機能：
    - 表示：
        - 時間を「00:00:00」(時:分:秒) 形式で表示
    - 操作ボタン：
        - 開始ボタン：計測開始
        - 停止ボタン：計測停止
        - リセットボタン：時間を 00:00:00 に戻す

## 2024-09-24 mise で最新の Node.js をインストール＆バージョンを固定

- プロジェクトディレクトリに移動して `mise use node@22.9`
- これで最新の Node.js をインストール＆固定
    - `.mise.toml` が作成される

## 2024-09-24 Vite を使用して React + TypeScript プロジェクトを作成

```sh
# Vite でプロジェクトを作成
npm create vite@latest stopwatch-app -- --template react-ts

# プロジェクトディレクトリに移動
cd stopwatch-app

# 依存関係をインストール
npm install

npm run dev
```

Ref: [はじめに | Vite](https://ja.vitejs.dev/guide/#%E6%9C%80%E5%88%9D%E3%81%AE-vite-%E3%83%95%E3%82%9A%E3%83%AD%E3%82%B7%E3%82%99%E3%82%A7%E3%82%AF%E3%83%88%E3%82%92%E7%94%9F%E6%88%90%E3%81%99%E3%82%8B)


## 2024-09-24 VS Code 拡張機能の追加

- ESLint
- Prettier
- editorconfig

## 2024-09-24 npm がエラーを吐くので TypeScript のバージョンを下げた

```sh
$ npm run lint

> stopwatch-app@0.0.0 lint
> eslint .

=============

WARNING: You are currently running a version of TypeScript which is not officially supported by @typescript-eslint/typescript-estree.

You may find that it works just fine, or you may not.

SUPPORTED TYPESCRIPT VERSIONS: >=4.7.4 <5.6.0

YOUR TYPESCRIPT VERSION: 5.6.2

Please only submit bug reports when using the officially supported version.

=============

$ rg "\"typescript\"" ./package-lock.json
23:        "typescript": "^5.5.3",
1338:        "typescript": {
1367:        "typescript": {
1410:        "typescript": {
1453:        "typescript": {
3083:        "typescript": ">=4.2.0"
3132:        "typescript": {

# 5.5.xの最新バージョンにする
$ npm install typescript@~5.5.0

$ rg "\"typescript\"" ./package-lock.json
23:        "typescript": "~5.5.0",
1338:        "typescript": {
1367:        "typescript": {
1410:        "typescript": {
1453:        "typescript": {
3083:        "typescript": ">=4.2.0"
3132:        "typescript": {

$ npm run lint

> stopwatch-app@0.0.0 lint
> eslint .
```

## 2024-09-24 テスト環境のセットアップ (Vitest のインストールと設定)

```sh
npm install -D vitest @testing-library/react @testing-library/user-event jsdom @testing-library/jest-dom
```

- Ref:
    - [vitestを導入してみた ＃Vitest - Qiita](https://qiita.com/Qiitakumin/items/914602de042e029ba7f4)

## 2024-09-24 テスト(、テスト駆動開発) は諦める

- React.js 初見でテストも同時にやるのは無理だ
- フロントエンドのテスト難しすぎる
    - DOM が絡むともうわからない
    - React.js に最低限慣れる＆フロントエンドテストの本読むのが先かも

## TODO 色々追加

- ESLint はこの時点で既に入ってるっぽい
- 追加で入れるべき：
    - prettier
- React-Bootstrap
- ~~Vitest によるテスト~~
- ~~GitHub Actions でビルドとテストを自動チェック~~
- ~~GitHub Pages へのデプロイ~~

## TODO

## ChangeLog

- 2024-09-24 Open
