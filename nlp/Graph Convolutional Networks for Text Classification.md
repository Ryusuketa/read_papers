# WIP: Graph Convolutional Networks for Text Classification
https://wvvw.aaai.org/ojs/index.php/AAAI/article/download/4725/4603

## 主張
GCNを文書分類に使う方法のベンチマークを最初に行なった。

## 解決したい問題点
文書分類

## 従来との差分・新規性
GCNをテキスト分類に使う方法のベンチマークを行なった。
documentはone hot vectorとした。
グラフはノードを文書および単語どちらともを持ち、documentおよび単語のエッジはtf-idf、単語間のエッジはpoint-wise mutual information（PMI）とした。それ以外は0となる。

## 結果・知見
word embeddingを事前に行うモデルなどより精度よく分類を行うことができた。
また、ラベル付きデータ数を減らしたときに、GCNの方が精度が比較的高く保てていることがわかった。
