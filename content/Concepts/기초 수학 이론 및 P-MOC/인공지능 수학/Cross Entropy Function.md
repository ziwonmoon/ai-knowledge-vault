
$$ cost(W) = -\sum^k_{j=1}y_jlog(p_j)$$

n개 데이터 전체에 대한 평균은,

$$ cost(W) = -\frac{1}{n}\sum^n_{i=1}\sum^k_{j=1}y_j^{(i)}log(p_j^{(i)})$$
*복잡하네. [[Cross Entropy Function Subtitution Example|간단히 예시 넣어보기]]*



#### 이진 분류에서의 크로스 엔트로피 함수
$$
cost(W) = -\frac{1}{n}[y^{(i)}\log(H(x^{(i)}))+(1-y^{(i)})\log(1-H(x^{(i)}))]
$$
[[Cross Entropy Function Subtitution Example]]에서 확인할 수 있듯이, 동일한 식이다.

