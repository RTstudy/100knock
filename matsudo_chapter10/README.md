# 10章

## ノック92

* 正規表現のチェックは[regular expressions 101](https://regex101.com/)が便利です。

## ノック94

* MeCabのインストール方法  
  ```
  $ pip install mecab-python3
  $ pip install unidic-lite
  ```
  https://pypi.org/project/mecab-python3/

* [MeCab の結果を Pandas DataFrame として得る](https://qiita.com/hoto17296/items/97c7ec64923625addf01)

## ノック95

* サンプルコードのままだと意図したとおりに動かないので修正した（ノック96以降も同様）。
    - `part = i.split()[1].split(",")[0]`で品詞が取得できない。MeCabのバージョンの問題？

## ノック96

* サンプルコードのままだと意図したとおりに動かないので修正した。
    - 「、」「。」「？」が来たときの例外処理が必要

## ノック100

* コサイン類似度: [コサイン類似度](https://mathtrain.jp/cosdistance)

