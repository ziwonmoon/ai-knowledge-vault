---
aliases:
  - PLA
date created: Wednesday, March 11th 2026, 6:40:44 pm
date modified: Thursday, March 12th 2026, 11:01:15 am
---
[[Perceptron|퍼셉트론]]의 가중치 $w$를 어떻게 학습할 것인가?

예측이 틀렸을 때만 가중치를 업데이트한다.

업데이트 식

$$\mathbf{w}(t+1) = \mathbf{w}(t) + y(t)\mathbf{x}$$
다르게 표현하면,
$$\mathbf{w} \leftarrow \mathbf{w} + y\mathbf{x}$$

**데이터가 선형 분리 가능하면 PLA는 반드시 수렴한다.**

y(예측결과)는 +1 또는 -1이기 때문에, 
(이게 어떻게 수렴하는지 생각하고 작성이어서하기)