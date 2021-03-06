# Salience Rank: Efficient Keyphrase Extraction with Topic Modeling
## 主張
Topical PageRankはキーワード抽出法の一つである。単語共起グラフに対して、トピックモデルを導入し、そのある単語に対するあるトピックにおける生起確率をランダムジャンプ項として導入する。

Topical PageRank（TPR）はトピック数ぶんだけPageRankを回すので重たい。本論文で提案する手法であるSalience Rankは一度だけPageRankを回せば良い。（だからSalience？

## 解決したい問題点
TPRはトピックごとにPageRankを実行して、フレーズのランクを計算するため計算が重たい。

他にもSingle TPRが比較できる。これはPageRankにおけるランダムジャンプの項をトピック中のワード正規確率のベクトルと、ドキュメントのトピック分布のベクトルのcosine similarity(Topical Word Importance)に置き換えてPageRankを実行したものである。これによってPageRankの実行回数を減らすことができる。

## 従来との差分・新規性
Single TPRとの差分は、トピックに関する項を一つにまとめただけでなく、corpus specifityも導入した点である。特定のトピックにのみ生起する単語のスコアを高くするTopic specifityと、コーパス中での生起確率からなるcorpus specifityの按分より、word salienceを求める。
このword salienceをランダムジャンプ項に利用する。
利点はcorpus内の重要性をベースにキーワード抽出を行うか、トピックでの重要性をベースにキーワード抽出を行うかである。

## 結果・知見
性能比較において、従来手法と比較して負けない or 良い性能を誇った。
また、corpus specifityを重要視した場合一般的な言葉を、topic specifityを重視した場合、その文章内で特徴的な語を高いランクに置くようになった。