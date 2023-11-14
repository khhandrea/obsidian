---
created-at: 2023-11-09T10:09
tags: 
description:
---
# Note: Vector-based Navigation Using Grid-Like Representations in Artificial Agents
## Abstraction
- 딥러닝이 복잡한 문제를 풀 정도로 발전했지만, 길 찾기 분제는 동물의 공간지각 능력에 밀린다.
- Grid cell은 공간의 여러 스케일에서의 지표를 제공해 path integration과 vector-based navigation 능력을 돕는다.
- 우리는 grid cell의 계산적 기능을 이용하는 DRL agent를 제안하고, 이가 낯설고 변하는 환경에서 목표를 찾는 데에 좋은 효과를 가짐을 보인다.

- place unit과 head direction unit은 매 step마다 supervised training의 형태로 제공한다.
- Agent는 path integration을 잘 했다.


## Methods
- $\vec{c}$: true place cell activations
- $\vec{h}$: true head-direction cell activations
- $\vec{y_t}$: prediction of the place cells
- $\vec{z}$: prediction of the head direction cells
- $\vec{x}$: position
- $\phi$: facing angle
- $\vec{l}$: LSTM cell state
- $\vec{m}$: LSTM hidden state
- $\vec{g}$: linear layer activations
- $g_c$: gradient clipping
- $\vec{u}$: noise in the velocity
- $\vec{v}$: velocity
- $\vec{\phi}$: visual input
- $\vec{e}$: vision embeddings

- Actions: 6 discrete actions: 회전, 앞/뒤/좌/우로 가속, 움직일 때 회전 가속

- Vision module
	- Input: RGB image
	- Output: embedded image
	- Learning: c와 h를 잘 예측하도록 학습
- Grid network
	- Input: velocity, direction
	- Embedded: grid code
	- Learning: c와 h를 잘 예측하도록 학습
- Actor learner
	- Input: current grid code, goal grid code, embedded image, last action, reward
	- Output: policy, value
	- Learning: policy loss + value loss + negative entropy loss를 줄이도록 학습
## References
| no  | reference                                                                                                                   | description                                      |
| --- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| 1   | LeCun, 2015, Deep learning                                                                                                  | 복잡한 게임, 딥러닝                              |
| 2   | Silver D, 2016, Mastering the game of Go with deep neural networks and tree search                                          | 복잡한 게임, 알파고                              |
| 3   | Oh J, 2016, active perceptron, and action in Minecraft                                                                      | navigation, minecraft에서 길 찾기                |
| 4   | Kulkarni T, 2016, Deep successor reinforcement learning                                                                     | navigation, DSR                                  |
| 5   | Mirowski P, 2017, Learning to navigate in complex environments                                                              | navigation, LSTM A3C 길 찾기                     |
| 6   | Hafting T, 2005, Microstructure of a spatial map in the entorhinal cortex                                                   | grid cell                                        |
| 7   | Fiete I, 2008, What grid cells convey about rat location                                                                    | grid cell 역할                                   |
| 8   | Mathis A, 2012, Optimal population codes for space: grid cells outperform place cells                                       | grid cell 역할                                   |
| 9   | McNaughton B L, 2006, Path integration and the neural basis of the 'cognitive map'                                          | path integration                                 |
| 10  | Erdem U M, 2012, A goal-directed spatial navigation model using forward trajectory planning based on grid cells             | vector-based navigation                          |
| 11  | Bush D, 2015, Using grid cells for navigation                                                                               | vector-based navigation                          |
| 12  | Barry C, 2014, Neural mechanisms of self-location                                                                           | self location 원리                               |
| 13  | Mittelstaedt M, Homing by path integration in a mammal                                                                      | vector-based navigation through path integration |
| 14  | Bassett J P, Neural correlates for angular head velocity in the rat dorsal tegmental nucleus                                | head direction                                   |
| 15  | Kropff E, 2015, Speed ceels in the medial entorhinal cortex                                                                 | velocity                                         |
| 16  | Srivastava N, Dropout: a simple way to prevent neural networks from overfitting                                             | dropout                                          |
| 17  | Wills T J, Development of the hippocampal cognitive map in preweanling rats                                                 | place cell, head direction cell 생성             |
| 18  | Langston R F, 2010, Development of the spatial representation system in the rat                                             | representation 생성                              |
| 19  | Zhang S J, 2013, Optogenetic dissection of entorhinal-hippocampal functional connectivity                                   | grid cell 역할                                   |
| 20  | Sargolini F, 2006, Conjunctive representation of position, direction, and velocity in entorhinal cortex                     | grid pattern 역할                                |
| 21  | Barry C, 2007, Experience-dependent rescaling of entorhinal grids                                                           | grid rescailing                                  |
| 22  | Stensola H, 2012, The entorhinal grid map is discretized                                                                    | grid rescailing                                  |
| 23  | Stemmler M, 2015, Connecting multiple spatial scales to decode the population activity of grid cells                        | grid rescailing prediction                       |
| 24  | Doeller C, 2010, Evidence for grid cells in a human memory network                                                          |   grid structure storage                                               |
| 25  | Kanitscheider, 2016, Training recurrent networks to generate hypotheses about how the brain solves hard navigation problems |                                                  |
| 26  | Milford M J, 2008, Mapping a suburb with a single camera using a biologically inspired slam system                          |                                                  |
| 27  | Hardcastle, 2015, Environmental boundaries as an error correction mechanism for grid cells                                  |                                                  |
| 28  | Chen G, 2013, How vision and movement combine in the hippocampal place code                                                 |                                                  |
| 29  | Sarel A, 2017, Vectorial representation of spatial goals in the hippocampus of bats                                         |                                                  |
| 30  | Dissanayake M G, 2001, A solution to the simultaneous localization and map building (slam) problem                          |                                                  |

