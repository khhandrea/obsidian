---
created-at: 2024-01-24T11:28
tags: 
description:
---
# Bilateral adversarial training

## Abstract
- We propose to perturb both the image and the label during training

## 1. Introduciton
- We propose a formulation to achieve two conditions: (1)low loss, (2)small gradient magnitude by perturbing both input images and labels during training
- We uses targeted attack to most confusing class
- We add random uniform noise to the original image
- We derive a forumla to perturb the groundtruth label

## 3. Motivation
- For adversarial robustness problem, we performed two experiments
- First experiment: PGD2-8(2 iterations and 8 step sizes, weaker attack) is largely as robust as PGD7-2(7 iterations and 2 step sizes, stronger attack) -> robustness may not be achieved by simply fitting sufficient adversarial examples. There is more essential ingredients that directly relate to network robustness.
- Second experiment: gradient magnitude of adversarially trained models is much smaller than that of undefended models -> gradient-based adversarial attacks fail with small gradient

## 4. Formulation
### 4.1. Genrating adversarial labels
- $y_c = 1$, and $y_k = 0, y \ne c$ for class index
$$
\begin{aligned}
& y_k' = \frac{\epsilon_y}{n - 1} \cdot \frac{v_k - v_{MC} + \gamma}{\frac{\sum_{k \ne c} v_k}{n - 1} - v_{MC} + \gamma}, k \ne c \\
& where \\
& v_k = \nabla_{y_k} L(x, y; \theta), \\
& v_{MC} = \min_{k \ne c} v_k, v_{LL} = \max_{k \ne c} v_k
\end{aligned}
$$

- If the gradient of non-groundtruth classes are equal, we obtain the label smoothing
$$y_k' = \frac{\epsilon_y}{n - 1}, k \ne c$$
- We find proper $\epsilon_y$ for $y_c' \ge \beta \cdot \max_{k \ne c} y_k'$
- We should consider two extreme cases; (1) the probabilities of non-groundtruth classes are evenly distributed (2) the probabilities of non-groundtruth classes are centered on one class
$$
\begin{aligned}
& (1) \epsilon_y \le \frac{1}{1 + \frac{\beta}{n - 1}} \\
& (2) \epsilon_y \ge \frac{1}{1 + \beta \frac{v_{LL} + \gamma}{v_{LL} + (n-1)\gamma}} \approx \frac{1}{1 + \beta} \\
& \therefore \epsilon_y \in (\frac{1}{1 + \beta}, \frac{1}{1 + \frac{\beta}{n - 1}}]
\end{aligned} \\
$$
### 4.2. Generating adversarial images
- One-step PGD to the most confusing(MC) class

## 참조
Jianyu Wang et al., (2019), Bilateral Adversarial Training: Towards Fast Training of More Robust Models Against Adversarial Attacks, ICCV 2019