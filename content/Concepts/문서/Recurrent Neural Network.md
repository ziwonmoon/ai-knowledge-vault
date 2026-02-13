---
aliases:
  - 순환 신경망
  - RNN
---
# 개요
딥 러닝에 있어서 가장 기본적인 [[Sequence Model|시퀀스 모델]].

[[Feed Borward Neural Network|피드 포워드 신경망]]과 달리, 이전 시점의 정보를 상태로 유지한다.
![[Non Feed Forward Neural Network.png]]

여기서 [[Cell|셀]]은 이전의 값을 기억하려고 하는 일종의 메모리 역할을 수행하므로 이를 [[Memory Cell|메모리 셀]]이라고 표현한다.

![[RNN의 두가지 표현.png]]
위 그림에서 두가지는 같은 표현이다. 우측이 시계열적으로 표현한 것.

# 수식
![[RNN Notation.png]]
현재 시점 $t$에서의 은닉 상태값은 $h_t$
[[Hidden Layer|은닉층]]의 [[Memory Cell|메모리 셀]]은 $h_t$계산을 위해 총 두개의 가중치가 필요하다.
$W_x$ : 입력층에서 입력값을 위한 가중치
$W_h$ : 이전 시점 $t-1$의 은닉 상태값인 $h_{t-1}$을 위한 가중치

$\text{은닉층}~h_t = tanh(W_xx_t+W_hh_{t-1}+b)$
$\text{출력층}~y_t = f(W_y+b)$

## 행렬 연산으로 이해하는 RNN 은닉층 연산
$x_t : (d \times 1)$
$W_x : (D_h \times d)$
$W_h : (D_h \times D_h)$
$h_{t-1} : (D_h \times 1)$
$b : (D_h \times 1)$
![[RNN Hidden Layer Calc.png]]
배치 크기가 1이고, d와 D_h 두 값 모두가 4로 가정했을 때, RNN의 은닉층 연산을 그림으로 표시한 것.

활성화 함수로는 추로 하이퍼볼릭 탄젠트가 사용되지만, ReLU로 바꿔 사용하려는 시도도 있다.

위의 식에서 $W_x, W_h, W_y$의 값은 모든 시점에서 값을 동일하게 공유한다. 만약, 은닉층이 2개 이상일 경우에는 은닉층 2개의 가중치는 서로 다르다.

# [[Feed Borward Neural Network|피드 포워드 신경망]]과의 차이점
피드 포워드 신경망에서는 [[Neuron|뉴런]]이라는 단위를 사용했다.
하지만 RNN에서는,
입력층과 출력층에서는 각각 입력 벡터와 출력 벡터,
은닉층에서는 은닉 상태
라는 표현을 주로 사용한다.

![[RNN Neuron.png]]
입력 벡터의 차원 : 4, 은닉 상태의 크기 : 2, 출력 벡터의 차원이 2 인 RNN
의 시점이 2일때의 모습

# 출력 구조
![[RNN Output Structures.png]]
입력과 출력의 길이를 다르게 설계할수 있으므로 다양한 용도로 사용할 수 있다.

