# 調整した箇所

## ノック32
- 標準化した値がちゃんと平均0、分散1になっているかのチェックを実施
    - ちなみにStandardScalerは出力がnumpyオブジェクトになっていることに注意する
    - pandasデータフレームではないのでheadとかdescribeとかが使えない
    
## ノック33
- コードは変更せず、noteを追加
- k-means法は乱数を使うためseedを設定しないと実行ごとに結果が変わる
- それが気に入らないのであれば、リンク先に示してあるようなseedの設定が必要

## ノック34
- 元のクラスタ番号が番号順に並んでいないので、sortedを追加
- 凡例を表示するように変更

## ノック38
- 平均来場回数、性別、キャンペーン、会員区分を追加してモデルを作成したところ、スコアが改善した

## ノック38_2:特徴量間の関係を調査
- 特徴量間の関係を見るためにペアプロットを実施
    - count_xとcount_predの間に線形の関係っぽいものは見えるが、ばらつきが大きいため、おそらく予測性能は低いだろう
    - meanは二峰性の分布を示している。また、count_xに比べてcount_predとの線形性が強そう。そのためにmeanを追加することで予測性能が向上した模様
- meanのヒストグラムをroutine_flgでグループ分けして作成
    - 定期的に通っている人の方が平均回数が多いグループに多く、ルーチンでない人は平均回数が少ないグループに分類できる
- meanのヒストグラムをcampaign_idでグループ分けして作成
    - どのキャンペーンで入会したか、もどうやら回数に影響がありそう
- meanとcount_predの関係をroutine_flgでグループ分けして散布図で表示
- meanとcampaign_idの関係をroutine_flgでグループ分けして散布図で表示
- routine_flgとgender, campaign_id, class_nameのクロス表（行で標準化）を作成
    - routine_flgとcampaign_idに関係がありそう

## ノック39
- 平均来場回数の係数が一番大きくなった