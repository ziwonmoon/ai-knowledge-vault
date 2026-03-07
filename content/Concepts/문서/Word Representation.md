---
aliases:
  - 단어 표현 방법
---

# 개요
단어의 표현 방법은 크게 국소 표현(Local Representation) 방법과 분산 표현 (Distributed Representation) 방법으로 나뉜다. 국소 표현 방법은 해당 단어 그 자체만 보고, 특정값을 매핑하여 단어를 표현하는 방법이며, 분산 표현 방법은 그 단어를 표현하고자 주변을 참고하여 단어를 표현하는 방법이다.
국소 표현 방법을 이산 표현 (Discrete Representation) 이라고도 하며, 분산 표현을 연속 표현 (Continous Representaiton)이라고도 한다. 국소 표현 방법은 단어의 의미, 뉘앙스를 표현할 수 없지만, 분산 표현 방법은 단어의 뉘앙스를 표현할 수 있게 된다.

![[Word Categorizing.png]]
# Local Representation
## [[One-Hot Encoding|One-Hot Vector]]
각 단어마다 하나의 자리만 1이고 나머지는 0인 벡터로 표현하는 방법

## [[Back of Words]]
단어의 순서는 고려하지 않고, 출현 빈도에만 집중하는 수치화 표현 방법