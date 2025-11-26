
$$ cost(W) = -\frac{1}{n}\sum^n_{i=1}\sum^k_{j=1}y_j^{(i)}log(p_j^{(i)})$$

n = 1 : 하나의 샘플
k = 3 : 3 분류

$$
cost(W) = -(y_1log(p_1) + y_2log(p_2) + y_3log(p_3))
$$
$p_j$ : 한 샘플 내에서 예측값을 결정하는, 정답의 확률, $p_1 + p_2 + p_3 = 1$ 
$y_j$ : 예측이 $j$일때 1인 One-Hot Vector의 요소

> 선택의 개념. y는 어떤 로그항을 사용할까 결정함
