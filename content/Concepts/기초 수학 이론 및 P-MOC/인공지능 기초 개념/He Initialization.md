---
aliases:
  - He 초기화
---

[[Xavier Initialization|자비에르 초기화]]와 유사하게 정규분포화 균등분포 두가지 경우로 나뉜다.
다만, He 초기화는 다음 층 뉴런의 수를 반영하지 않는다.

$n_{in}$ : 이전 층 뉴런의 개수

## Uniform Distribution 초기화
$$ W \sim Uniform(-\sqrt{\frac{6}{n_{in}}},+\sqrt{\frac{6}{n_{in}}}) $$

## Normal Distribution 초기화
$$ W \sim N(0, \sigma^2) $$
$$ \sigma = \sqrt{\frac{2}{n_{in}}} $$

## 정리
S자 형태의 [[Activation Function|활성화 함수]]를 사용할때는 [[Xavier Initialization|세이비어 초기화]]쓰는게 낫다
[[ReLU]]쓸 때는 He 초기화를 보통 쓴다. ReLU + He 가 보편적인 방법