---
created-at: 2024-01-24T13:06
tags: 
description:
---
# DISCO: Adversrial defense with local implicit functions

## Abstract
- We propose to remove adversarial perturbations by localized manifold projections
- It outperforms prior defenses, regardless of whether the defense is know to the attacker

## 3 Method
### 3.1 Motivation
- DNN을 이용한 implicit function이 realistic image나 3d shape의 분포를 기억하고 합성할 수 있다.
- DISCO는 합성된 이미지가 manifold thickening을 위해 사용될 수 있다고 말한다.
### 3.2 Model architecture and training
- (H * W * 3)  크기의 adversarial image가 들어오면 encoder E가 (H * W * C) 크기의 feature map을 만든다. 이후 MLP implicit module L이 특정 위치 좌표를 input으로 받으면 feature map의 특정 위치 좌표 주변의 feature map을 추출하여 해당 좌표의 픽셀을 복원한다. 이들을 합성해 (H' * W' * 3) 크기의 복원된 이미지가 만들어진다.

### 3.3 Inference
- Classifier, attack, dataset의 종류가 달라져도 유연하게 성능을 내는 모습을 보였다.

### 3.4 DISCO cascades
- 모든 dataset에 대해 image를 만드는 adversarial training보다 효율적이다.
- Classifier에 의존하지 않고 학습을 진행할 수 있어 효율적이다.

## 4 Experiments


## 5 Discussion, societal impact and limitations
- Limitations: 더 다양한 attack, dataset, 방법론에 대해서 실험이 필요하다.
- Societal impact: local implicit function을 사용하는 것이 의의가 있다.

## 참조
- Chih-Hui Ho et al., (2022), DISCO: Adversarial Defense with Local Implicit Functions, NeurIPS 2022