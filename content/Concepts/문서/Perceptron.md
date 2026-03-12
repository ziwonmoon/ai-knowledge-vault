---
aliases:
  - 퍼셉트론
---
# 개요
단층 문제를 해결 가능한 모델.
엄밀하게는 [[Neuron|뉴런]]의 하위 모델임.
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

# 근본
머신러닝 수업을 듣고.

$$\begin{aligned}
h(\mathbf{x})=sign(\sum^d_{i=1}(w_ix_i)+b)
\end{aligned}$$

이게 퍼셉트론. 끝. 근데 조금 더 행렬친화적으로 표현하면.

$$\begin{aligned}
\text{let}~~~ &b = w_0x_0 \\
\text{where}~~~ &w_0=b,~x_0=1 \\
h(\mathbf{x})&=sign(\sum^d_{i=0}w_ix_i) \\
&=sign(\mathbf{w}^T \mathbf{x})
\end{aligned}$$



# Logistic Regression vs Perceptron

Logistic Regression : $Sigmoid(\sum^n_i(W_ix_i+b))$
Perceptron : $Step(\sum^n_i(W_ix_i+b))$


# 하위 문서
* [[Single-Layer Perceptron]]
* [[Multi-Layer Perceptron]]


