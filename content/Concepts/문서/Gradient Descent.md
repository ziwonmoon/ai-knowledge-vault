---
aliases:
  - 경사 하강법
---

# 개요
[[Cost Function|손실 함수]]의 기울기를 따라 파라미터를 반복적으로 업데이트하여 최소값을 찾는 최적화 방법

$$ w \leftarrow w - \eta\nabla J(w) $$
$J(w)$ : 손실 함수
$\nabla J(w)$ : 손실 함수의 기울기(Gradient)
$\eta$ : 학습률

# 수식 예시
Bias는 무시하고, [[Weight]] 만 찾는 방법

$$
gradient = \frac{\partial cost(W)}{W}
$$

$$
W:=W-\alpha\times gradient
$$

α : Learning Rate. 