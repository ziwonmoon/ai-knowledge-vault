---
aliases:
  - Vanishing Gradient
  - Gradients Vanishing
  - 기울기 소실
---

역전파 과정에서 0에 가까운 아주 작은 기울기가 곱해지게 되면, 앞단에는 기울기가 잘 전달되지 않는 현상

![[Vanishing Gradient.png]]

## ReLU와 그 변형을 사용하라
은닉층에서는 시그모이드 함수를 사용하면 기울기 소실 문제가 발생하기 쉬움
대신 ReLU, LeakyReLU와 같은 함수를 사용
