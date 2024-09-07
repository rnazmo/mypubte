2024-09-07T10:21
---

Customize

- 設定弄ってみる
- 設定ファイルの場所は `~/.config/starship.toml`
- とりま設定ファイル作る
    - `$ mkdir -p ~/.config && touch ~/.config/starship.toml`
- なんかとりあえず、公式で用意されてる（？］プリセットを導入するのが良さそう
- 利用可能なプリセットの一覧を確認：
    - `$ starship preset --list`
- pastel-powerline ってやつがぱっと見で良さそうなので試す
    - `$ starship preset pastel-powerline -o ~/.config/starship.toml`
- おお、すぐに反映された
    - なんかめっちゃおしゃれ
    - 視認性は微妙
        - 配色のせいで文字が見づらい
- 別の試す
- gruvbox-rainbow ってやつ試す
    - `$ starship preset gruvbox-rainbow -o ~/.config/starship.toml`
    - pastel-powerline の色違い版ぽい
    - 良い
        - 「配色のせいで文字が見づらい」が解消されてる
        - 彩度が低い色が好きなので、これ好きかも
- とりあえずしばらくは gruvbox-rainbow を採用する方針でいく
    - 時刻表示だけ邪魔だけど、まあいいか
- コマンド一つでお手軽にプリセット試せるの、良いね Starship。反映も一瞬だし
- ファイル全体
    - TODO:
