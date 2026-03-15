---
aliases:
  - 워드 임베딩
  - 임베딩 벡터
  - Embedding Vector
date created: Sunday, March 15th 2026, 11:29:34 am
date modified: Sunday, March 15th 2026, 11:35:11 am
---
# 개요
단어를 [[Dense Representation|밀집 벡터]]의 형태로 표현하는 방법. 이 방법으로 나온 결과를 **임베딩 벡터**라고 한다.

워드 임베딩 방법론으로는 LSA, Word2Vec, FastText, Glove등이 있다.
파이토치에서 제공하는 도구인 nn.embedding()은 앞서 언급한 방법들을 사용하지는 않지만, 단어를 랜덤한 값을 가지는 밀집 벡터로 변환한 뒤에, 인공신경망의 가중치를 학습하는것과 같은 방식으로 단어 벡터를 학습하는 방법을 사용한다.

# One-Hot Vector vs Embedding Vector
![[One-Hot Vector vs Embedding Vector]]