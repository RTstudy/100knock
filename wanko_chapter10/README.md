# 調整した箇所

## ノック95
- words_arr = [] が二回でてくるけど一方だけで良いのでは？

## ノック96
- appendとextendの違い
    - [Pythonでリスト（配列）に要素を追加するappend, extend, insert](https://note.nkmk.me/python-list-append-extend-insert/)
    
## ノック97
- 参考
    - [Python3×日本語：自然言語処理の前処理まとめ](https://qiita.com/chamao/items/7edaba62b120a660657e)
    
## ノック100
- コサイン類似度は内積の公式から導出
    - cosθ = a・b / |a||b|
    
    
## Mecabの挙動確認
- mecab_testを追加し、出力形式を確認
    - [MecabをPythonで使うまで](https://qiita.com/Sak1361/items/47e9ec464ccc770cd65c)
    - matsudoさんの出力はChaSen形式と呼ばれるもので、品詞の出力位置が本書と異なる
        - [ChaSen -- 形態素解析器](https://chasen-legacy.osdn.jp/)
        - ChaSenという別の形態素解析器（日本語向け）があります。ほかにもいろいろ。
    - 直接的な原因は不明だが、バージョン違いによるものの可能性大
        - wankoのバージョンは0.996.3でした
        - バージョンの確認はanacondaのEnvironmentsから。MeCab.VERSIONだと0.996までしか出ない。