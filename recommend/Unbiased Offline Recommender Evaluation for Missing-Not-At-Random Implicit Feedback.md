<script async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS_CHTML"></script>
<script type="text/x-mathjax-config">
 MathJax.Hub.Config({
 tex2jax: {
 inlineMath: [["\\(","\\)"] ],
 displayMath: [ ['$$','$$'], ["\\[","\\]"] ]
 }
 });
</script>


# Unbiased offline recommender evaluation for missing-not-at-random implicit feedback.


## 主張
推薦システムなどのランキングのオフライン評価は人気度や既存の推薦システムによるバイアスを受ける。

これは無視できるものではないので、それを補正したunbiasedな評価方法を提案する。


## 解決したい問題点
評価指標にbiasが乗って評価されること。

## 従来との差分・新規性
unbiasedな評価方法を提案。これはランキングの評価指標ごとに評価されるものではなくて、あらゆるランキングの評価方法に対して有効である。

推薦・検索アイテムに関して状態が既知の時のランキング評価は次の通り

$$ R(\hat{Z}) = \frac{1}{|U|}\sum_{u \in U}\frac{1}{|S_u|}\sum_{i \in S_u} c(\hat{Z}_{u,i}) $$
ここで\(Z\) はランキング, \(R(\hat{Z})\)はランキング評価関数、\(U\)はユーザー集合、\(S_u\)はユーザー、\(c(\cdot)\)はランキング評価関数。

Average-over-all(AOA)評価関数では、ユーザーにexposureされたアイテムのみに関して評価を行う方法で次の通りである。
$$ R_{\rm AOA}(\hat{Z}) = \frac{1}{|U|}\sum_{u \in U}\frac{1}{\sum_{u \in U}O_{u,i}}\sum_{i \in S_u} c(\hat{Z}_{u,i})O_{u,i} $$
またAOAは、人気のアイテムを上に持ってくるほど評価を高くする傾向にある。

ここで\(O_{u,i}\)はユーザーに露出したか否かの{0,1}の値である。この\(O_{u,i}\)に関する期待値をとっても\(R(\hat{Z})\)とは一致しない。
ここで次のようなInverse-Propensity-Scoringを提案する。

$$ R_{\rm IPS}(\hat{Z}) = \frac{1}{|U|}\sum_{u \in U}\frac{1}{|S_u|}\sum_{i \in S_u}\frac{c(\hat{Z}_{u,i})O_{u,i}}{P_{u,i}} $$

ここで\(P_{u,i}\)はpropensity確率である。
\(O\)に関する期待値を取ると、\(R(\hat{Z})\)と一致する。

最終的に\(O\)を含まない次のSelf-Normalized Inverse-Prppensity-Scoring(SNIPS)を提案する。
また、同時に\(P_{u,i}\)の推定方法も提案する。これはpopularity-basedな方法で推定している。

## 結果・知見
いくつかのデータセットおよびimplicit feedbackを用いたアイテムのランキング手法に関してAOAとIPSとで比較を行った。
結果として、AOAはどの手法でもIPSにくらべてやや良い結果を出していた。また、複数の手法を同時に比較した時、IPSのほうが手法間における性能の差を大きくしており、手法同士の比較により有用だと考えられる。