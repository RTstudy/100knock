# 調整した箇所

## ノック62
- コードが冗長すぎるように見える
    - tr_dfが隣接行列になっているので、そこからそのままグラフを作れるのではないか？
    - うまくいかなかったので、pandasデータをmeltしてtidyな形にし、source, target, weightの変数を持たせた形に変形
    - それをfrom_pandas_edgelistでグラフにするとうまくいった
    - [整然データ(Tidy Data)への変換をpandasでやってみる](https://qiita.com/ishida330/items/922caa7acb73c1540e28)
    - [pandas→networkx→pyvisでネットワーク分析＆可視化](https://qiita.com/niship2/items/9d7e2b6ab2ca1be18eaf)
    
## ノック63
- 判定用の関数がやはり冗長
    - 修正案は6章で実施済み
    
## ノック65
- これもなぜforループ（しかも二重ループ）しているのか？マージして利益と生産数を掛け算するだけではだめなのか？

## ノック68
- いきなり`logistics_network`が使われているが、引数の形式などにまったく言及されておらず
- [ortoolpy.logistics_networkの使用時に、日本語の列名を使いたくない場合の対処](https://qiita.com/miler0528/items/d9eea13fc3559a6b0c66)
    - どうも「工場」「需要地」などを変数名としてもっていることが引数の条件のよう
    - もしかして日本人が書いたライブラリなのか？