---
aliases:
  - 코사인 유사도
---
두 벡터간의 코사인 각도를 이용하여 구할 수 있는 두 벡터의 유사도.
![[Cosine Similarity.png]]$$similarity = cos(\theta) = \frac{A\cdot B}{||A||~||B||}=\frac{\sum^n_{i=1}A_i\times B_i}{\sqrt{\sum^n_{i=1}(A_i)^2}\times\sqrt{\sum^n_{i=1}(B_i)^2}}$$
문서의 길이가 다른 상황에서 공정한 비교를 할 수 있다.