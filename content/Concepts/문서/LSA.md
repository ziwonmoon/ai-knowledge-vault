---
aliases:
  - Latent Semantic Analysis
date created: Saturday, September 12th 2026, 10:47:01 pm
date modified: Saturday, September 12th 2026, 10:54:36 pm
---
각 단어의 빈도수를 카운트한 행렬을 입력으로 받아 차원을 축소(Truncated SVD)하여 잠재된 의미를 끌어내는 방법론.

# [[Word2Vec]]과의 비교
LSA는 `왕:남자=여왕:?`과 같은 유추 잡업(Analogy task)에는 성능이 떨어진다.
[[Word2Vec]]은 예측 기반으로 단어간 유추 작업에는 LSA보다 뛰어나지만, 임베딩 벡터가 윈도우 크기 내에서만 주변 단어를 고려하기 때문에 [[Corpus|코퍼스]]의 전체적인 통계 정보를 반영하지 못한다.

이러한 한계를 극복하기 위해 나온게 [[GloVE]]라고 생각하면 된다.