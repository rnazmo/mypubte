---
mymetag_version: v3.1.0
id: 114a4d98-d930-451d-82f3-c92990b6cd35
type: Scrap
status: ["visibility::public", "workflow::production"]
drafted_at: 2024-09-09T00:03
created_at: 2024-09-09T00:03
last_updated_at:
last_reviewed_at: TODO:
categories: ["tool::Git", "GitHub"]
tags: ["branch (Git)"]
keywords: ["rename", "GUI"]
title: "Git：GitHub 上でリモートブランチをリネームした（v2024-09"
aliases: ["Git：Renamed remote branch on GitHub（v2024-09"]
---

## まとめ

- ブラウザから GitHub 上で簡単にリネームできる
- 手順：
  1. 左上のブランチのドロップダウンメニューから`View all branches` を選択し、`Branches` ページへ飛ぶ
  2. 該当ブランチの右端にある…ドロップダウンメニューから `Rename branch` を選択する
  3. 変更用のウィンドウで新しい名前を入力する

## やりたかったこと

- GitHub 上でブランチをリネームしたい

## 手順（やったこと）

1. リポジトリのメインページの左上にあるブランチのドロップダウンメニューから `View all branches` を選択し、`Branches` ページへ飛ぶ
  ![ブランチのドロップダウンメニュー](./media/ce8ca7ca-6e18-4f5e-8e3d-7dd8759a3138.png)
2. 該当ブランチの右端にある…ドロップダウンメニューから `Rename branch` を選択
  ![…ドロップダウンメニュー](./media/e3a97db5-2251-4c4a-a47b-505dee550095.png)
3. 変更用のウィンドウが表示されるので、新しい名前を入力すればOK
  ![リネーム用ウィンドウ](./media/8d4aec30-e885-42f1-8846-12b21e4e36b4.png)

## 感想

- GUI でポチポチするだけでできる
- GitHub 上でできて楽

## 参考

- [ブランチの名前を変更する - GitHub Docs](https://docs.github.com/ja/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/renaming-a-branch)
