# 調整した箇所

## ノック71
- df_linksは20ユーザの隣接行列になっているので、ここからnetworkxにノードとエッジの情報を作ることができるはず、もしくは前回やったようにmeltするか？
    1. [Converting to and from other data formats](https://networkx.org/documentation/stable//reference/convert.html)
        - ただしこれだとノードの名前を後でつけなければならずちょっとひと手間かかってしまう
    1. 7章でやったようにmeltする
        - 列名をint型にしておかないとsourceと異なるtypeになってしまい、異なるノード名として扱われてしまう点に注意する

## ノック72
- ここでやっていること
    1. ノード0をactivate
    1. ノード0とつながっているノードを調べる
    1. ノード0とつながっているノードを確率0.1でactivate
    1. activateになっているノードを探す
    1. activateになっているノードとつながっているノードを調べる
    1. activateになっているノードとつながっているノードを確率0.1でactivate
    1. 4に戻る
    
## ノック74
- ここでやっていることはノック72の伝播と同じで、現在activeなノードとつながっているノードは一定確率でactiveになる
- 合わせて、すべてのactiveなノードは一定確率でdeactivateされるものとする
- グラフを描くところで、forループで描く時点ごとの合計を算出している部分は内包表記にできるはず
    - 個人的には処理が少ないforループは内包表記にするのが良いと思うが、流派があるようなのでそこはお好みで
- 会員の増減グラフは乱数を使っているので必ずしも本文と同じようにはならない点に注意すること
    - 特に最後の消滅確率を高くした場合のシミュレーションの場合、いきなりノード0がdisapparenceになってその後ずっと0になる、というケースも割とあることに留意すること
    - なので、ひとつ前のシミュレーションの最後を初期状態として消滅確率を高くしたシミュレーションをするとわかりやすい
    
# ノック77
- リンク数の集計をforループでやっているが、pandasの集計を使ったらもっと簡単
    - ちなみに隣接行列は対称行列なので、合計を列でとっても行でとっても同じ、つまりaxis=0とaxis=1は同じ結果になる
    
# ノック78
- 拡散の確率推定の部分が何をやっているのかよくわからない