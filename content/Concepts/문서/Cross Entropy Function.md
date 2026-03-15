---
date created: Sunday, January 25th 2026, 6:42:46 pm
date modified: Sunday, March 15th 2026, 3:09:40 pm
---
# 개요
$$ cost(\mathbf{W}) = -\sum^k_{j=1}y_jlog(p_j)$$

$\mathbf{W} = \begin{bmatrix} w_{11} & w_{12} & \dots & w_{1d} \\ w_{21} & w_{22} & \dots & w_{2d} \\ \vdots & \vdots & \ddots & \vdots \\ w_{k1} & w_{k2} & \dots & w_{kd} \end{bmatrix}$

$k$ : 분류해야 하는 전체 클래스의 개수
$d$ : 입력 특징의 개수
$j$: 클래스 인덱스
$y_j$ : 정답을 벡터로 표현한 것의 j번째 값(보통 [[One-Hot Encoding|One-Hot Vector]]
	예를 들어, 클래스가 3개이고 정답이 두 번째 클래스라면
	$y =[0, 1, 0]$
	따라서
	- $y_1 = 0$
	- $y_2 = 1$
	- $y_3 = 0$
$p_j$ : 모델이 예측한 클래스 j일 확률. 보통 [[Softmax Function|Softmax]]로 계산된다.
출력값 : 스칼라

정답 클래스 확률이 높을수록 loss가 작아지고 정답 클래스 확률이 낮으면 loss가 커지도록 설계되었다.
## $y$가 One-Hot Vector라면
결국 식은 $cost = -log(p_{j^*})$으로 정답일 확률에 로그를 씌운것에 불과하다.
정답일 확률이 1이면 손실함수는 0, 정답 확률이 0.1이면 2.3



## n개 데이터 전체에 대한 평균

$$ cost(\mathbf{W}) = -\frac{1}{n}\sum^n_{i=1}\sum^k_{j=1}y_j^{(i)}log(p_j^{(i)})$$
*복잡하네. [[Cross Entropy Function Subtitution Example|간단히 예시 넣어보기]]*



# 이진 분류에서의 크로스 엔트로피 함수
$$
cost(W) = -\frac{1}{n}[y^{(i)}\log(H(x^{(i)}))+(1-y^{(i)})\log(1-H(x^{(i)}))]
$$
[[Cross Entropy Function Subtitution Example]]에서 확인할 수 있듯이, 동일한 식이다.

