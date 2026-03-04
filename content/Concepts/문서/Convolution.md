---
aliases:
  - 합성곱
  - 컨볼루션
---
# 개요
[[Convolutional Neural Network|CNN]]에서 사용. 입력과 [[Kernel|커널]]을 합성곱한다.


# 연속함수의 합성곱
$$(f*g)(t) = \int_{-\infty}^{\infty}f(\tau)g(t-\tau)d\tau$$
# 이산 합성곱
$$(f*g)[n] = \sum^\infty_{k=-\infty}f[k]g[n-k]$$


# [[Convolutional Neural Network|CNN]]에서의 실제 합성곱 구현
$$ y[n] = \sum_{k=0}^{K-1}x[n+k]w[k] $$
뒤집지 않는다.
네트워크가 알아서 이런 형태로 학습되기 때문에 굳이 뒤집을 필요가 없는것.
![[Convolution Example.png]]

# 다수의 [[이미지 처리|채널]]을 가질 경우의 합성곱 연산
![[Convolution when multi-channel.png]]
이때, 이건 3개의 [[Kernel|커널]]이 아니라, 3개의 [[이미지 처리|채널]]을 가진 1개의 [[Kernel|커널]]이다.

아래 그림도 수학적으로 완전히 동일한 연산

![[3-dimension convolution.png]]
$I_h$ : 입력의 높이
$I_w$ : 입력의 너비
$K_h$: 커널의 높이
$K_w$ : 커널의 너비
$O_h$ : 특성 맵의 높이 
$O_w$ : 특성 맵의 너비
$C_i$ : 입력 데이터의 채널

# 다수의 [[Kernel|커널]]을 가질 경우의 합성곱 연산
![[Convolution with multiple kernels.png]]
실제 [[Convolutional Neural Network|CNN]]은 커널을 여러개 동시에 연산한다.

커널은 서로 다른 가중치를 가지고, 서로 다른 특징을 학습한다.
입력 하나에 대해 커널 하나 당 출력이 여러 개 생기는데, 이는 출력의 채널이 된다

## 어떻게 여러 [[Kernel|커널]]이 다른 특징을 배우게 될까?
>일부러 다르게 만들지 않아도, 손실함수와 역전파가 알아서 다르게 만든다.

[[Back Propagation|역전파]]를 거치다 보면, 차이가 점점 커지면서 커널마다 다른 패턴을 담당하게 된다.

