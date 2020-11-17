
# Word Rotator's Distance
https://arxiv.org/abs/2004.15003

## 主張
semantic text similarity（STS）における新しい指標を提案する。
角度に対するEMDを考えることで、よりsemanticな類似度を評価できるようになる。
本手法ではdirectionに対するEMDを考えることでalignment basedなSTSにおいてdirectionを考えられるようにする。

## 解決したい問題点
word vectorではnormとdirectionはそれぞれ異なる意味を持つと考えられるが、従来のalimentd basedなSTSではnormとdirectionをわけて評価することができなかった。
normはあくまでそのwordに対する重要度のみを考えてると考えれるため、類似度の文脈では切り分けたいと考えられる。

## 従来との差分・新規性
本手法ではdirectionに対するEMDを考えることでalignment basedなSTSにおいてdirectionを考えられるようにする。
また、denoisingや重み付けを使用したVector Converter（VC）を用いることでさらに精度良く類似度を評価できるようにする。

## 結果・知見
先にcos similarityがSTSタスクにおいて良好な性能を示すことを確認し、WMDとWRDを比較した。
WMDに対してWRDはナイーブな比較においても改善を示し、VCを用いることでさらに性能改善をした。
ベーシックなAlignment basedなSTSに対する比較はなかった。