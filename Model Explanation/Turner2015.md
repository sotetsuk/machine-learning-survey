# A Model Explanation System

- Title: A Model Explanation System
- Authors: R. Turner
- Journal(Conference): Proc. of NIPS workshop
- Year: 2015

## link
- [link to paper](http://www.blackboxworkshop.org/pdf/Turner2015_MES.pdf)
- [related link](http://www.inference.vc/accuracy-vs-explainability-in-machine-learning-models-nips-workshop-poster-review/)

# Personal memo (in japanese)

## 1. どんなもの？
- Model explanation system (MES)を提案。Black box classifierをexplainする。
- credit card transaction historyでの詐欺を検知する識別器に使っている。
- 単一のサンプルに予測に対し説明を行っている。
- False positive（詐欺じゃないのに詐欺と言う）が多くなりがちなので、人間に対する説明があった方がよい。
- interpretableとaccuracy-focusedのトレードオフを考えるのではなく、accuracy-focusedに後から解釈を与えるので、精度を犠牲にしない
- 単一サンプルの予測に対する説明なので、モデル全体について説明するより大分楽。
- Discriminative modelに対するMESでも、input distributionに依存する（本来学習してないはずだが）
- Decision treeとの違いは、back-boxモデルの一つの説明に対し、fitするdecision-treeを作り上げている点

## 2. 先行研究と比べて何がすごい？

## 3. 技術や手法のキモはどこ？

## 4. どうやって有効だと検証した？

## 5. 議論はある？
- input distributionを別で学習する必要がある

## 6. 次に読むべき論文は？
> The downside of the interpretable approach is seen in machine learning competitions, where the winning methods are typically nonparametric, or have a very large number of parameters (e.g., deep learning) [4].
> Discriminative models, even when probabilistic, do not learn the input feature distribution, which we refer to as p [11].

- [4] Ferna ́ndez-Delgado, M., Cernadas, E., Barro, S., and Amorim, D. (2014). Do we need hundreds of classi- fiers to solve real world classification problems? Journal of Machine Learning Research, 15(1):3133–3181.
- [11] Ng, A. Y. and Jordan, M. I. (2002). On discriminative vs. generative classifiers: A comparison of logistic regression and naive Bayes. In Advances in Neural Information Processing Systems 14, pages 841–848.
