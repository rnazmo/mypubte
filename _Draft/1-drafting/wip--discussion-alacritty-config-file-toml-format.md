2024-09-07T08:17
7ed73067-19bc-4c6e-b218-2147736859a8
Alacritty の設定ファイル (`alacritty.toml`) の TOML の書き方どうするか問題

---

- TOML は、同じ構造を数通りの書き方で表現できる
- 「Alacritty のフォントを Cica に指定する設定ファイル」（`alacritty.toml`）の例で考えてみる
- 思いついた書き方が、以下の 3 通り
    - 各形式の名称は適当に名付けた。正式名称は知らない

#### 辞書形式

```toml
[font]
normal = { family = "Cica", style = "Regular" }
bold = { family = "Cica", style = "Bold" }
italic = { family = "Cica", style = "Italic" }
bold_italic = { family = "Cica", style = "Bold Italic" }
```

#### フラット形式

```toml
[font]
normal.family = "Cica"
normal.style = "Regular"
bold.family = "Cica"
bold.style = "Bold"
italic.family = "Cica"
italic.style = "Italic"
bold_italic.family = "Cica"
bold_italic.style = "Bold Italic"
```

#### ネスト形式

```toml
[font]
[font.normal]
family = "Cica"
style = "Regular"
[font.bold]
family = "Cica"
style = "Bold"
[font.italic]
family = "Cica"
style = "Italic"
[font.bold_italic]
family = "Cica"
style = "Bold Italic"
```

#### どの形式にするか

- 辞書形式：
    - ファイル編集して `git diff` したときに、差分が綺麗に表示されなそう
    - 行数・記述量は一番少ない
    - ぱっと見が見づらいからあまり好きじゃないかも
    - 公式ドキュメント内ではこの形式で説明されている
- フラット形式：
    - 少し冗長だが視認性高め？
- ネスト形式：
    - 一番行数が多い。冗長
    - 階層構造に強いというか、拡張性が高い
    - データ構造が直感的に分かりづらい
- 検討：
    - 正直どれでも良い
    - ぱっと見の視認性の高さで、フラット形式が一番好きかも
        - たぶん 100 行未満くらいの小規模なファイルならフラット形式が一番見やすいんじゃないかな
        - 逆に大規模や複雑なものだとネスト形式に分がありそう
- 結論：
    - フラット形式でいく
        - 好みでしか無いので、変えたくなったらいつでも変えて良い
