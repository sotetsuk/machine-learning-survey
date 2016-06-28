# Model Explanation

- Ribeiro et al., 2016 [“Why Should I Trust You?” Explaining the Predictions of Any Classifier](Ribeiro+2016.md) ![model:any](https://img.shields.io/badge/model-any-blue.svg) ![in:local](https://img.shields.io/badge/in-local-brightgreen.svg)
- Turner, 2015, [A Model Explanation System](Turner2015.md) ![model:any](https://img.shields.io/badge/model-any-blue.svg) ![in:local](https://img.shields.io/badge/in-local-brightgreen.svg)
- Baehrens et al., 2010, How to explain individual classification decisions ![model:any](https://img.shields.io/badge/model-any-blue.svg) ![in:local](https://img.shields.io/badge/in-local-brightgreen.svg)
- Koyamada et al., 2015, Principal Sensitivity Analysis ![model:any](https://img.shields.io/badge/model-any-blue.svg) ![in:local](https://img.shields.io/badge/in-global-red.svg)

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
