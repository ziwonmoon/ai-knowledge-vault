---
aliases:
  - 임베딩 층
date created: Wednesday, September 30th 2026, 4:29:40 pm
date modified: Saturday, October 3rd 2026, 9:51:19 pm
---

임베딩 층(embedding layer)를 만들어 훈련 데이터로부터 처음부터 임베딩 벡터를 학습할 수 있다.

임베딩 과정은
어떤 단어 -> 단어에 부여된 고유한 정수값(정수 인코딩) -> 임베딩 층 통과 -> 밀집 벡터

이렇게 이루어진다.

정수를 [[Dense Representation|밀집 벡터]]로 매핑한다는 점에서, 임베딩 레이어를 "특정 단어와 매핑되는 정수를 인덱스로 가지는 테이블로부터 임베딩 벡터 값을 가져오는 룩업 테이블"이라고 볼 수 있다.

![[embedding vector lookup table.png]]