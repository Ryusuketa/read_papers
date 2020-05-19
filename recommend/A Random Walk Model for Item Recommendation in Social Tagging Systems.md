# A Random Walk Model for Item Recommendation in Social Tagging Systems

## 主張
social taggingシステムを使った推薦システムは現代において重要である。一方でdata sparsityが大きな課題として上がる。

## 解決したい問題点
data sparsityの問題。

## 従来との差分・新規性
random walkを用いるアプローチは過去にもあったが、user-item, item-tag, tag-userの二部グラフを順番にrandom walkさせており、計算量が大きかった。
本手法では、random walkするのはあくまでuserグラフ上、itemグラフ上のみであり、その遷移確率の計算にuser-item, item-tag, tag-userのグラフを用いる。

## 結果・知見
定量評価のみ。定性評価なし。性能は他のナイーブな方法に比べて高いが、従来のrandom walkとの差分は大きくはない。
また推薦の精度は、高頻度のタグのみを残すように減らしていっても、精度に直接の影響はなかったため、高頻度のものを残していけばよい。
（ただし、それほど極端に減らしたわけではない。）