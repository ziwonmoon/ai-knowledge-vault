---
aliases:
  - 동시 등장 확률
date created: Saturday, September 12th 2026, 11:02:44 pm
date modified: Saturday, September 12th 2026, 11:13:44 pm
---
# 개요
동시 등장 확률 $P(k|i)$는 동시 등장 행렬로부터 특정 단어 $i$의 전체 등장 횟수를 카운트하고, 특정 단어 i가 등장했을 때 어떤 단어 $k$가 등장한 횟수를 카운트하여 계산한 조건부 확률

$P(k|i)$에서 $i$를 중심 단어(Center Word), $k$를 주변 단어(Context Word)라고 했을 때, [[Co-occurrence Matrix|동시 등장 행렬]]에서 중심 단어 $i$행의 모든 값을 더한 값을 분모로 하고 $i$행 $k$열의 값을 분자로 한 값

# 예시
| 동시 등장 확률과 크기 관계 비                          | $k=\text{solid}$ | $k=\text{gas}$ | $k=\text{water}$ | $k=\text{fasion}$ |
| ------------------------------------------ | ---------------- | -------------- | ---------------- | ----------------- |
| $P(k\mid\text{ice})$                       | 0.00019          | 0.000066       | 0.003            | 0.000017          |
| $P(k\mid\text{steam})$                     | 0.000022         | 0.000078       | 0.0022           | 0.000018          |
| $P(k\mid\text{ice})/ P(k\mid\text{steam})$ | 8.9              | 0.085          | 1.36             | 9.6               |
## 해석
ice가 등장했을때 solid가 등장할 확률은 steam이 등장했을 때 solid가 등장할 확률의 8.9배이다.
ice가 등장했을때 gas가 등장할 확률은 steam이 등장했을 때 gas가 등장할 확률의 0.085배이다.
