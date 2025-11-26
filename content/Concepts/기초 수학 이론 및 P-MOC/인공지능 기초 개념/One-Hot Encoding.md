
### Example

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


### 왜 1, 2, 3, 4로 인덱싱하지 않고 One-Hot Encoding 을 사용하는가?
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


