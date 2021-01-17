# 調整した箇所

## ノック84
- [HOG特徴量](https://ikatakos.com/pot/programming/python/packages/scikit-image/hog)

## ノック85
- [Haar-like 特徴を使ったリアルタイム顔検出 ](http://www.akita-pu.ac.jp/neuro/seika/haarlike.pdf)
    - Haar特徴量を使った顔検出の場合、基本的に正面を向いた顔でないと検出できない
    
## ノック86
- sinの定義域は-1～1であり、その範囲を超えてasin仕様とすると'math domain error'が発生する
- gx_out,gy_outは輪郭の点の座標、gx_in,gy_inは顔の各要素の点の座標、dは検出された顔を囲む矩形を表し、.left, .rightは矩形の左端と右端のx座標である
    - この計算でどうして顔の角度の算出になるのかよくわからない。計算が単純すぎ？
    - 参考
    	- [顔向き推定について調査中](https://qiita.com/nonbiri15/items/f6910a993457a1862632)

## ノック90
- [畳み込み積分や移動平均を求めるnumpy.convolve関数の使い方](https://deepage.net/features/numpy-convolve.html)
- [NumPyのarange, linspaceの使い方（連番や等差数列を生成）](https://note.nkmk.me/python-numpy-arange-linspace/)