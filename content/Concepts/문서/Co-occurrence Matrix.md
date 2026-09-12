---
aliases:
  - 동시 등장 행렬
  - Window based Co-occurrence Matrix
  - 윈도우 기반 동시 등장 행렬
date created: Saturday, September 12th 2026, 10:56:01 pm
date modified: Saturday, September 12th 2026, 11:14:07 pm
---
# 개요
행과 열을 전체 단어 집합의 단어들로 구성하고, i단어의 윈도우 크기(Window Size) 내에서 k 단어가 등장한 횟수를 i 행 k 열에 기재한 행렬

이를 가지고 [[Co-occurence Probability|동시 등장 확률]]을 계산할 수 있다.
# Ex
>I like deep learning
>I like NLP
>I enjoy flying

윈도우 크기가 N이라는건, 단어 좌우의 N개의 단어만 참고한다는 뜻
윈도우 크기가 1일 때의 예제

| 카운트      | I   | like | enjoy | deep | learning | NLP |
| -------- | --- | ---- | ----- | ---- | -------- | --- |
| I        | 0   | 2    | 1     | 0    | 0        | 0   |
| like     | 2   | 0    | 0     | 1    | 0        | 1   |
| enjoy    | 1   | 0    | 0     | 0    | 0        | 0   |
| deep     | 0   | 1    | 0     | 0    | 1        | 0   |
| learning | 0   | 0    | 0     | 1    | 0        | 0   |
| NLP      | 0   | 1    | 0     | 0    | 0        | 0   |
| flying   | 0   | 0    | 1     | 0    | 0        | 0   |

전치(Transpose)해도 동일한 행렬이 된다는 특징이 있다.
