# FORMAN, George. An extensive empirical study of feature selection metrics for text classification. Journal of machine learning research, 2003, 3.Mar: 1289-1305.
[リンク](http://www.jmlr.org/papers/volume3/forman03a/forman03a.pdf)

## 主張
20の特徴量選択を使って229のテキスト分類問題をとき、その結果を評価した。

## 解決したい問題点
文書分類にはclass distribution skew（おそらくラベルアンバランスの問題を指す）があり、この状況においてどの特徴量選択が良いかを明確にする。
20の特徴量選択を使って229のテキスト分類問題をとくことで評価した。（マルチラベリングを1-of-mのbinary classificationに置き換えることで229のタスクを生成）

## 従来との差分・新規性
特徴量選択が与える影響を調べるタスクは他にもあるが、文書分類について調べたものはない。
今回改めて文書分類について調べたことが新規性である。

## 方法
ワードごとに特徴量選択手法を実行し、どのような結果が得られるか調べた。

## 結果・知見
- 分類モデルにはSVMを採用
- class distribution skewが高い時ほど特徴量選択が有効に働き、他方でclass distrubtion skewが低いと有効には働かない。
- 記事中で提案されているBNSという指標が一番良いパフォーマンスだった
- chi二乗値がしばしば使われているがこの報告ではあまり良い結果を導かなかった。

