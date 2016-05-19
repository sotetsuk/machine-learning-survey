# 1. 神嶌先生の文献から

## 特徴ベース・分離型
神嶌先生の文献から引用

> [Daume 07] ´ は非常に簡便な帰納転移学習用の方法を提案している．入力特徴ベクトルや 0 ベクトルを連結して，共通，目標ドメイン，元ドメインに対応した三つの部分で構成される，元の 3 倍の長さのベクトルを生成する．具体的に，目標ドメインの事例 (x(T),y(T)) は，(〈x(T),0,x(T)〉,y(T)) に，元ドメインの事例 (x(S),y(S))は，(〈x(S),x(S),0〉,y(S)) に変換したのち，通常の分類問題として解く．すると，両ドメインに共通して利用される特徴は，三つのうちで，両ドメインで特徴が共通している最初の部分が分類規則で利用される．一方，両ドメインで働きが異なる特徴は，一方のドメインの値が 0になっていて両ドメインで異なっている残りの部分が自然に利用されるようになる．

## 特徴ベース・統合型
神嶌先生の文献から引用

> Caruana の [Caruana 97] は，複数のタスクを共通の中間層で学習するニューラルネット（特徴ベース・統合型）を，いくつかの帰納転移学習問題に適用し，転移学習について論考した，この時点以前の研究を俯瞰した論文であり，一読されることを薦める．

## 事例ベース・分離型
神嶌先生の文献から引用

> 単独では予測精度の低い弱分類器を組み合わせて予測性能を向上させるアンサンブル学習に基づく方法を幾つか示す．これらは，弱学習器として通常の学習器を用いるため，分離型である．

> 代表的なブースティングである AdaBoost [Freund 96,フロインド 99] を，帰納転移学習問題に拡張したのがTrAdaBoost [Dai 07b] である．通常のブースティングでは訓練事例を重み付けし，弱学習器はこの重みを反映した誤差を最小化するように学習する．その弱分類器に事例を分類させて，分類を誤った，すなわち苦手な事例を重視するように，事例の重みを更新する．このように学習した弱分類器の予測を，分類誤差に応じて凝集することで，最終的な予測結果を得る．TrAdaBoost では，苦手な目標ドメインのデータの重みを増やす点は同じだが，誤って分類した元ドメインデータは目標問題への関連が弱いとみなして，その重みを下げる．

# 2. Multimodal Deep Learning
ICML2011

AudioとVideoのマルチモーダル学習を提案。共通レイヤを持つAEを学習して識別に応用。

<img width="300" alt="2016-04-15 11 18 35" src="https://cloud.githubusercontent.com/assets/5868442/14549576/d4fc48c8-02fb-11e6-9714-f46aa725df1a.png">

論文より図を引用

# Curriculum Learning
Bengio et al., 2009

入力を簡単なものに最初は限定することで良い局所解を得ておいて、そこから学習を始める。

<img width="300" alt="2016-04-15 11 51 55" src="https://cloud.githubusercontent.com/assets/5868442/14550063/85814c44-0300-11e6-81f3-8c7ad6a2453f.png">

論文より図を引用

# Transfer Learning in Collaborative Filtering for Sparsity Reduction
AAAI2013

ユーザ、アイテムの双方についてよりリッチなドメインがあるときに、それらを使って転移学習をする。
Coordinate System Transfer(CST)という手法を提案。SoTAを達成。

<img width="300" alt="2016-04-15 13 32 12" src="https://cloud.githubusercontent.com/assets/5868442/14551464/7e72dd7e-030e-11e6-9ba3-7c09b580c330.png">

論文より図を引用

手法の発想は極めてシンプルで、上記R(1), R(2)というより情報がリッチな行列でそれぞれSVDをして、
基底行列をとってきてそれに近くなるよう正則化をかけてRをSVDする。

# 文献

- [転移学習](http://www.kamishima.net/archive/2010-s-jsai_tl.pdf) by 神嶌先生
- [転移学習のサーベイ](http://www.kamishima.net/archive/2009-tr-jsai_dmsm1-PR.pdf) by 神嶌先生
- [Multimodal Deep Laarning](http://machinelearning.wustl.edu/mlpapers/paper_files/ICML2011Ngiam_399.pdf)
- [Curriculum Learning](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=C9AC00EA19D0E3819C2F9C57C4D6C9E2?doi=10.1.1.149.4701&rep=rep1&type=pdf)
- [Transfer Learning in Collaborative Filtering for Sparsity Reduction](http://www.aaai.org/ocs/index.php/AAAI/AAAI10/paper/viewFile/1649/1963/)
