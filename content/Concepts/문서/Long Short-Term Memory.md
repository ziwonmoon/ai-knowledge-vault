---
aliases:
  - LSTM
  - 장단기 메모리
---
# 개요
기본 RNN에, **셀 상태(cell state)** 라는 별도의 장기 메모리 통로를 추가한 구조
과거의 정보(시퀀스상의 앞 정보)가 전달되지 않는 문제를 해결하기 위한 구조


# [[Recurrent Neural Network|Vanilla RNN]]과의 비교
| [[Recurrent Neural Network\|Vanilla RNN]] | LSTM                    |
| ----------------------------------------- | ----------------------- |
| ![[Vanilla RNN Structure.png]]            | ![[LSTM Structure.png]] |
은닉층의 메모리 셀에 입력 게이트, 망각 게이트, 출력 게이트를 추가하여 불필요한 기억을 지우고, 기억해야할 것을 정한다.
위 그림에서 셀 상태는 $C_t$로 표현된다.

RNN과 비교하여 긴 시퀀스의 입력을 처리하는데 탁월한 성능을 보인다.

## 도식 해석
$\sigma$ : Sigmoid Function
$W_{xi},W_{xg},W_{xf},W_{xo}$ : $x_t$와 함께 각 게이트에서 사용되는 가중치
$W_{hi},W_{hg},W_{hf},W_{ho}$ : $h_{t-1}$와 함께 각 게이트에서 사용되는 가중치
$b_i,b_g,b_f,b_o$ : 각 게이트에서 사용되는 편향
### 셀 상태
![[content/_assets/img/LSTM Cell State.png]]
셀 상태 : 위의 그림에서 왼쪽에서 오른쪽으로 가는 굵은 선
-> 이전 시점의 셀 상태가 다음 시점의 셀 상태를 구하기 위한 입력으로 사용됨

### 입력 게이트

![[LSTM Input Gate.png]]
$$i_t = \sigma(W_{xi}x_t+W_{hi}h_{t-1}+b_i)$$
$$g_t = tanh(W_{xg}x_t + W_{gh}h_{t-1} + b_g)$$
현재 정보를 기억하기 위한 게이트

이 두개의 값을 가지고 선택된 기억할 정보의 양을 정함. 구체적인 방법은 셀 상태 수식 참고

### 삭제 게이트
![[LSTM Remove Gate.png]]$$f_t = \sigma(W_{xf}x_t+W_{hf}h_{t-1}+b_f)$$
[[Sigmoid Function|시그모이드 함수]]이므로 0과 1사이의 값이 나온다
0에 가까울수록 정보가 많이 삭제된 것이고, 1에 가까울 수록 정보를 온전히 기억한 것이다.
이를 가지고 셀 상태를 구한다.

### 셀 상태 (장기 상태)
![[LSTM Cell State 1.png]]
$$C_t = f_t \circ C_{t_1} + i_t \circ g_t $$
$f_t(ELEMENT~WISE~DOT)C_{t_1}$ : 이전 셀 상태를 $f_t(0<=f_t<=1)$와 곱하여 삭제

아?마 $f_t$와 $i_t$는 $0<=X<=1$임을 이용해서 선택용으로 사용되는듯. 그래서 원소곱
### 출력 게이트와 은닉 상태 (단기 상태)
![[LSTM Output Gate and Hidden State.png]]
$$ o_t = \sigma(W_{xo}x_t + W_{ho}h_{t-1} + b_o)$$
$$h_t = o_t \circ tanh(c_t)$$
은닉상태(h)를 단기상태라고 하기도 한다. 은닉상태는 $0\leq h \leq1$의 범위를 가진다.