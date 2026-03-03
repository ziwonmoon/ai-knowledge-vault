---
aliases:
  - N-gram
  - N-gram 언어 모델
---
# 개요
카운트에 기반한 통계적 접근을 사용하는 [[Statistical Language Model|SLM]]의 일종
일반적인 SLM과는 달리 이전에 등장한 모든 단어를 고려하는 것이 아닌 일부 단어만 고려한다. 이대 일부 단어를 몇 개 보느냐를 결정하는데 이것이 N-gram에서의 N의 의미이다.

# 접근 방법
$P(\text{is | An adorable little boy}) \approx P(\text{is | boy})$
이처럼 참고하는 단어를 줄이면 카운트(이를 보고 다음 단어를 예측)를 할 가능성을 높일 수 있다.

# N-gram
N-gram은 N개의 연속적인 단어 나열을 의미한다. N-gram을 통한 언어 모델에서는 다음에 나올 단어의 예측은 오직 n-1개의 단어에만 의존한다.
unigrams, bigrams, trigrams, 4-grams

# 한계
전체 문장을 고려한 언어 모델보다는 정확도가 떨어진다.
## Sparsity Problem (희소 문제)
N을 크게 선택한다면 예측의 정확도는 높아지더라도 희소 문제는 점점 심각해진다. N이 커질수록 모델 사이즈가 커진다.
N을 작게 선택한다면 카운트는 잘 되겠지만 근사의 정확도는 현실의 확률분포와 멀어진다. **N은 최대 5를 넘게 잡아서는 안 된다고 권장**된다.

|            | Unigram | Bigram | Trigram |
| ---------- | ------- | ------ | ------- |
| Perplexity | 962     | 170    | 109     |
