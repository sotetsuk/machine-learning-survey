# Reinforcement Learning

## Classical (Pavlovian) Conditioning
Schultz et al., 1997とPan et al., 2005についてスライドにまとめた: [強化学習勉強会・論文紹介](http://www.slideshare.net/sotetsukoyamada/22-62639753)

### 関連する脳部位

- Midbrain (中脳)
  - VTA (ventral tegmental area; 腹側被蓋野)
  - SN (substantia nigra; 黒質)

> Dopamine neurons of the ventral tegmental area (VTA) and substantia nigra have long been identified with the processing of rewarding stimuli. [cited from Schultz et al., 1997]

#### Midbrain dopamine (DA) cell

DA cellの活動はclassical learningをみせる

> Midbrain dopamine (DA) cells play a central role in rewardmediated learning in animals, and their activity follows classical learning rules (Schultz, 1998, 2002; Waelti et al., 2001) [cited from Pan et al., 2005]

TD学習が行われているのではないかという説がSchultz et al., 1997などで主張されている

> Furthermore, several features of DA cell activity match properties of the prediction error signal of the temporal difference (TD) algorithm for machine learning, leading to the hypothesis that DA cell activity may be providing a teaching signal within a neural analog of a TD learning system in the brain (Houk et al., 1995; Montague et al., 1996; Schultz et al., 1997; Daw et al., 2003; Nakahara et al., 2004). [cited from Pan et al., 2005]

### 文献
- Dayan and Abbott, 2001, [Theoretical Neuroscience](http://cns-classes.bu.edu/cn510/Papers/Theoretical%20Neuroscience%20Computational%20and%20Mathematical%20Modeling%20of%20Neural%20Systems%20-%20%20Peter%20Dayan,%20L.%20F.%20Abbott.pdf)
- Samejima and Doya 2001, [強化学習と大脳基底核(pdf)](http://ci.nii.ac.jp/els/110001096714.pdf?id=ART0001257939&type=pdf&lang=jp&host=cinii&order_no=&ppv_type=0&lang_sw=&no=1464335228&cp=)
- Schultz et al., 1997, [A neural substrate of prediction and reward](Schultz+1997.md)
  - 有名なscienceの論文
- Schultz, 1998 [Predictive reward signal of dopamine neurons](Schultz1998.md)
- Pan et al., 2005, [Dopamine Cells Respond to Predicted Events during Classical Conditioning: Evidence for Eligibility Traces in the Reward-Learning Network](Pan+2005.md)

# DQN

[Guest Post (Part I): Demystifying Deep Reinforcement Learning](https://www.nervanasys.com/demystifying-deep-reinforcement-learning/)（解説ブログ）