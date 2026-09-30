---
aliases:
  - 패스트텍스트
date created: Tuesday, September 15th 2026, 10:45:08 pm
date modified: Wednesday, September 16th 2026, 5:01:54 pm
---
# 개요
[[Word2Vec]]의 확장된 매커니즘
Word2Vec은 단어를 쪼개질 수 없는 단위로 생각한다면, FastText는 하나의 단어 안에도 여러 단어들이 존재하는 것으로 간주한다. 

# 예시
FastText에서는 각 글자 단위 [[N-gram Language Model|N-gram]]의 구성으로 취급한다.
n=3인 tri-gram의 경우 apple이라는 단어는
```
<apple>, <ap, app, pple, ple, le>
# '<'와 '>'는 처음과 끝이라는 표시
```
이렇게 5가지의 내부 단어 (subword) 토큰과, 기존 단어에 <>를 붙인 특별 토큰까지 6개의 토큰을 벡터화한다.

실제로는 보통 n의 범위를 지정하여 사용하는데, 기본값으로는 최소값 3 최대값6으로 둔다. 이 경우,
```
<ap, app, ppl, ple, le>,
<app, appl, pple, ple>,
<appl, apple, pple>,
<apple, apple>,
<apple>
```

# 모르는 단어에 대한 대응
데이터셋만 충분하다면 내부 단어를 통해 모르는 단어 (Out of Vocabulary, OOV)에 대해서도 다른 단어와의 유사도를 계산할 수 있다.

# 단어 집합 내 빈도수가 적었던 단어 (Rare Word)에 대한 대응
희귀 단어라도 다른 단어의 N-gram과 겹친다면, [[Word2Vec]]과 비교하여 비교적 높은 임베딩 벡터값을 얻는다.
노이즈가 많은 코퍼스에서 강점을 가진다. Word2Vec에서는 오타가 섞인 단어는 임베딩이 제대로 되지 않지만 FastText는 이에 대해서도 일정 수준의 성능을 보인다.

