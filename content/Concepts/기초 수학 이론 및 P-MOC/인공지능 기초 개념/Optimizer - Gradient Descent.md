---
aliases:
  - 경사 하강법
---

경사 하강법 : Cost Function 을 최소화하는 방법

Cost Function을 미분하여 구함 극소값을 찾음
Local Minimum == Global Minumum

예시) Bias는 무시하고, Weight 만 찾는 방법

$$
gradient = \frac{\partial cost(W)}{W}
$$

$$
W:=W-\alpha\times gradient
$$

α : Learning Rate. 