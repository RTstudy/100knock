# 5章

## ノック41

* forの中身が分かりにくかったから、書き直したけど行数が合わない。

## ノック42

* `pd.to_datetime`はSeriesに適用できる`strptime`みたいなものか。
* > 結合したデータは、退会した顧客の退会前月のデータのみなので欠損値が多く発生しています。
    + よく分からなかったけど、こういうこと？
    + `customer`は元々customer.csvから作られている。customer.csvは2019/03時点の会員データである。
    + 今、2018/05-2019/02に退会申請した顧客のリストを作成した。
    + ほとんどの会員は2019/03には退会済みのため、name列がNullになった。
* `exit_customer["年月"] = exit_customer["exit_date"].dt.strftime("%Y%m")`はAttribute Errorで動かない
  → `exit_customer["年月"] = pd.to_datetime(exit_customer["exit_date"]).dt.strftime("%Y%m")`

## ノック46

* p.121「このダミー変数ですが、一点注意が必要です。」以下の処理、手でやらないといけないの？もっといいやり方がありそうだけど。

## ノック47

* 決定木を『Pythonではじめる機械学習』pp.70-82で勉強した。
* もっと数理面を勉強したい。・・・そのうち。
