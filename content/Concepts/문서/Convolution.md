---
aliases:
  - 합성곱
---
# 개요
[[Convolutional Neural Network|CNN]]에서 사용. 입력과 [[커널]]을 합성곱한다.


# 연속함수의 합성곱
$$(f*g)(t) = \int_{-\infty}^{\infty}f(\tau)g(t-\tau)d\tau$$
# 이산 합성곱
$$(f*g)[n] = \sum^\infty_{k=-\infty}f[k]g[n-k]$$


# [[Convolutional Neural Network|CNN]]에서의 실제 합성곱 구현
$$ y[n] = \sum_{k=0}^{K-1}x[n+k]w[k] $$
뒤집지 않는다.
네트워크가 알아서 이런 형태로 학습되기 때문에 굳이 뒤집을 필요가 없는것.
![[Convolution Example.png]]