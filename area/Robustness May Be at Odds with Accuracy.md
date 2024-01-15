---
created-at: 2023-11-21T22:52
tags: 
description:
---
# Note: Robustness May Be at Odds with Accuracy

References
- [[paper-Robustness May Be at Odds with Accuracy|Robustness may be at odds with accuracy]]

## Abstract
Robust model의 훈련은 자원을 소비할뿐만 아니라 accuracy에도 영향을 미친다. 단순한 상황에서 accuracy와 robustness 사이의 trade-off가 'provably' 있다는 것을 보인다. 또한 robust model이 인간이 인지하는 형태와 비슷한 특징을 배운다는 점을 보인다.
## 1 Introduction
- 딥러닝은 인상적인 발전을 이루었지만, 작은 공격에 취약하다는 점이 밝혀졌다.
- 다양한 adversarial example에 대한 훈련이 진행됐다.
- 이 training들은 비용이 많이 든다.
- 이 비용을 전부인가? 그렇다면, 비용을 내고 robust model을 갖는 것이 항상 이득인가?
- ==모델이 adversarially robust trained 됐을지라도, 보편적으로는 Standard accuracy와 adversarially robust accuracy 사이의 trade-off가 존재한다.== 그리고 우리는 단순한 상황에서 이 trade-off가 'provably' 존재한다는 것을 보여준다.
## 2 On the Price of Adversarial Robustness
- Data의 perturbation은 data augmentation의 궁극적인 형태로 볼 수 있다고 생각했다.
- Worst case $\delta$를 찾는 것은 training data를 가장 헷갈리는 방법으로, 즉 가장 도움이 되는 방법으로 도와주는 것이기 때문이다.
- 하지만 실제로는 perturbation이 늘어남에 따라 standard accuracy가 감소하고, 심지어 일정 이후에는 학습 도중 내려가는 모습을 볼 수 있다.
### 2.1 Adversarial robustness might be incompatible with standard accuracy
- u.a.r: uniformly at random
$$
\begin{aligned}
& y \sim^{u.a.r} \{-1, +1\} \\
& x_1  =
  \begin{cases}
    +y &w.p. p \\
    -y &w.p. 1 - p
  \end{cases} \\
& x_2, \cdots, x_{d+1} \sim^{i.i.d} N(\eta y, 1)\\
\end{aligned}
$$
- $x_1$: moderately correlated (robust feature)
- $x_2, \cdots, x_{d+1}$: weakly correlated (non-robust feature)

- Classifier는 간단하게 정확도를 높일 수 있다.

$$f_{avg}(x) := sign(w_{unif}^Tx) \text{, where } w_{unif} := [0, \frac{1}{d}, \cdots, \frac{1}{d}]$$
- $\eta \ge \frac{3}{\sqrt{d}}$일 경우(충분히 클 경우) 다음 확률은 99%를 넘는다.
$$P[f_{avg}(x) = y] = P[sign(w_{unif}^Tx) = y] = P[\frac{y}{d} \sum N(\eta y, 1) > 0] = P[N(\eta, \frac{1}{d}) > 0]$$
- 하지만, 해당 non-robust feature는 $\varepsilon \ge 2\eta$일 경우 class가 바뀌게 된다.
$$\min_{||\delta||_\infty \le \varepsilon} P[sign(x + \delta) = y] \le P[N(\eta, \frac{1}{d}) - \varepsilon > 0] = P[N(-\eta, \frac{1}{d}) > 0]$$
- 만약 w가 non-robust feature에 의존했다면, adversarial accuracy는 1%를 넘지 못한다.

- Q1. 만약 dataset이 무한하다면 해결할 수 있지 않나?
- A1. 위 유도는 부족한 dataset이 아닌 non-robust feature를 가진 dataset에 대한 주장이기 때문에 그렇지 않다.
- Q2. Standard dataset에 대한 완벽한 robust/accurate classifier(e.g. 인간)는 만들 수 없는건가?
- A2. 인간또한 특정 벤치마크에 대해 모델보다 더 낮은 벤치마크를 기록하곤 한다. (ref. 94%)

### 2.2 The importance of adversarial training
- Classifier가 합리적으로 standart accuracy와 robust accuracy를 높이는 접근을 위해선 학습 방법이 달라져야 한다.

## 3 Unexpected benefits of adversarial robustness
- Robust model의 loss gradients이 인간의 인지에 대응한다.
- Adversarial example이 salient data characteristics를 가지고 있다.
- Large $\varepsilon$으로 gradient based attack(PGD)을 하니 attack이 인간 눈에 대응되는 특징을 만들어 공격하는 것을 볼 수 있었다.
## 4 Related work
- Classifier의 robustness의 upper bound를 증명하는 연구가 있다.
	- Fawzi et al., 2018, Analysis of classifiers' robustness to adversarial perturbation
	- Ross & Doshi-Velez, 2018, Improving the adversarial robustness interpretability of deep neural networks by regularizing their input gradients
	- Schmidt et al., Adversarially robust generalization requires more data
## 5 Conclusions and future directions
- 두 접근의 상대적인 비용에 관해 완전한 이해가 될 수 있는 계기가 되었으면 한다.