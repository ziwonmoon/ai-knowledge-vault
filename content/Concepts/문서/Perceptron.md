---
aliases:
  - 퍼셉트론
---

초기 형태의 인공신경망
다수의 입력으로부터 하나의 결과를 내보냄
가중치곱의 합이 임계점을 넘으면 1을 출력, 아니면 0을 출력.

![[Perceptron Neuron.png]]

![[Perceptron Multi Input.png]]

$$ if\sum^{n}_{i} W_ix_i \geq \theta \rightarrow y=1 $$
$$ if\sum^n_iW_ix_i < \theta \rightarrow y=0 $$
$\theta$ 좌변으로 넘기고 $b$ 로 변경

![[Perceptron Multi Input Bias.png]]
$$ if\sum^n_iW_ix_i + b \geq 0 \rightarrow y=1 $$
$$ if\sum^n_iW_ix_i+b < 0 \rightarrow y=0 $$
$b=(-\theta)$ 자료에서 생략되더라도 편향또한 최적의 값을 찾아야 할 변수


## Logistic Regression vs Perceptron

Logistic Regression : $Sigmoid(\sum^n_i(W_ix_i+b))$
Perceptron : $Step(\sum^n_i(W_ix_i+b))$


## 하위 문서
* [[Single-Layer Perceptron]]
* [[Multi-Layer Perceptron (MLP)]]


