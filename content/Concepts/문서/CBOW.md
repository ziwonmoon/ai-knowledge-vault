---
aliases:
  - Continous Bag of Words
date created: Sunday, March 15th 2026, 1:36:25 pm
date modified: Sunday, March 15th 2026, 3:23:44 pm
---
# 개요
[[Word2Vec]]의 한가지 방법
주변의 단어를 가지고 중간의 단어를 예측한다.
# 예시
코퍼스에 아래와 같은 문장이 있다.
> The fat cat sat on the mat

예측하고 싶은 단어 sat을 중심 단어(center word)라고 하고, 예측에 사용되는 단어를 주변 단어(context word)라고 한다.
중심 단어를 예측하기 위해 앞뒤로 몇개의 단어를 볼지에 대한 범위를 윈도우(window)라고 한다. 앞뒤로 참고하기 때문에, 윈도우 크기가 n이라면, 실제 중심단어를 예측하기 위해 참고하는 주변 단어의 개수는 2n개이다.

Word2Vec에서 입련은 모두 [[One-Hot Encoding|One-Hot Vector]]가 되어야 한다.
## 슬라이딩 윈도우 (Sliding Window)
![[CBOW Sliding Window.png]]

## CBOW의 인공 신경망
![[content/_assets/img/CBOW Neural Network.png]]
입력측의 입력으로서 앞뒤의 단어들의 One-Hot Vector가 들어간다.
출력층에서 예측하고자 하는 단어의 One-Hot Vector가 필요하다.

[[Word2Vec]]은 딥러닝 모델은 아니다. 입력층과 출력층 사이의 은닉층의 개수가 단 하나이기 때문이다. 이런 경우는 보통 Shallow Neural Network라고 부른다.

Word2Vec의 은닉층은 일반적인 은닉층과는 달리 [[Activation Function|활성화 함수]]가 존재하지 않고, **룩업 테이블**이라는 연산을 담당하는 층이다. 일반적인 은닉층과 구분하기 위해 **투사층(Projection Layer)이라고** 부르기도 한다.

## 자세히 알아보기
![[CBOW Neural Network 1.png]]
투사층의 크기가 M이다. M은 임베딩하고 난 벡터의 차원이다. 다시 말해, 위 그림에서 투사층의 크기는 M=5이기 때문에 CBOW를 수행하고 나서 얻는 각 단어의 임베딩 벡터의 차원은 5가 된다.
입력층과 투사층 사이의 가중치 W는 V x M 행렬이며, 투사층에서 출력층사이의 가중치 W'는 M x V행렬이다. (참고로 W'는 표기만 그렇지 W의 전치행렬은 아니다. 완전히 다른 새로운 행렬)
CBOW는 W와 W'를 계속해서 학습해나가는 인공신경망이다.

## Lookup Table
![[CBOW Lookup Table.png]]
$x$ : 각 주변 단어의 원-핫 벡터.
i번째 인덱스에 1이라는 값을 가지고 그 외에 0을 값을 가지는 입력 벡터와 가중치 W행렬의 곱은 W행렬의 i번째 행을 그대로 읽어오는것과 동일하다. 그래서 이 벡터를 lookup table이라고 부른다.
여기서 lookup해온 W의 각 행벡터가 사실 [[Word2Vec]]을 수행한 후의 각 단어의 M차원의 크기를 갖는 임베딩 벡터이다.

## Projection Layer
![[CBOW Projection Layer.png]]
Lookup Table의 결과들은 모두 더해져 벡터들은 투사층에서 만나 이 벡터들의 평균인 벡터를 구하게 된다. [^1]

## Output Layer
![[CBOW Output Layer.png]]
행렬곱을 (1 x V \* V x M \* M x V) 했기 때문에 1 x V 행렬이 나온다.
이 벡터에 대해 [[Softmax Function|소프트맥스 함수]]를 취하는데, 이렇게 나온 값을 Score Vector라고 한다.

## Score Vector
스코어 벡터의 j번째 인덱스가 가진 0과 1사이의 값은 j번째 단어가 중심 단어일 확률을 나타낸다. 그리고 이 스코어 벡터는 우리가 실제로 알고 있는 벡터인 중심 단어의 [[One-Hot Encoding|One-Hot Vector]]의 값과 가까워져야 한다.
스코어 벡터를 $\hat{y}$라고 한다. 중심단어를 $y$로 했을 때, 이 두벡터값의 오차를 줄이기위해 CBOW는 [[Cost Function|손실 함수]]로 [[Cross Entropy Function]]을 사용한다.

$$\begin{aligned}
H(\hat{y}, y) &= -\sum^{|V|}_{j=1}y_jlog(\hat{y}_j) \\
&=-y_ilog(\hat{y}_i)~~\because\text{\ y는 One-Hot Vector}
\end{aligned}$$

## Embedding Vector
이제 [[Back Propagation|역전파]]를 수행하여 W와 W'를 학습한다. 학습이 다 되었다면 M차원의 크기를 갖는 W의 행이나 W'의 열로부터 어떤 것을 [[Word Embedding|임베딩 벡터]]로 사용할지를 결정한다. 때로는 W와 W'의 평균치를 가지고 임베딩 벡터를 선택하기도 한다. [^2]

[^1]: 왜 평균? 그냥 쓰면 안되나?

[^2]: 여기서 선택한 임베딩 벡터가 **단어를 벡터로 표현한 것 그 자체**가 된다.
