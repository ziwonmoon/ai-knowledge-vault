
$$ sigmoid(Wx+b) = \frac{1}{1+e^{-(Wx+b)}} $$
선형 회귀에서와 비슷하게, 가중치와, 편향을 찾는게 목표.


![[Sigmoid Function Plot.png]]

$$ -1 < sigmoid(x) < 1 $$ $$ \lim_{x \to \infty}{sigmoid(x)}=1 $$$$  \lim_{x \to -\infty}{sigmoid(x)} = -1 $$

#### W 바꿔보기
![[Sigmoid Funtion Weigts Variance.png]]
W값이 클 수록 그래프의 경사가 심해짐

#### b 바꿔보기
![[Sigmoid Function bais Variance.png]]그래프의 x축 이동


#### Sigmoid 비용 함수 - MSE(Mean Square Error)?
$$ cost(W, b) = \frac{1}{n} \sum_{i=1}^{n}{[y^{(i)}-H(x^{(i)})]^2}$$
$$H(x) = sigmoid(Wx+b)$$
![[Differential of Sigmoid Function.png]]
미분한다고 해도 최소값을 찾을 수 있는게 아니라서 이거 안씀.
## Sigmoid 비용 함수 - 크로스 엔트로피 함수
![[Sigmoid Cost Function - Log.png]]
$$cost(H(x),y) = \begin{cases}-\log(H(x))\\-\log(1-H(x))\end{cases}$$
$$
cost(W) = -\frac{1}{n}[y^{(i)}\log(H(x^{(i)}))+(1-y^{(i)})\log(1-H(x^{(i)}))]
$$
y = 실제 결과값(1 or 0)
