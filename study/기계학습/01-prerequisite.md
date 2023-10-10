---
created-at: 2023-10-10T12:58
tags:
  - study
  - ML
description:
---
# 01-Prerequisite for ML
## 기계학습이란
- Mitchell의 정의
	- A computer program is said to learn from experience E with respect to some class of task T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E
	- 어떤 컴퓨터 프로그램이 T라는 작업을 수행한다. 이 프로그램의 성능을 P라는 척도로 평가한다. 경험 E를 통해 성능 P가 개선된다면 이 프로그램은 학습을 한다고 말할 수 있다.
## 기계 학습 문제
- 분류(classification): 미리 정의된 범주에 입력 데이터를 할당하는 문제
- 군집화(clustering): 미리 정의된 규칙에 따라 데이터를 그룹화하는 문제
- 생성(generation): todo
## 기계 학습 방법론
- 지도 학습
- 비지도 학습
- 반지도 학습
### 지도 학습
지도 학습(supervised learning): 정답이 부착된 데이터를 바탕으로 학습을 진행
- 장점: 비지도 학습에 비해 높은 성능을 보임
- 단점: 데이터 구축에 많은 시간과 노력이 듦
### 비지도 학습
비지도 학습(unsupervised learning): 정의된 척도(measue)에 따라 학습을 진행
- 장점: 정답 부착이 불필요해 데이터 구축이 쉬움
- 단점: 지도 학습에 비해 낮은 성능을 보임
- 척도 예시: 유클리디언 거리, 코사인 유사도
- 예시: 유사한 문장, 문서, 혹은 단어를 그룹화
###  반지도 학습
반지도 학습(semi-supervised learning): 소량의 정답 부착 데이터를 바탕으로 모델을 만들고, 대량의 정답 미부착 데이터를 바탕으로 성능을 개선
- 장점: 데이터 구축이 지도 학습보다 쉬움
- 단점: 지도 학습에 근접하지만 낮은 성능
- 능동 학습(active learning)
	1. 정답 부착 데이터로 모델 학습
	2. 학습된 모델을 이용하여 정답 미부착 데이터에 정답 자동 부착
	3. 일정 수준 이하의 자동 부착 정답을 수정하여 데이터에 추가
	4. 수렴할 때까지 (1)~(3) 반복
## 데이터 구성
- 기계학습 데이터: 훈련 데이터(80%) + 개발 데이터(10%) + 평가 데이터(10%)
- 훈련 데이터(training data, train set): 모델을 만들기 위해 사용되는 데이터
- 개발 데이터(developing data, dev set): 학습이 잘 되고 있는지 평가하는데 사용되는 데이터
- 평가 데이터(test data, test set): 최종 학습된 모델을 평가하기 위해 사용되는 데이터
## 지도 학습 모델 개발 절차
1. 데이터 수집
2. 데이터 변환
3. 모델 학습
4. 모델 평가
### 데이터 수집
- 고려사항
	- 기계학습 대상이 되는 문제를 명확히 선정
	- 문제 해결을 위한 데이터를 가능한 많이 수집
	- 문제 대상 데이터(positive data)와 비대상 데이터(negative data)를 균형 있게 수집
- 예시
	- 문제: 스팸 메일 검출
	- Positive data: 스팸 메일
	- Negative data: 비스팸 메일
### 데이터 변환
- 자질 추출(feature extraction): 주어진 문제를 해결하는 데 중요한 단서가 될 수 있는 정보를 선별하여 기계가 읽을 수 있는 형태로 변환하는 작업
- 정답 부착(labeling, tagging, annotation): 지도 학습을 위해서 자질 추출 데이터에 정답을 부착하는 작업. 시간과 노력이 많이 든다.
- ARFF(Attribute-Relation File Format): WEKA라는 기계학습 툴킷에서 사용하는 데이터 포맷
### 모델 학습
- 적합한 모델 선택
	- Decision tree
	- Support vector machine
	- Conditional random fields
	- Artificial neural network
- 다양한 툴킷을 이용하여 모델 구성 및 학습
	- GUI 기반 기계학습: WEKA
	- 전통적인 기계학습: Scikit-learn
	- 딥러닝(deep learning): Tensorflow, Pytorch
### 모델 평가
- Closed test
	- 학습 데이터를 이용한 평가
	- 학습이 되고 있는지 확인
- Development test
	- 개발 데이터를 이용한 평가
	- 올바른 방향으로 학습되고 있는지 확인
- Open set
	- 평가 데이터를 이용한 평가
	- 실제 환경에서 어느 정도 성능이 나오는지 확인

- 10배 교차검증(10-fold cross validation)
	1. 데이터를 10등분 후 9개로 학습, 1개로 평가
	2. (1) 과정을 10회 반복
	3. 10회 평가의 평균 값을 모델의 성능으로 사용
- 평가 척도(evaluation measure)	$$\begin{array}
~ & 정답(1) & 정답(0) \\
\hline
예측(1) & TP & FP \\
\hline
예측(0) & FN & TN \\
\hline
\end{array}$$
	- 정밀도(accuracy): 레이블에 상관 없이 맞은 것의 비율	$$\frac{TP + TN}{TP + FP + FN + TN}$$
	- 정확률(precision): 모델의 (true) 출력 중에 맞은 것의 비율
	$$\frac{TP}{TP + FP}$$
	- 재현율(recall): 정답(positive) 중에 맞은 것의 비율
	$$\frac{TP}{TP + FP}$$
	- F1-score: 정확률과 재현율의 조화평균
	$$\frac{2(precision)(recall)}{(precision) + (recall)}$$