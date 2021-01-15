# 8章メモ

## ノック71

* nx.from_numpy_arrayを使うと、NumPy arrayの隣接行列からグラフが一発で作れる。  
https://networkx.org/documentation/stable//reference/generated/networkx.convert_matrix.from_numpy_array.html

## ノック72

* simulate_percolationでやっていることが分かりづらいので書き換えた。
* p.190の「これにより、t=0, 10, 99を表示します。」はt=0, 11, 35の誤り？

## ノック74

* ノック72同様に、simulate_populationを書き換えた。
* df_linksは書き換えないので、simulate_populationの引数のdf_linksはおそらく不要。
    - Pythonの変数スコープはよくわからない。雰囲気で使っている・・・。

## ノック75

* 「相図」って初めて聞いた。
    - [これ](https://ja.wikipedia.org/wiki/%E7%9B%B8%E5%9B%B3)のことか。大学受験の時、化学（水の三態）でやって以来。
* 1つ目のセルで何をやっているかが分かりづらかった。
    - ノック74で定義したNUMを使いまわして`list_active = np.zeros(NUM)`で`list_active`を作成している。
    - 読み進めたら理解できた。

## ノック77

* 何を可視化しているか：各会員が持っているリンク数の分布

## ノック78

* ノック77まで読んだところで、「シミュレーションできたのはいいけど、こんなの結局は伝播/消滅の確率次第で結果がいかようにも変わってしまうじゃん」と思っていたが、過去の実績からこれらの値を推定できるのか。なるほど。
* 拡散の確率推定は難しかった。
    - 途中まで読んだけど諦めた。Pandasって条件による行・列の抽出の文法が複雑な気がする。