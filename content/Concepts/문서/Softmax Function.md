---
aliases:
  - 소프트맥스 함수
  - Softmax
---

k차원의 벡터, i번째 원소를 $z_1$, i번째 클래스가 정답일 확률 $p_i$

$$p_i = \frac{e^{z_i}}{\sum^k_{j=1}e^{z_j}}$$

$$ softmax(z) = [\frac{e^{z_1}}{\sum^{3}_{j=1}e^{z_j}}, \frac{e^{z_2}}{\sum^{3}_{j=1}e^{z_j}}, \frac{e^{z_3}}{\sum^{3}_{j=1}e^{z_j}}] = [p_1, p_2, p_3] = \hat{y} = 예측값 $$

![[Softmax Function Plot.png]]