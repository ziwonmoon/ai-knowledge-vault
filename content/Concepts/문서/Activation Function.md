---
aliases:
  - 활성화 함수
---
# 개요
뉴런에서 출력값을 변경시키는 함수.
Nonlinear function : 활성화 함수는 비선형 함수이다.
>선형 함수로는 은닉층을 여러번 추가하더라도 1회 추가한 것과 등가이다.
>그러므로 은닉층에 선형 함수를 사용한다면, 중간중간에 비선형 함수를 끼워줘야함.

| 문제                             | 활성화 함수  |
| ------------------------------ | ------- |
| [[Binary Classfication]]       | Sigmoid |
| [[Multi-class Classification]] | Softmax |
| [[Regression]]                 | 없음.     |

>스탠포드 대학교의 딥 러닝 강의(cs231n)에서는 ReLU를 먼저 시도해보고, 그 다음으로 LeakyReLU나 ELU같은 ReLU의 변형들을 시도해보며, Sigmoid는 사용하지 말라고 권장함.


# [[Sigmoid Function]] and [[Gradient Vanishing]]
![[Sigmoid Function and Vanishing Gradient.png]]
![[신경망 학습]]

![[Sigmoid Function Vanishing Gradients.png]]
![[Gradient Vanishing]]

매개변수 W가 업데이트 되자 않아 학습이 되지 않음.

**시그모이드 함수를 은닉층에 사용하는 것은 지양됨**

# 예시
## Hyperbolic Tangent Function 
![[Hyperbolic Tangent Function]]

## ReLU 
![[ReLU]]

## Leaky ReLU
![[Leaky ReLU]]

## Softmax Function
![[Softmax Function]]
