# Character-level Convolutional Networks for Text Classification
https://papers.nips.cc/paper/5782-character-level-convolutional-networks-for-text-classification.pdf

## 主張
文字レベルのcnnによる文書分類を提案。cnnを使った初めての論文

## 従来との差分・新規性
cnnで分類を行うこと。
WordNetをつかって類似語にランダムに入れ替えることでデータオーギュメンテーションする。

bag-of-wordsのtf-idf, n-gramのtf-idf、word embeddingを特徴とした各々の分類モデルと比較する。

## 結果・知見
他のモデルに比べて圧倒的に性能が良いわけではない。畳み込みを用いるモデルは比較的良いがそれより大きく優っていることはなかった。