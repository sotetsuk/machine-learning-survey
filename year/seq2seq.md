# Seq2Seq
Seq2SeqやAttentionに関する論文や、応用として活用している論文を年代毎に列挙する。コメントは[この方針](https://github.com/sotetsuk/machine-learning-survey/tree/renewal#年代毎-1)に従って付けられている。


（同じ年の中での上下に特に意味はなく、時系列順になっているわけではない）

## 2014

### Sutskever et al. [Sequence to sequence learning with neural networks](http://papers.nips.cc/paper/5346-information-based-learning-by-agents-in-unbounded-state-spaces.pdf) NIPS 2014

いわゆるSeq2Seq論文（似たようなEncoder-DecoderモデルのCho et al. (2014)よりは後）。
LSTMを積んだEncoderで入力系列（可変長）を固定長のベクトルにエンコードし、その固定長ベクトルを同じくLSTMを詰んだDecoderの隠れ状態の初期値として出力系列を生成。
シンプルな構造だが、WMT'14の英仏翻訳のデータセットにおけるBLUEでの評価でベースラインを上回る結果。

### Cho et al. [Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](https://arxiv.org/pdf/1406.1078.pdf) EMNLP 2014

Sutskever et al. (2014)に似たEncoder-Decoderモデル（こちらが先）。
Sutskever et al. (2014)と違い、Encoderの最後の隠れ状態がDecoderの各t'番目のトークンについての尤度計算に直接組み込まれている。
直接Encoder-Decoderモデルから出力系列を生成するというよりスコアの補正に使っている。
WMT’14の英仏翻訳のデータセットにおけるBLEUでの評価でベースラインを上回る結果。

## 2015

### Bahdanau et al. [Neural machine translation by jointly learning to align and translate](https://arxiv.org/pdf/1409.0473.pdf) ICLR 2015

Attentionメカニズムを導入した論文。
Sutskever et al. (2014)では入力系列を固定長のベクトルにまとめていたが、これは無理があるのに加え、最初の方の入力を忘れてしまう問題がある（実際Sutskever et al. (2014)は入力系列を逆にしていた）。
そこで入力系列のt毎の隠れ層の重み付き平均を使って出力系列のt'番目のトークンを予測する手法を提案。
WMT'14の英仏翻訳データセットにおいて、Cho+14の手法と比べBLUEが大きく改善すること、特に長い文長にロバストなことを実験的に示した。

### Sorokin et al. [Deep Attention Recurrent Q-Network](https://arxiv.org/pdf/1512.01693v1.pdf) NIPSWS 2015

DQNにRNNを使ったDRQNにAttentionメカニズムを組み合わせたDARQNを提案。
意志決定時の直前4画像フレームだけでなく長期の状態の情報を使いつつ、特定の画像領域にだけ注視するのが目的。
時刻t毎に画像フレームをCNNを使って複数の特徴量マップを出力し、これと時刻t-1のRNNの隠れ状態からattentionを計算する。
そしてこのattentionによる特徴量マップの重み付き平均によりcontextを作り、これをRNNの時刻tでの入力とする。
AtariのいくつかのゲームでDQNやDRQNより高い報酬を得ることに成功している。
Attentionがゲーム攻略に重要なオブジェクトを示しているという旨の主張もしている。

### Vinyals and Quoc [A neural conversational model](https://arxiv.org/pdf/1506.05869v3.pdf) ICML 2015

Sutskever et al. (2014)のSeq2Seqモデルを対話モデルの構築に使って検証を行った。
既存の対話モデルは特定のドメインに応じて個別のルールの作成が必要だが、Seq2Seqならデータを集めるだけでよい。
Sutskever et al. (2014)のモデルで出力系列を入力系列の文に対する返答の文として学習をする。
ITヘルプデスクと映画のセリフのデータセットで学習を行い、結果の例示によって学習がうまくいっていること、人間による評価によって先行研究の手法と比べても自然な対話が出来ていることを主張している。

### Xu et al. [Show, attend and tell: Neural image caption generation with visual attention](http://www.jmlr.org/proceedings/papers/v37/xuc15.pdf) ICLR 2015

Attentionを使って画像からキャプションを生成する手法を提案。
画像の低次元特徴量のマップとLSTMの前の隠れ状態からattentionを作り、contextを計算してLSTMに渡している。
Softとhardの二通りのattentionを提案しており、softはナイーブな重み付き和で、hardはattentionにカテゴリカル分布を置いてREINFORCEを使って最適化している。
Flickr8k、Flickr30k、COCOの3つのデータセットで生成文のBLUEによる評価でSoTAの性能を示した。
Softの方がAttentionの見た目はいいが、Hardの方がBLUEは良い。

### Sukhbaatar et al. [End-To-End Memory Networks](https://arxiv.org/pdf/1503.08895v5.pdf) NIPS 2015

- https://github.com/vinhkhuc/MemN2N-babi-python

### Yao et al. [Attention with Intention for a Neural Network Conversation Model](https://arxiv.org/pdf/1510.08565v3.pdf) NIPSWS 2015

### Luong et al. [Addressing the Rare Word Problem in Neural Machine Translation](https://arxiv.org/pdf/1410.8206.pdf)

NMTのOOVの問題にナイーブな前後処理を加えて対応する手法を提案した。
NMTではEmbeddingする次元に制限があり、固有名詞などボキャブラリに入り切らない単語が問題になる。
翻訳元と翻訳先の単語間のアラインメントを事前に教師なしで学習し、NMTは入力するUNKトークンにアラインメント情報を加えて学習をさせる。
最後にアラインメントに応じてUNKの対応に応じて適切な単語を置き換える。
頻出頻度の低い文で確かに性能が向上されており、全体としての性能自体もWMT14英仏でBLUEを評価した結果当時のSoTA(37.8)。


### Jean e al. [On Using Very Large Target Vocabulary for Neural Machine Translation](https://arxiv.org/pdf/1412.2007.pdf) ACL 2015

NMTではボキャブラリサイズを大きく出来ない問題に対して、それにImportance samplingをして対処するという論文。
NMTのボキャブラリーサイズが大きいと最後のsoftmaxの正規化をするときに計算量が多くなってしまうのと、デコーディングが効率的に出来ないので、ボキャブラリのサイズを大きくしづらい。
そこで、勾配の期待値計算をImportance samplingを使うことで計算を速くする手法を提案。デコーディング時も翻訳元の文に合せて候補トークンリストを作り、ボキャブラリを絞ってデコードをする。
WMT'14の英仏・英独データセットを使ってBLEUで評価し、アンサンブルすればSoTAと遜色ないという主張。


## 2016

### Li et al. [Deep Reinforcement Learning for Dialogue Generation](https://arxiv.org/pdf/1606.01541.pdf) EMNLP 2016

対話文の生成タスクを２つのエージェントに対話をさせていると見立てて方策勾配法で解いた論文。
MLEでの最適化だと"I don't know"のように単純に頻度が高い返答を返しがちだったり、同じ返答を繰り返したり無限ループにハマったりしてしまうことが多い。
そこで、ユーザが設計した対話に適した報酬を最適化でき、かつ長期の影響を考慮できるように強化学習を用いる。
状態は直前の２つの会話文、行動は次に返答する会話文と定義し、報酬は(1) 返答のしやすさ、(2) 新しい情報を返しているか、(3) 文の流れが妥当か、を組み込んでヒューリスティックに作っている。
２つのエージェントで対話を生成していきREINFORCEで最適化をしている。カリキュラム学習的に学習する対話の回数を少しずつ増やしていっている。
対話の続いた長さや多様性を測って定量的に評価している。あとは実際に対話例を明示して有用性（対話が続きそう、多様）を示している。

### Yuan and Briscoe [Grammatical error correction using neural machine translation](https://www.aclweb.org/anthology/N/N16/N16-1042.pdf) NAACL-HLT 2016

GECタスクにNMTを初めて使ったという論文。
OOVの問題がGECタスクではより顕著になるので、これについてもLuong et al. (2015)のアラインメントベースの手法を踏まえたより簡潔な解決方法を提案している。
恐らくNMTのUNK入りアウトプットにアラインメントをかけて、単語レベルの翻訳をするだけだと思われる。
FCEとCoNLL2014のデータセットにおいてGLEU, I-measure, M2スコアで評価。CoNLL2014のM2スコアが39.90でSoTA（当時）という主張。
イントロの例でむやみにUNKトークンに変えると意味を踏まえた識別が出来ないという前フリが解決出来てない気がするが...

### Chollampatt et al. [Neural Network Translation Models for Grammatical Error Correction](https://arxiv.org/pdf/1606.00189.pdf) IJCAI 2016

### Xie et al. [Neural Language Correction with Character-Based Attention](https://arxiv.org/pdf/1603.09727.pdf) arXiv:1603.09727 2016

GECタスクに文字ベースのNMTを使ったという論文。
GECではOOVの問題がさらに顕著なので、そもそも文字ベースのNMTを使うという話。
系列が長くなりすぎるので双方向GRUをピラミッド型に積んだエンコーダを使っている。
CoNLL2014のデータでM2スコアで40.56でSoTA（当時）という主張。
ただし、結局一緒に外部データで学習した言語モデルを使ったり、人工的にトレーニングデータの誤りを増やしたり、誤り訂正を適用するかどうかのモデルを用意したりと単体では精度が出ない印象。

### Mou et al. [Sequence to Backward and Forward Sequences: A Content-Introducing Approach to Generative Short-Text Conversation](https://arxiv.org/pdf/1607.00970v2.pdf) COLING 2016

### Ranzato et al. [Sequence level training with recurrent neural networks](https://arxiv.org/pdf/1511.06732v7.pdf) ICLR 2016

言語モデルなどにおけるRNNによる文の予測では、トレーニング/テスト時の最適化と予測の基準の乖離が生じる。
これを解決するため、REINFORCEを使ったMIXERという手法を提案した。
RNNベースの言語モデルの予測は、学習時は真の系列で条件付けて次のトークンの尤度を計算するが、学習時は自身の予測系列に条件付けて次トークンの予測を行うので、トレーニング時とテスト時の乖離が激しい。また、BLEUのようなテスト時の指標をきちんと最適化出来ていないという二つの問題がある。
RNNによる予測を確率的な方策だとして、文の最後まで予測をしたらBLUE等のスコアによって報酬を与えることで強化学習の問題に落とし、REINFORCEで解いている。
強化学習の問題としては行動空間が大きすぎるので、クロスエントロピー誤差も組み合わせることにより解決するMIXERを提案。
具体的には、最初の方のepochはクロスエントロピー誤差だけでトレーニングし、その後で段々とREINFORCEで学習するトークン数を後ろから前に広げていく。
最近の手法も含めた他のベースラインと要約、翻訳、キャプション生成のタスクでBLUEにおいて比較し、優位性を実験的に示した。

- [github.com/facebookresearch/MIXER](https://github.com/facebookresearch/MIXER)

### Bahdanau et al. [An Actor-Critic Algorithm for Sequence Prediction](https://arxiv.org/pdf/1607.07086v2.pdf) ICLR 2017

Seq2Seqの学習にactor-criticを使うことで、自らのそれまでの予測で条件付けながら、テスト時の指標（BLUE等）を直接最適化するように学習する手法を提案した。
Ranzato et al. (2016)で提案されたREINFORCEを使ったMIXERの発展と見なすことができる。
REINFORCEベースの手法は勾配の分散が大きくなってしまうので、actor-criticにして行動価値関数も推定することで分散を減らして性能の向上をさせたい。
先行研究と同じようにDecoderを確率的な方策と見なし、各トークンを予測したときにBLUE等から報酬を定めて強化学習の枠組みに落とし込み、actor-criticで解いている。
また、大きい行動空間を制限するためのヒューリスティックな工夫や、報酬がスパースになるのを避けるため部分系列にも報酬を定義するなどの工夫もしている。
独英翻訳のデータセットにおいて、MIXERと比べBLUEが改善されていることを実験的に示した。

- [github.com/rizar/actor-critic-public](https://github.com/rizar/actor-critic-public)

### Tu et al. [Neural Machine Translation with Reconstruction](https://arxiv.org/pdf/1611.01874v1.pdf) arXiv:1611.01874 2016

### Kalchbrenner et al. [Neural Machine Translation in Linear Time](https://arxiv.org/pdf/1610.10099v1.pdf) arXiv:1610.10099 2016

### Kočiský et al. [Semantic Parsing with Semi-Supervised Sequential Autoencoders](https://arxiv.org/pdf/1609.09315v1.pdf) arXiv:1609.09315 2016

### Gu et al. [Incorporating Copying Mechanism in Sequence-to-Sequence Learning](http://aclweb.org/anthology/P/P16/P16-1154.pdf) ACL 2016

OOVな単語でも、翻訳元の文中にあれば出力出来るCopyNetを提案。
対話タスクなどでは人名などを繰り返すことがあるが、これに対応する狙いがある。
デコーダーの出力をボキャブラリーに加えて翻訳元の文からも出力できるようにして、End-to-Endで学習をしている。
人工データにおける評価と、LCSTSデータセットで要約タスクにおけるROUGEスコアでの評価、DS-1, DS-2データセットで対話タスクの評価を行った。
ナイーブではあるが、実データはどちらも翻訳元の内容を繰り返すのが重要なタスクなので、スコアは随分改善されているようにみえる。

- [関連資料]( http://www.lr.pi.titech.ac.jp/~sasano/acl2016suzukake/slides/08.pdf)

### Park et al. [Attentive Explanations: Justifying Decisions and Pointing to the Evidence](https://arxiv.org/pdf/1612.04757v1.pdf) arXiv:1612.04757 2016

### Dauphin et al. [Language Modeling with Gated Convolutional Networks](https://arxiv.org/pdf/1612.08083v1.pdf) arXiv 2016

### Lu et al. [Knowing When to Look: Adaptive Attention via A Visual Sentinel for Image Captioning](https://arxiv.org/pdf/1612.01887v1.pdf) arXiv:1612.01887 2016

### Bhoopchand et al. [Learning Python Code Suggestion with a Sparse Pointer Network](https://arxiv.org/pdf/1611.08307v1.pdf) arXiv:1611.08307 (ICLR2017 under review) 2016

- https://github.com/uclmr/pycodesuggest

### Wu et al. [Google's Neural Machine Translation System: Bridging the Gap between Human and Machine Translation](https://arxiv.org/pdf/1609.08144v2.pdf) arXiv:1609.08144 2016

### Johnson et al. [Google’s Multilingual Neural Machine Translation System: Enabling Zero-Shot Translation](https://arxiv.org/pdf/1611.04558v1.pdf) arXiv:1611.04558v1 2016

### Locascio et al. [Neural Generation of Regular Expressions from Natural Language with Minimal Domain Knowledge](https://arxiv.org/pdf/1608.03000v1.pdf) arXiv:1608.03000 2016

### Yin et al. [Neural Generative Question Answering](https://arxiv.org/pdf/1512.01337v4.pdf) arXiv:1512.01337 2016

### Serban et al. [Multiresolution Recurrent Neural Networks: An Application to Dialogue Response Generation](https://arxiv.org/pdf/1606.00776v2.pdf) arXiv:1606.00776 2016

- http://qiita.com/icoxfog417/items/b7dbacc2b5a3bf89d53e

## 2017

### Zhai et al. [Neural Models for Sequence Chunking](https://arxiv.org/pdf/1701.04027v1.pdf) AAAI 2017

### Kuncoro et al. [What Do Recurrent Neural Network Grammars Learn About Syntax](https://arxiv.org/pdf/1611.05774v1.pdf) EACL 2017

### Li et al. [Understanding Neural Networks through Representation Erasure](https://arxiv.org/pdf/1612.08220.pdf) arXiv:1612.08220 2017
