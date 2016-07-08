# Model Explanation

## 論文

##### Ribeiro et al., 2016 [“Why Should I Trust You?” Explaining the Predictions of Any Classifier](Ribeiro+2016.md) 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](http://arxiv.org/pdf/1602.04938.pdf)
[![source:github](https://img.shields.io/badge/source-github-8470FF.svg?style=flat-square?maxAge=86400)](https://github.com/marcotcr/lime)
![@:kdd](https://img.shields.io/badge/%40-KDD-6666ff.svg?style=flat-square?maxAge=86400)
![model:any](https://img.shields.io/badge/model-any-blue.svg?style=flat-square?maxAge=86400) 
![in:local](https://img.shields.io/badge/in-local-brightgreen.svg?style=flat-square?maxAge=86400)

_local_に_interpretable_なモデルで近似する手法LIMEを提案。また**SP-LIMEという代表的なサンプルを取ってくる手法も提案することで、モデルを_global_に理解することも可能**だと主張している。被験者を使った実験も行って妥当性を検証している。

##### Turner, 2015, [A Model Explanation System](Turner2015.md) 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](http://www.blackboxworkshop.org/pdf/Turner2015_MES.pdf)
![@:nips](https://img.shields.io/badge/%40-NIPS (WS)-ff4040.svg?style=flat-square?maxAge=86400)
![model:any](https://img.shields.io/badge/model-any-blue.svg?style=flat-square?maxAge=86400) ![in:local](https://img.shields.io/badge/in-local-brightgreen.svg?style=flat-square?maxAge=86400)

##### Baehrens et al., 2010, [How to explain individual classification decisions](Baehrens+2010.md)
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](http://www.jmlr.org/papers/volume11/baehrens10a/baehrens10a.pdf)
![@:jmlr](https://img.shields.io/badge/%40-JMLR-8ee5ee.svg?style=flat-square?maxAge=86400)
![model:any](https://img.shields.io/badge/model-any-blue.svg?style=flat-square?maxAge=86400) 
![in:local](https://img.shields.io/badge/in-local-brightgreen.svg?style=flat-square?maxAge=86400)

モデルを_local_に説明する_local explanation vector_（単なる勾配）を提案。

##### Rasmussen et al., 2011, Visualization of nonlinear kernel models in neuroimaging by sensitivity maps
[![source:link](https://img.shields.io/badge/source-link-yellow.svg?style=flat-square?maxAge=86400)](http://www.sciencedirect.com/science/article/pii/S1053811910016198)
![model:any](https://img.shields.io/badge/model-any-blue.svg?style=flat-square?maxAge=86400) 
![in:global](https://img.shields.io/badge/in-global-red.svg?style=flat-square?maxAge=86400)

sensitivity analysisを使ったneuroimaging応用。
sensitivity analysisは勾配を平均とったもので、_global_なモデルの（線形な）可視化と言える。

##### Koyamada et al., 2015, Principal Sensitivity Analysis 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](http://arxiv.org/pdf/1412.6785v2.pdf)
![model:any](https://img.shields.io/badge/model-any-blue.svg?style=flat-square?maxAge=86400) ![in:global](https://img.shields.io/badge/in-global-red.svg?style=flat-square?maxAge=86400)

モデルを_global_に説明する_Principal Sensitivity Analysis(PSA)_を提案。
線形なクラスに限定して、最も説明出来ている基底を探している。

##### Turner 2016, A Model Explanation System: Latest Updates and Extensions 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Park et al., 2016, ACDC: α-Carving Decision Chain for Risk Stratification 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Dhurandhar et al., 2016, Building an Interpretable Recommender via Loss-Preserving Transformation 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Srivastava et al., 2016, Clustering with a Reject Option: Interactive Clustering as Bayesian Prior Elicitation 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Chen et al., 2016, Enhancing Transparency and Control when Drawing Data-Driven Inferences about Individuals 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Goodman and Flaxman, 2016, EU Regulations on Algorithmic Decision-Making and a "Right to Explanation" 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)

EUがアルゴリズムの意思決定について、その意思決定の対象となった人が説明を求める権利を有する、という規則(the General Data Protection Regulation (GDPR) 
)を採択したという話とその影響についての考察。

##### Abdollahi et al., 2016, Explainable Restricted Boltzmann Machines for Collaborative Filtering 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Moeyersoms et al., 2016, Explaining Classification Models Built on High-Dimensional Sparse Data 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Das et al., 2016, Human Attention in Visual Question Answering: Do Humans and Deep Networks Look at the Same Regions? 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Krakovna et al., 2016, Increasing the Interpretability of Recurrent Neural Networks Using Hidden Markov Models 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Jandot et al., 2016, Interactive Semantic Featuring for Text Classification 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Mostafa et al., 2016, Interpretability in Linear Brain Decoding 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Souillard-Mandar et al., 2016, Interpretable Machine Learning Models for the Digital Clock Drawing Test 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Su et al., 2016, Interpretable Two-level Boolean Rule Learning for Classification 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Gallego-Ortiz et al., 2016, Interpreting Extracted Rules from Ensemble of Trees: Application to Computer-Aided Diagnosis of Breast MRI 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Yu et al., 2016, Learning Interpretable Musical Compositional Rules and Traces 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Hara and Hayashi, 2016, Making Tree Ensembles Interpretable 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Condry, 2016, Meaningful Models: Utilizing Conceptual Structure to Improve Machine Learning Interpretability 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Ribeiro et al., 2016, Model-Agnostic Interpretability of Machine Learning 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Lipton 2016, The Mythos of Model Interpretability 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Reing et al., 2016, Toward Interpretable Topic Discovery via Anchored Correlation Explanation 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Krause et al., 2016, Using Visual Analytics to Interpret Predictive Machine Learning Models 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Zrihem et al., 2016, Visualizing Dynamics: from t-SNE to SEMI-MDPs 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)
##### Handler et al., 2016, Visualizing Textual Models with In-Text and Word-as-Pixel Highlighting 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)

## 会議・ワークショップ
##### WHI 2016 @ ICML
[![source:link](https://img.shields.io/badge/source-link-yellow.svg?style=flat-square?maxAge=86400)](https://sites.google.com/site/2016whi/)
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](https://drive.google.com/file/d/0B9mGJ4F63iKGZWk0cXZraTNjRVU/view)
![@:icml](https://img.shields.io/badge/%40-ICML (WHI2016)-orange.svg?style=flat-square?maxAge=86400)

## 関連研究者
- [Marco Tulio Ribeiro](https://homes.cs.washington.edu/~marcotcr/): author of LIME 
- Turner: author of MES

## なぜ重要なのか

## 考えられる応用先
- ゲームAI（AlphaGoは人間を超える性能を示したが、その一手を何故打ったのかは分からない）
- 医療画像（なぜfMRI脳機能画像から統合失調症と判断したのか？なぜレントゲン写真から肺がんだと判断したのか？）
- 文章校閲（学習によって自動校閲ができたとして、例えばなぜそのPassiveは是なのか（否なのか？））
- 異常検知（なぜ異常だと判断したのか）
- Data leakageの検出 (mentioned by Ribeiro et al., 2016)
  - これはAccuracyなんかを見ているだけでは厳しい
- Turner 2015: クレカの不正利用検知（なぜ不正利用だと感じたのか）
- Ribeiro et al., 2016:

## サーベイポイント

- globalかlocalか
- 対象となるモデルは何か
- 対象となるデータのドメインは何か（e.g., 画像、自然言語、構造化されたデータ）
- 対象となるアプリケーションは何か（e.g., diagnosis, クレカ不正利用）
- 使っているデータセットは何か
- Explanationの定義は何か
- その可視化はどう有用なのか

## Tags 

##### source 
[![source:pdf](https://img.shields.io/badge/source-pdf-green.svg?style=flat-square?maxAge=86400)](link)
[![source:link](https://img.shields.io/badge/source-link-yellow.svg?style=flat-square?maxAge=86400)](link)
[![source:github](https://img.shields.io/badge/source-github-8470FF.svg?style=flat-square?maxAge=86400)](link)

##### @
![@:kdd](https://img.shields.io/badge/%40-KDD-6666ff.svg?style=flat-square?maxAge=86400)
![@:nips](https://img.shields.io/badge/%40-NIPS-ff4040.svg?style=flat-square?maxAge=86400)
![@:icml](https://img.shields.io/badge/%40-ICML-orange.svg?style=flat-square?maxAge=86400)
![@:jmlr](https://img.shields.io/badge/%40-JMLR-8ee5ee.svg?style=flat-square?maxAge=86400)

##### model
![model:any](https://img.shields.io/badge/model-any-blue.svg?style=flat-square?maxAge=86400)

##### in
![in:local](https://img.shields.io/badge/in-local-brightgreen.svg?style=flat-square?maxAge=86400)
![in:local](https://img.shields.io/badge/in-global-red.svg?style=flat-square?maxAge=86400)

##### application
![application:diagnosis](https://img.shields.io/badge/application-diagnosis-ff69b4.svg?style=flat-square?maxAge=86400)


