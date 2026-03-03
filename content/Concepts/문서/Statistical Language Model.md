---
aliases:
  - 통계적 언어 모델
  - SLM
---
# 개요
언어 모델의 전통적인 접근 방법

# 문장에 대한 확률
문장의 각 단어는 문맥이라는 관계로 인해 이전 단어의 영향을 받아 나온 단어이다. 그리고 모든 단어로 하나의 문장이 완성되기 때문에 문장의 확률을 구하고자 [[Conditional Probability|조건부 확률]]을 사용할 수 있다.

## 예시
문장 \[An adorable little boy is spreading smiles]을 확률 P(An adorable little boy is spreading smiles)라고 표현할 수 있다.
![[Conditional Probability#^2e9ba5]]
 문장에 해당 식을 적용하면 다음과 같다.
 P(An adorable little boy is spreading smiles) = P(An) x P(adorable|An) x P(little | An adorable) x P(boy | An adorable little) x P(is | An adorable little boy) x P(spreading | An adorable little boy is) x P(smiles | An adorable little boy is spreading)

# 이전 단어로부터 다음 단어에 대한 확률을 구하는 방법
카운트에 기반하여 확률을 계산한다.
$$$P(\text{is | An adorable little boy}) = \frac{\text{count(An adorable little boy is)}}{\text{count(And adorable little boy)}}$$

## Sparsity Problem (희소 문제)
충분한 데이터를 관측하지 못하여 언어를 정확히 모델링하지 못하는 문제

이 문제를 완화하는 방법으로 N-gram 언어 모델이나 스무딩, 백오프 같은 여러가지 일반화 기법이 존자한다. 하지만 희소문제에 대한 근본적인 해결책은 되지 못하기 때문에 "인공 신경망 언어 모델"을 사용한다.
