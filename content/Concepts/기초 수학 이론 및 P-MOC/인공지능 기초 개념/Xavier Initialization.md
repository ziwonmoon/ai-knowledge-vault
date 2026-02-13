---
aliases:
  - 자비에르 초기화
  - 세이비어 초기화
  - Glorot Initialization
---
$n_{in}$ : 이전 층의 뉴런의 개수
$n_{out}$: 다음 층의 뉴런의 개수
## Uniform Distribution 초기화
$$ W \sim Uniform(-\sqrt{\frac{6}{n_{in}+n_{out}}}, \sqrt{\frac{6}{n_{in}+n_{out}}}) $$

## Normal Distribution 초기화
$$ W \sim N(0, \sigma^2) $$
$$\sigma = \sqrt{\frac{2}{n_{in}+n_{out}}} $$

## 정리
여러 층의 기울기 분산 사이에 균형을 맞춰서 특정 층이 너무 주목을 받거나 다른 층이 뒤쳐지는것을 막는다.
S자 형태의 활성화 함수와 함께 사용하면 좋은 성능을 보인다.
하지만 ReLU계열에는 다른 초기화 방법을 사용하는것이 좋다. 