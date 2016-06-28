# Model Explanation

## 論文

- Ribeiro et al., 2016 [“Why Should I Trust You?” Explaining the Predictions of Any Classifier](Ribeiro+2016.md) ![model:any](https://img.shields.io/badge/model-any-blue.svg) ![in:local](https://img.shields.io/badge/in-local-brightgreen.svg)
- Turner, 2015, [A Model Explanation System](Turner2015.md) ![model:any](https://img.shields.io/badge/model-any-blue.svg) ![in:local](https://img.shields.io/badge/in-local-brightgreen.svg)
- Baehrens et al., 2010, How to explain individual classification decisions ![model:any](https://img.shields.io/badge/model-any-blue.svg) ![in:local](https://img.shields.io/badge/in-local-brightgreen.svg)
- Koyamada et al., 2015, Principal Sensitivity Analysis ![model:any](https://img.shields.io/badge/model-any-blue.svg) ![in:local](https://img.shields.io/badge/in-global-red.svg)
- Turner 2016, A Model Explanation System: Latest Updates and Extensions ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Park et al., 2016, ACDC: α-Carving Decision Chain for Risk Stratification ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Dhurandhar et al., 2016, Building an Interpretable Recommender via Loss-Preserving Transformation ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Srivastava et al., 2016, Clustering with a Reject Option: Interactive Clustering as Bayesian Prior Elicitation ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Chen et al., 2016, Enhancing Transparency and Control when Drawing Data-Driven Inferences about Individuals ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Goodman et al., 2016, EU Regulations on Algorithmic Decision-Making and a "Right to Explanation" ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Abdollahi et al., 2016, Explainable Restricted Boltzmann Machines for Collaborative Filtering ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Moeyersoms et al., 2016, Explaining Classification Models Built on High-Dimensional Sparse Data ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Das et al., 2016, Human Attention in Visual Question Answering: Do Humans and Deep Networks Look at the Same Regions? ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Krakovna et al., 2016, Increasing the Interpretability of Recurrent Neural Networks Using Hidden Markov Models ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Jandot et al., 2016, Interactive Semantic Featuring for Text Classification ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Mostafa et al., 2016, Interpretability in Linear Brain Decoding ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Souillard-Mandar et al., 2016, Interpretable Machine Learning Models for the Digital Clock Drawing Test ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Su et al., 2016, Interpretable Two-level Boolean Rule Learning for Classification ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Gallego-Ortiz et al., 2016, Interpreting Extracted Rules from Ensemble of Trees: Application to Computer-Aided Diagnosis of Breast MRI ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Yu et al., 2016, Learning Interpretable Musical Compositional Rules and Traces ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Hara and Hayashi, 2016, Making Tree Ensembles Interpretable ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Condry, 2016, Meaningful Models: Utilizing Conceptual Structure to Improve Machine Learning Interpretability ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Ribeiro et al., 2016, Model-Agnostic Interpretability of Machine Learning ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Lipton 2016, The Mythos of Model Interpretability ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Reing et al., 2016, Toward Interpretable Topic Discovery via Anchored Correlation Explanation ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Krause et al., 2016, Using Visual Analytics to Interpret Predictive Machine Learning Models ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Zrihem et al., 2016, Visualizing Dynamics: from t-SNE to SEMI-MDPs ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)
- Handler et al., 2016, Visualizing Textual Models with In-Text and Word-as-Pixel Highlighting ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)

## 会議・ワークショップ
- [WHI 2016 @ ICML](https://sites.google.com/site/2016whi/) ![@WHI2016](https://img.shields.io/badge/%40-WHI2016-orange.svg)

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
