# Inbox
とくにテーマ毎にまとめてない論文で読んだものについて列挙してコメントをする。

## 2010

### Pan et al. [Transfer Learning in Collaborative Filtering for Sparsity Reduction](http://www.aaai.org/ocs/index.php/AAAI/AAAI10/paper/viewFile/1649/1963/) AAAI 2010

ユーザ、アイテムの双方についてよりリッチなドメインがあるときに、それらを使って転移学習をするCoordinate System Transfer(CST)という手法を提案。
元々SVDをかけたいRという行列と、R(1)とR(2)というより情報がリッチな行列があるとする。R(1)とR(2)それぞれSVDをして基底行列をとってきて、それに近くなるよう正則化をかけてRをSVDする。
NetflixとMovieLensのデータセットを使って実験を行い、SoTAを達成。

## 2012

### Gretton et al. [A Kernel Two-Sample Test](http://www.jmlr.org/papers/volume13/gretton12a/gretton12a.pdf) JMLR 2012

## 2015

### Migut et al. [Visualizing Multi-Dimensional Decision Boundaries in 2D](https://pure.uva.nl/ws/files/2110683/164710_431596.pdf)  Data Min Knowl Disc 2015

## 2016

### Jaderberg et al. [Decoupled Neural Interfaces using Synthetic Gradients](https://arxiv.org/pdf/1608.05343v1.pdf) arXiv:1608.05343 2016

### Toderici et al. [Full Resolution Image Compression with Recurrent Neural Networks](https://arxiv.org/pdf/1608.05148v1.pdf) arXiv:1608.05148 2016

- http://itpro.nikkeibp.co.jp/atcl/idg/14/481542/082600264/

### Champandard [Semantic Style Transfer and Turning Two-Bit Doodles into Fine Artwor](https://arxiv.org/pdf/1603.01768v1.pdf) arXiv:1603.01768 2016

- https://github.com/alexjc/neural-doodle

### Su et al. [Learning from Real Users: Rating Dialogue Success with Neural Networks for
Reinforcement Learning in Spoken Dialogue Systems](https://arxiv.org/pdf/1508.03386v1.pdf) arXiv:1508.03386 2015

- http://qiita.com/icoxfog417/items/d0206a9a1b3b445105ea

### Cheng et al. [Wide & Deep Learning for Recommender Systems](https://arxiv.org/pdf/1606.07792v1.pdf) arXiv:1606.07792 2016

### Lipton et al. [The Mythos of Model Interpretability](https://arxiv.org/pdf/1606.03490v2.pdf) ICMLWS 2016

解釈性の尺度について

### Higgins et al. [Early Visual Concept Learning with Unsupervised Deep Learning](https://arxiv.org/pdf/1606.05579v3.pdf) arXiv:1606.05579 2016

## 2017

### Jang et al. [CATEGORICAL REPARAMETERIZATION WITH GUMBEL-SOFTMAX](https://arxiv.org/pdf/1611.01144.pdf) ICLR 2017

カテゴリカル分布の微分可能なバージョンとしてGumbel-Softmaxを提案した。
例えばVAEのようなモデルは目的関数中にカテゴリカル分布による期待値計算が入っているが、カテゴリカル分布からのone-hotなサンプル（[0, 1, 0, ...]など）を使ってサンプリングをして目的関数の値を求めると、微分不可能になってしまい誤差逆伝搬法ができなくなってしまう。
そこで、Gumbel分布からのサンプルを使ってsoftmax関数をかませることで"微分可能なカテゴリカル分布"であるGumbel-Softmaxを新しく提案した。
Gumbel-Softmaxは温度τをパラメータに持ち，τ↓0でカテゴリカル分布のようにサンプルがone-hotになっていく。
実験的には特に、VAEの学習をELBOで評価したときに良い性能を示した。

