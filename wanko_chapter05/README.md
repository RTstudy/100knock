# 調整した箇所

## ノック41
- 留意事項
    - year_monthsが年月でソートされている前提でのコードとなっている
    - もしソートされていない状態でunique()をするとたしかソートされずにi-1が必ずしもひと月前の値になるとは限らないはず
    - 元のデータがどうなっているかも注意してみる必要がある
    
## ノック42
- 元のコードのままだと`dt.strftime`のところで`Can only use .dt accessor with datetimelike values`というエラーが発生する
    - `exit_customer['exit_date'] = pd.to_datetime(exit_customer['exit_date'])`の一文を追加した
    - おそらくrelativedeltaを使うとdatetime型でなくなることが原因と思われる
    - 正誤表にも記載はなく、もしかしたらライブラリのバージョン違いによるものかもしれない
    
## ノック43
- 各顧客ごとに１レコードずつランダムサンプリングするには
    - 元のコードでは一度データフレームの行をシャッフルして重複排除する、という方法をとっている
    - 顧客idでgroupbyして、そのgroupに対してsampleを実行する、という方法もある。ただし、微妙に時間がかかるのでもしかしたら実用上は難しいかも？
        - [pandas.core.groupby.DataFrameGroupBy.sample](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.sample.html)
        
## ノック48
- オリジナルコードの正答率の算出方法はややまだるっこしい
    - y_predとy_testの差の絶対値を合計すれば誤りの数になるので、それをもとに正答率を算出する方が簡単
    - というか、そのあとすぐに出てくるscoreメソッドを使う方がずっと良い
- 本文では単純に木の深さを5として比較しているが、グリッドサーチで最適なパラメータを探す方法もあるのでは？
    - [Pythonのグリッドサーチで決定木のハイパーパラメータを調整！](https://watlab-blog.com/2020/02/20/grid-search-decisiontree/)
    - [決定木(分類)のハイパーパラメータとチューニング](https://qiita.com/FujiedaTaro/items/47e06c758b451cbda412)
    - 本気でやると時間がかかりすぎるので、ここではmax_depthをサーチする形とした

## ノック49
- 木構造を可視化
    - [Pythonの決定木をdtreevizでスマートに可視化する](https://qiita.com/calderarie/items/e4321bff95ac3042601b)
    - dtreevizはインストールがうまくいかなかったので断念
    
## おまけ
- この章では決定木を使っているが、二値分類ならばロジスティック回帰でも良い
    - ランダムフォレスト、ブースティングなどの決定木を拡張したモデルでも良い
    - 本文のデータは特徴量がそこまで多くないため、わざわざランダムフォレストやブースティングを使う必要はないが、頭の片隅においておくと良い
- 決定木は特徴量がどのように分類に使われているのかがわかりやすく、モデルの説明可能性という意味では良い手法である
- 一方で決定木は精度をそこまで出せるモデルではないため、精度を求めるならば他の手法を選ぶと良い