---
date created: Sunday, March 15th 2026, 11:49:22 am
date modified: Wednesday, March 18th 2026, 11:31:27 am
---
# 개요
[[Distributed Representation|분산 표현]]을 위한 학습 방법

[[CBOW]]와 [[Skip-Gram]] 두 가지 방식이 있다.

미리 훈련된 파라미터 많으니까 그거 써도 된다.

## Negative Sampling
대체적으로 Word2Vec을 사용한다고 하면 SGNS(Skip-Gram with Negative Sampling)을 사용한다. Word2Vec의 마지막 단계에서, 출력층에서 소프트맥스 함수를 거치는데 이는 무거운 작업이다.
하지만 Word2Vec은 모든 단어 집합에 대해서. '돈가스'와 '컴퓨터'와 같은 연관 관계가 없는 수많은 단어의 임베딩까지 조정한다. Word2Vec은 주변 단어들을 Positive로 두고 랜덤으로 샘플링 된 단어들을 Negative로 둔 다음에 이진 분류 문제를 수행한다.
이는 기존의 다중 클래스 분류 문제를 이진 분류 문제로 바꾸면서도 연산량에 있어서 훨씬 효율적이다.

# 딴이야기
Word2Vec은 자연어 처리에서 단어를 [[Dense Representation|밀집 벡터]]로 만들어주는 단어 임베딩 방법론이지만 최근에 들어서는 자연어 처리를 넘어서 추천 시스템에도 사용되는 모델이다. 키워드 **item2vec**
