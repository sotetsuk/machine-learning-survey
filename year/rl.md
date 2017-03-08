# Reinforcement Learning
強化学習の論文を列挙する。
目標は2010年頃以降のものについては主要な国際会議の論文を全部網羅すること。
また2010年以前の著名な論文も網羅したい。
理論寄りの論文を中心にしたいが、応用だけの論文もひとまずここにまとめる。
コメントは[この方針](https://github.com/sotetsuk/machine-learning-survey/tree/renewal#年代毎-1)に従って付けられている。

## 1998

### Claus and Boutilier [The Dynamics of Reinforcement Learning in Cooperative Multiagent Systems](http://www.aaai.org/Papers/AAAI/1998/AAAI98-106.pdf) AAAI 1998

協調ゲーム（エージェントの利害が互いに一致するゲーム）を解くマルチエージェントシステムに強化学習を使った論文。エージェントはナッシュ均衡が複数あるようなゲームを何回も繰り返す中で、その最適な方策を学習しようとする。エージェントが自分の行動の方策だけ考えるエージェント (IL; Independent learner) と、他のエージェントの方策についても分布を想定して自分の方策を決めるエージェント (JAL; Joint-action learner) を実験的に比較し、どちらも純粋戦略のナッシュ均衡（最適とは限らない）へ確率1で収束することを定理として述べている（証明はない）。また、楽観的な戦略（普通の楽観的とは違い、他のエージェントの方策が自分にとって都合が良いものが選ばれると思い込む戦略）を混ぜることで最適戦略に収束しやすくなると主張している。

## 1999

### Sutton et al. [Policy Gradient Methods for Reinforcement Learning with Function Approximation](https://webdocs.cs.ualberta.ca/~sutton/papers/SMSM-NIPS99.pdf) NIPS 1999

## 2012

### Xie et al. [Artist Agent: A Reinforcement Learning Approach to Automatic Stroke Generation in Oriental Ink Painting](https://arxiv.org/pdf/1206.4634.pdf) ICML 2012

筆絵を書く筆エージェントを連続空間における方策勾配法で学習した研究。
指定された領域に対して滑らかに筆を滑らせるのは領域の形が変わったときに汎化させるのが難しい。
そこで、これまで通ってきた軌跡から相対的にどちらに筆を動かすのかの角度を連続な行動として、方策をガウシアンとして平均と標準偏差でパラメトライズして方策勾配法で学習をする。
即時報酬を、指定された領域をきちんと塗れているか、滑らかに動けているかといった観点で細かく設計している。
実際に筆絵を描いて定性的な評価を行っている。人間が線を引く領域を作ってやる必要があるので論文中の細かい絵などは中々大変そうである。

- IEICEのジャーナル版: http://www.ms.k.u-tokyo.ac.jp/2013/ArtistAgent.pdf

## 2013

### Levine and Koltun [Guided Policy Search](https://graphics.stanford.edu/projects/gpspaper/gps_full.pdf) ICML 2013

- https://www.youtube.com/watch?v=xMHjkZBvnfU

## 2016

### Wang et al. [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/pdf/1511.06581.pdf) ICML 2016

DQNにおいて、状態を入力として行動毎の行動価値Qをいきなり出力するのではなく、その前に状態価値V（スカラー）と行動毎のアドバンテージAを出力するDNNアーキテクチャを提案。
状態における価値を求めるのと、その状態でどう行動するのがいいかは別の話なので別々に学習したほうがいい場面も当然ある。
特にどの行動をとっても同じような価値しか得られない場合、そこは状態価値関数に縮約した方が自然である。
ネットワークは状態価値とアドバンテージを別々に出力して、それらから行動価値を出力するので、既存の（あるいはこれからの）DQNの資産を活用できる。
57個のAtariのゲームでこの時点でSoTAを達成。

### Mnih et al. [Asynchronous Methods for Deep Reinforcement Learning](https://arxiv.org/pdf/1602.01783v2.pdf) ICML 2016

CPUでの並列スレッド実行により、GPUで学習したDQNより学習が早く、性能もいいアルゴリズムA3C (Asynchronous Advantage Actor-Critic) を提案した。
DQNは本質的に体験再生を使った方策オフ型の学習なので、複数ステップ版のQ学習のような方策オン型のアルゴリズムの学習が出来ない。
これは状態と行動の組(s, a)においての推定が少しずつ伝搬していく必要があり、タスクによっては学習が遅くなってしまう。
そこで、体験再生の代わりに複数スレッドで環境とインタラクションして方策オンのサンプルを生成し、
それに基づいたパラメータの勾配によってグローバルなモデルのパラメータを更新することで、Deepなモデルが方策オンでも学習できるアルゴリズムを実装した。
A3CはAtariにおいて学習が早く、SoTAの性能を叩き出すという結果。また、行動空間が連続のタスク（MuJoCoなど）でもうまくいくことをデモしている。
A3Cでは明示的にQ関数を学習する必要がなくなり、方策にLSTMを使えたり、連続空間のタスクにも使えるのも大きなメリットか。

- [github.com/openai/universe-starter-agent](https://github.com/openai/universe-starter-agent)
- [github.com/miyosuda/async_deep_reinforce](https://github.com/miyosuda/async_deep_reinforce)
- [github.com/muupan/async-rl](https://github.com/muupan/async-rl)

### Schaul et al. [Prioritized Experience Replay](https://arxiv.org/pdf/1511.05952v4.pdf) ICLR 2016

### Tamar et al. [Value Iteration Networks](https://arxiv.org/pdf/1602.02867v2.pdf) NIPS 2016
汎用的なプランニングが出来る価値反復アルゴリズムを提案したという話。
昨今の深層学習と強化学習を組み合わせた話の主流は完全なモデルフリーの話だが、
これはモデル（遷移確率カーネルと即時報酬関数）について明示的に学習していないので、新しい別の（似た）MDPに汎化できない（新しい迷路を解けない）。
そこで、モデルをCNNで汎化させて未知のMDPに対してもプランニングが出来るアルゴリズムを考えたい。
（これは新しいモデルについて具体的なモデルを最初に学習して解く必要があるモデルベースの手法とは違う（例えばE3とかは新しいMDP毎に探索をする））
具体的には、end-to-endで（プランニングから価値反復まで）学習できるVIN (Value Iteration Network) を、即時報酬関数を学習するCNNや、方策を学習するCNNを連結させて実装した。
CNNを使ったモデルフリーな手法が解き切れない新しい迷路などのタスクがしっかり解けていることを実験で示した。
価値反復の部分をCNNを何回に突っ込むことで実現しているのが面白い。

### Kulkarni et al. [Hierarchical Deep Reinforcement Learning: Integrating Temporal Abstraction and Intrinsic Motivation](https://arxiv.org/pdf/1604.06057v2.pdf) NIPS 2016

### Bellemare et al. [Unifying Count-Based Exploration and Intrinsic Motivation](https://arxiv.org/pdf/1606.01868v2.pdf) NIPS 2016

### Munos et al. [Safe and Efficient Off-Policy Reinforcement Learning](https://arxiv.org/pdf/1606.02647v2.pdf) NIPS 2016

## 2017

### Wang et al. [Sample Efficient Actor-Critic with Experience Replay](https://arxiv.org/pdf/1611.01224.pdf) ICLR 2017

### O'Donoghue et al. [PGQ: Combining policy gradient and Q-learning](https://arxiv.org/abs/1611.01626) ICLR 2017

エントロピー正則化付きの方策勾配法とQ学習の不動点の関係について新しい知見を見出し、それを使って方策勾配法とQ学習を組み合わせた新しいアルゴリズムPGQを提案した。
背景には、方策勾配法は基本的にオンラインでオフラインのデータの活用が出来ないのでそれを活用できるようにしたいというモチベーションがある（これはACER等と同じ）。
PGQは、Actor-Criticの更新則に、方策と状態の価値関数から計算される行動価値関数にQ学習を適用する項をηで重み付けして追加する。
学習される行動価値関数が最適へと収束することの証明に加え、AtariでDQNとA3Cと比較をした結果、PGQが一番悪いゲームはなかった（つまり常に1位か2位）。

##### 示している・示唆していること
- 3.1, 3.2: エントロピー正則化付きの方策勾配法は、アドバンテージを学習していると見なすことが出来る（のでこれを使えばQ関数を表現できる）
- 3.3: Action-preferenceで表現した方策を使うactor-critic（方策勾配法）と、dueling architectureとボルツマン方策を使った価値関数ベースの手法（Q学習やSARSA）が更新則として等しい
- 4.3: PGQの更新則が最適価値関数を導く

### Nachum et al. [Bridging the Gap Between Value and Policy Based Reinforcement Learning](https://arxiv.org/pdf/1702.08892.pdf) ICML under review 2017

割引付きのエントロピー正則化項が追加された目的関数O_entを最適化する（ことになる）アルゴリズム、PCLを提案。
背景には方策オンと方策オフの一長一短を解決したいというのがある。これは方策オフの複数ステップへの延長路線。
まず、最適ベルマン作用素を特殊ケースとして含む新しいベルマン作用素を提案 (softmax Bellman opperator) し、
これの不動点であるsoftmax-vとO_entの最適方策が、方策オンのサンプルの軌跡に対して満たすべき関係式を導いている。
そしてこの関係式を満たすように方策と状態価値関数を更新する。また軌跡をリプレイバッファに入れることで方策オフ的な学習効率の改善もしている。
複数ステップの方策オフ型学習をしていることになるが、バイアスがないのが大きな特徴か。

##### 定義・提案しているもの
- Softmaxベルマン方程式・作用素（式4, 54）とそれらの不動点としてのsoftmax-Vとsoftmax-Q（式13, 14）
- 3.2: 割引付きのエントロピー正則化項（とそれを通常の累積割引報酬和の期待値に足した目的関数O_ent（式15））

##### 示しているもの
O_entの最適方策とsoftmax-V(Q)の間には定理1と補題3の関係が成り立つ

- 定理1: O_entについての最適方策とsoftmax-Vが式16の関係式を満たす
  - 別々に定義されたO_ent（の最適方策）とsoftmax-Vがここで繋がる
  - 式16はsoftmaxベルマン作用素の不動点が満たすべき関係式のようなもの（？）
  - 通常の最適ベルマン作用素と比べるとTD誤差がゼロになるのではなく、O_entの最適方策のlogになる
- 補題2: O_entの最適方策がsoftamxアドバンテージ関数（softmax-Qとsoftmax-V）を使って表せる
- 補題3: O_ent, O_entの最適方策、softmax-Vが与えられたとき、これらは軌跡s1:tについてある関係式を満たす（必要がある）
  - 式16の等式を帰納的に軌跡s1:tに適用していくことで導かれる等式
  - 恐らく式(16)が1ステップのベルマン方程式に対応し、これが複数ステップのベルマン方程式に対応している（？）
  - O_entの最適方策とsoftmax-Vがこの関係を軌跡s1:tについて満たさなければならないので、これを満たすものを学習しようというのがPCLの発想
- 定理4: ある方策と価値関数Vが任意のサンプル(s, a, s')で式(16)を満たせば、それらはそれぞれO_entの最適方策とsoftmax-Vになる
  - つまり、任意のサンプルで式(16)を満たすように学習していけば、これがO_entの最適方策とsoftmax-Vが求まる根拠になる
