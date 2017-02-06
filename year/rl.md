# Reinforcement Learning
強化学習の論文を列挙する。
目標は2010年頃以降のものについては主要な国際会議の論文を全部網羅すること。
また2010年以前の著名な論文も網羅したい。
理論寄りの論文を中心にしたいが、応用だけの論文もひとまずここにまとめる。
コメントは[この方針](https://github.com/sotetsuk/machine-learning-survey/tree/renewal#年代毎-1)に従って付けられている。

## 1999

### Sutton et al. [Policy Gradient Methods for Reinforcement Learning with Function Approximation](https://webdocs.cs.ualberta.ca/~sutton/papers/SMSM-NIPS99.pdf) NIPS 1999

## 2013

### Levine and Koltun [Guided Policy Search](https://graphics.stanford.edu/projects/gpspaper/gps_full.pdf) ICML 2013

- https://www.youtube.com/watch?v=xMHjkZBvnfU

## 2016

### Mnih et al. [Asynchronous Methods for Deep Reinforcement Learning](https://arxiv.org/pdf/1602.01783v2.pdf) ICLR 2016

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
