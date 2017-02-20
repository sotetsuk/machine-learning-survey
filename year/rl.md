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

### Wang et al. [Sample Efficient Actor-Critic with Experience Replay](https://arxiv.org/pdf/1611.01224v1.pdf) arXiv:1611.01224 (ICLR2017 under review) 2016

### O'Donoghue et al. [PGQ: Combining policy gradient and Q-learning](https://arxiv.org/abs/1611.01626) arXiv:1611.01626 (ICLR2017 under review) 2016
