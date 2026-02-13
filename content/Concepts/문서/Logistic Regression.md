---
aliases:
  - 로지스틱 회귀
---
# 개요
로지스틱 회귀는 이름은 Regression 이지만 실제로는 분류 (Classfication) 작업에 사용할 수 있음.

# 직선 함수의 사용 불가능
![[Logistic Regression Example Plot.png]]
이런 데이터를 훈련시키는데, 직선의 방정식을 활용하는 건 적절하지 않다.

# [[Sigmoid Function]]


# 인공 신경망으로 표현되는 로지스틱 회귀

로지스틱 회귀는 인공 신경망으로 간주할 수 있다.
![[ANN Logistic Regression.png]]
$$ H(x) = sigmoid(w_1x_1 + w_2x_2 + b) $$

*시그모이드 함수는 인공 신경망의 은닉층에서는 거의 사용하지는 않음.*
1. 기울기 소실 문제
2. 출력값이 항상 양수

