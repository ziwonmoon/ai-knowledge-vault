---
aliases:
  - 역전파
  - BackPropagation
date created: Sunday, February 1st 2026, 8:59:50 pm
date modified: Tuesday, March 17th 2026, 2:31:26 pm
---

![[신경망 학습]]
# 개요

이름 그대로. 출력에서 입력 방향으로 '거꾸로'들어가면서 가중치를 하나씩 업데이트함

역전파 1단계, 2단계 라는 식으로 명명할 수 있는데, 
레이어 사이의 가중치 행렬을 업데이트하는 하나하나의 단계를 뜻하는거임.
근데 거꾸로 들어가니까 제일 첫단계인 1단계는 가장 마지막 가중치행렬 업데이트.


# 직접 계산해보는 역전파
![[간단한 신경망 그림자료.png]]
활성화 함수로 시그모이드, 비용함수로 MSE 사용
### 역전파 1단계 $W_5$ 를 찾기 

>Chain Rule

$$
\frac{\partial E_{total}}{\partial W_5} = 
\frac{\partial E_{total}}{\partial o_1} \times
\frac{\partial o_1}{\partial z_3} \times
\frac{\partial z_3}{\partial W_5}
$$

#### ${\partial E_{total}} / {\partial o_1}$
$$
E_{total} = 
\frac{1}{2}(target_{o1}-output_{o1})^2 + \frac{1}{2}(target_{o2}-output_{o2})^2
$$

$target_{o1}$, $target_{o2}$, $output_{o2}$는 모두 $o_1$에 대한 함수가 아님.
$output_{o1} = o_1$임. 표기법 차이.
$$
\frac{\partial E_{total}}{\partial o_1} =
-target_{o1} + output_{o1}
$$
$target_{o1}, output_{o1}$ : 알고 있는 값.
#### ${\partial o_1} / {\partial z_3}$

참고,
![[Sigmoid Function#Sigmoid의 미분]]
또한, $o_1 = sigmoid(z_3)$ 이다.
$$
\frac{\partial o_1}{\partial z_3} =
o_1 \times (1 - o_1)
$$
$o_1$ : 알고 있는 값.
#### ${\partial z_3} / {\partial W_5}$
$$
\frac{\partial z_3}{\partial W_5}
= h_1
$$
왜 why? $W_5 \cdot h_1 + b = z_3$
$h_1$ : 알고 있는 값.
### 역전파 2단계 $W_1$ 찾기
$$
\frac{\partial E_{total}}{\partial W_1} =
\frac{\partial E_{total}}{\partial h_1} \times
\frac{\partial h_1}{\partial z_1} \times
\frac{\partial z_1}{\partial W_1}
$$
#### $\partial E_{total} / \partial h_1$


$$
\begin{aligned}
\frac{\partial E_{total}}{\partial h_1}
&= \frac{\partial E_{o1}}{\partial h_1} +
\frac{\partial E_{o2}}{\partial h_1}
\\
&= \frac{\partial E_{o1}}{\partial z_3}
\frac{\partial z_3}{\partial h_1} +
\frac{\partial E_{o2}}{\partial z_4}
\frac{\partial z_4}{\partial h_1}
\\
&= \frac{\partial E_{o1}}{\partial o_1}
\frac{\partial o_1}{\partial z_3}
\frac{\partial z_3}{\partial h_1} +
\frac{\partial E_{o2}}{\partial o_2}
\frac{\partial o_2}{\partial z_4}
\frac{\partial z_4}{\partial h_1}
\end{aligned}
$$


1단계와 같은 방법
#### $\partial E_{o1} / \partial o_1$
$$
\begin{aligned}
E_{o1} &= \frac{1}{2}(target_{o1}-output_{o1})^2 \\
\frac{\partial E_{o1}}{\partial o_1}
&= -(target_{o1} - output_{o1})
\end{aligned}
$$
$target_{o1}, output_{o1}$ : 알고 있는 값.
#### ${\partial o_1}/{\partial z_3}$
$$
\frac{\partial o_1}{\partial z_3} = o_1 \times (1 - o_1)
$$
$o_1$ : 알고 있는 값.
#### $\partial z_3 / \partial h_1$
$$
\frac{\partial z_3}{\partial h_1} =
W_5
$$
$W_1$ : 알고 있는 값 (역전파 1단계에서 구함)

## 결론
이처럼 역전파 단계를 거쳐가며 새로운 가중치 값을 찾아낼 수 있음을 확인하였다.