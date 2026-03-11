---
aliases:
  - One-Hot Vector
  - 원-핫 인코딩
  - 원-핫 벡터
---
# 개요
단어를 표현하는 가장 기본적인 표현 방법

# 과정
1. 정수 인코딩 : 각 단어에 고유한 인덱스를 부여한다.
2. 표현하고 싶은 단어의 인덱스의 위치에 1을 부여하고, 다른 단어의 인덱스의 위치에는 0을 부여한다.
# Example
- I like NLP
- I like DL
- DL is AI

| 단어   | One-Hot Vector |
| ---- | -------------- |
| I    | [1 0 0 0 0 0]  |
| like | [0 1 0 0 0 0]  |
| NLP  | [0 0 1 0 0 0]  |
| DL   | [0 0 0 1 0 0]  |
| is   | [0 0 0 0 1 0]  |
| AI   | [0 0 0 0 0 1]  |


# 왜 1, 2, 3, 4로 인덱싱하지 않고 One-Hot Encoding 을 사용하는가?
ex) MSE as the cost function
$$ Lost function = \frac{1}{n}\sum^{n}_{i}(y_i-\hat{y}_i)^2$$

| Banana | Tomato | Apple |
| ------ | ------ | ----- |
| 1      | 2      | 3     |
Answer: Tomato(2)
Prediction: Banana(1)
**MSE:1

Answer: Apple(3)
Prediction: Banana(1)
**MSE: 4

토마토-바나나가 사과-바나나보다 유사한가? -> 아니기 때문에
벡터로 표현해야 한다!


# 한계
단어의 개수가 늘어날수록, 벡터를 저장하기 위한 공간(벡터의 차원)이 계속 늘어난다.
단어의 유사도를 표현하지 못한다.