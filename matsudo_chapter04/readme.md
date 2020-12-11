# 4章

## ノック32

* k-meansクラスタリング  
    https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html
    - 3変数以上でのk-meansクラスタリングって、重心からの距離をどう定義するの？
    > k-means clustering minimizes within-cluster variances (squared Euclidean distances), but not regular Euclidean distances, which would be the more difficult Weber problem: the mean optimizes squared errors, whereas only the geometric median minimizes Euclidean distances. For instance, better Euclidean solutions can be found using k-medians and k-medoids.  
    > https://en.wikipedia.org/wiki/K-means_clustering
    -  よくわからん。ユークリッド距離なのかな？


* StandardScaler  
https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html


## ノック34

* n_components
    > int, float, None or str
    > Number of components to keep. if n_components is not set all components are kept  
    https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html

* seabornで[5×5のアレ](https://qiita.com/HiromuMasuda0228/items/babdfa175815fb3e3a94#%E5%B7%A8%E5%A4%A7%E3%81%AA%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BB%E3%83%83%E3%83%88%E3%81%8B%E3%82%89%E5%8A%B9%E7%8E%87%E3%82%88%E3%81%8F%E3%82%A4%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%82%92%E5%BE%97%E3%82%8B)作ったほうがいいのでは？
    - 作った

* 主成分分析、勉強したことないから良いテキストがほしい。
    + この辺を読んだ。
        * 『Pythonではじめる機械学習』 3.4.1 主成分分析
        * [10分でわかる主成分分析(PCA)](https://www.slideshare.net/takanoriogata1121/10pca-49324044)

* > 一般的には、今回作成された2つの軸（変数）が、どの変数から成り立っているかを分析していくと、軸の意味づけが可能となりますが、この本では、次元削除の話はここまでに留めます。
    + たしかにここは気になる。


## ノック35

* クラスター1に退会者しかいない
* 結果（おそらくクラスタリングの結果）が本と異なる。
    + 機械学習だから？

## ノック36

* 機械学習の概要を説明したAppendix2の説明が、整理されていてわかりやすい。
* forの中身を理解するのに時間がかかった。


## ノック37

* importをコードの途中に書くのは[PEP-8規約](https://www.python.org/dev/peps/pep-0008/#imports)違反です。（警察）