---
aliases:
  - GAP
---
각 [[Feature Map]]의 모든 값을 평균하여 [[이미지 처리|채널]]당 하나의 값으로 요약하는 [[Pooling|풀링]]연산

$$H \times W \times C \rightarrow 1 \times 1 \times C$$
직관적으로, 각 특성 맵이 이미지 전체에서 얼마나 강하게 활성화되었는지를 하나의 값으로 요약한다. 공간 정보는 없어지고 특성의 존재 정도만 남겨진다