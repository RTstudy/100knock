# 調整した箇所

## ノック23
- additional analysis1,2を追加
    - pivot_tableを使ってクロス集計
    - たぶん後で出てくるところとは思ったが気になったので
    
## ノック24
- aditional analysis 3を追加
    - 本文でいう「最新月」とは2019年3月のことである
    - したがって、2019年3月末で退会したユーザも解析に含めたい
    - しかし、データ上は2019年3月に退会したユーザにもis_deletedフラグがたってしまっている（クロス集計したところ111名であった）
    - この111名も解析に含めるため、is_deletedフラグではなく退会日で絞り込みをする
    
## ノック28
- relativedeltaでなぜわざわざfor loopを使っているのか確認
    - 列を引数に入れるとエラーが発生する。おそらくSeriesデータを直接扱えないためと思われる
    
## ノック30
- is_deletedで層別したmeanのヒストグラムを作成し、違いを明確にする