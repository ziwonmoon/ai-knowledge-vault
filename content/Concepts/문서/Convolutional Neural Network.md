---
aliases:
  - CNN
  - 합성곱 신경망
---
# 개요
[[이미지 처리]]를 위해 사용한다.
이미지의 공간적인 구조 정보를 보존하면서 학습할 수 있는 신경망.

크게 [[Convolution|합성곱]]층(Convolution Layer)과 [[Pooling|풀링]]층(Pooling Layer)으로 구성된다.
![[Conveolution Neural Network Example.png]]
비선형화를 위해 [[Activation Function|활성화 함수]]를 사용해야 하는것도 다른 인공신경망 모델과 동일하다.
(보통 [[ReLU]]와 그 변형을 사용한다.)

# [[Convolution|합성곱]] 연산
입력과 [[Kernel|커널]]을 [[Convolution|합성곱]]연산한다.

| [[Stride]]               | [[Padding]]      |
| ------------------------ | ---------------- |
| ![[CNN Convolution.png]] | ![[Padding.png]] |
커널의 원소는 가중치의 역할을 하고, 편향을 추가할 수 있다.
![[CNN bias.png]]

# [[Feature Map|특성 맵]]
입력과 커널을 합성곱한 결과  

$$O_h=floor(\frac{I_h-K_h+2P}{S}+1)$$

$$O_w=floor(\frac{I_w-K_w+2P}{S}+1)$$

$floor()$ : 내림
$I_h$ : 입력의 높이
$I_w$ : 입력의 너비
$K_h$ : 커널의 높이
$K_w$ : 커널의 너비
$S$ : 스트라이드
$O_h$ : 특성 맵의 높이
$O_w$ : 특성 맵의 너비
$P$ : 패딩의 폭

# [[Pooling|풀링]] 층
일반적으로 합성곱 층(합성곱 연산 + 활성화 함수) 다음에는 [[Pooling|풀링]] 층을 추가하는것이 일반적이다.