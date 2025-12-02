---
aliases:
  - 소프트맥스 회귀
---

 ![[Softmax Function]]

예시.
![[Sofmax Regression Understanding.png]]

#### 1. 소프트맥스 함수의 입력
하나의 샘플 데이터의 독립 변수 4차원 벡터, 소프트맥스 함수는 3차원 벡터를 입력으로 받음.
![[Softmax Input Processing.png]]
각각의 화살표는 각각의 가중치. 총 12개. 학습 과정에서 변함.

#### 2. 오차를 구하는 방법
![[Softmax Regression Error.png]]
### 소프트맥스 회귀에서 예측값을 구하는 과정을 행렬으로 표현
![[Softmax Regression How to figure out the prediction.png]]

## Cost Function

![[Cross Entropy Function]]

