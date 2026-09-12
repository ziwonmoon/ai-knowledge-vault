---
aliases:
  - 글로브
  - Global Vectors for Word Representation
  - GloVe
date created: Saturday, September 12th 2026, 10:42:27 pm
date modified: Sunday, September 13th 2026, 12:38:19 am
---
# 개요
카운트 기반과 예측 기반을 모두 사용하는 [[Word Embedding|워드 임베딩]] 방법론

# [[Cost Function|손실 함수]] 유도
[[Co-occurence Probability|동시 등장 확률]]의 개념이 필요하다

- $X$ : [[Co-occurrence Matrix|동시 등장 행렬]]
- $X_{ij}$ : 중심 단어 $i$가 등장했을 때 윈도우 내 주변 단어 $j$가 등장하는 횟수
- $X_i = \sum_j{X_{ij}}$ : 동시 등장 행렬에서 $i$행의 값을 모두 더한 값
- $P_{ik} = P(k|i) = \frac{X_{ik}}{X_i}$ : 중심 단어 $i$가 등장했을 때 윈도우 내 주변 단어 $k$가 등장할 확률
Ex) $P({\text{solid} \mid \text{ice})}$ : 단어 ice가 등장했을 때 단어 solid가 등장할 확률
- $\frac{P_{ik}}{P_{jk}}$ : $P_{ik}$를 ${P_{jk}}$로 나눠준 값
Ex) $P({\text{solid} \mid \text{ice})} / P({\text{solid} \mid \text{steam})} = 8.9$
- $w_i$ : 주변 단어 $i$의 임베딩 벡터
- $\tilde{w_k}$ : 주변 단어 k의 임베딩 벡터

Glove의 아이디어를 한 줄로 요약하면 **임베딩 된 중심 단어와 주변 단어 벡터의 내적이 전체 코퍼스에서의 동시 등장 확률이 되도록 만드는 것**
>정확히는 동시 등장 확률 그 자체가 아닌 그 확률의 로그값에 대응하도록 학습한다.

>[!note]
># 내적이라는 연산이 등장하는 이유(직관적 설명)
>두 단어 벡터의 관계를 숫자 하나로 만드는 가장 자연스러운 연산이 내적이기 때문
>
>내적이 크면 두 단어가 관련이 있다고 할 수 있음
>더 나아가, 로그를 사용하기 때문에 확률의 비용이 뺄셈으로 바뀐다
>$\text{king} - \text{man} + \text{woman} \approx \text{queen}$ 이렇게 되는것도 이 때문

$$w_i \cdot \tilde{w_k} \approx \log{P({k\mid i})} = \log{P_{ik}}$$
>[!note]
># 왜 이렇게 하면 좋은 임베딩이 되는가?
>핵심은 $P_{ik}$에 이미 단어의 의미에 대한 정보가 들어 있기 때문이다.
> ># 분포 가설
> >비슷한 문맥에서 등장하는 단어는 비슷한 의미를 갖는 경향이 있다
>
> 코퍼스에서 나타나는 단어들의 관계를 작은 벡터만으로 재현할 수 있는 표현이 좋은 임베딩이라고 볼 수 있다.
> 코퍼스 전체의 단어 관게 패턴을 저차원 벡터 공간으로 압축하는 것으로, 압축 규칙으로 $w_i \cdot \tilde{w_k} \approx \log{P_{ik}}$를 쓴다고 봐도 된다.

벡터 $w_i$, $w_j$, $\tilde{w_k}$를 가지고 어떤 함수 $F$를 수행하면 $P_{ik} / P_{jk}$ 가 나온다는 초기 식으로부터 전개를 시작한다
$$F(w_i, w_j, \tilde{w_k}) = \frac{P_{ik}}{P_{jk}}$$
아직 함수 $F$는 정해지지 않았다.

**함수** $F$는 코퍼스에서의 동시 등장 확률의 비율 관계를 벡터 공간의 관계로 대응시키기 위해 도입한 것이므로,
$$F(w_i - w_j, \tilde{w_k}) = \frac{P_{ik}}{P_{jk}}$$
스칼라-벡터 관계를 성립하기 하기 위해
$$F((w_i- w_j)^T\tilde{w_k}) = \frac{P_{ik}}{P_{jk}}$$
중심 단어 $w$와 주변 단어는$w$무작위 선택이므로 둘은 자유롭게 교환될 수 있어야 한다. 이를 위해 F가 [[Homomorphism|준동형]]이 되도록 한다.
$$F(a+b) = F(a)F(b)$$
$a = v_1^Tv_2, b= v_3^Tv_4$
$$F(v_1^Tv_2 + v_3^Tv_4) = F(v_1^Tv_2)F(v_3^Tv_4), \forall v_1,v_2,v_3,v_4 \in V$$
뺄셈과 나눗셈으로 표현
$$F(v_1^Tv_2 - V_3^Tv_4) = \frac{F(v_1^Tv_2)}{F(v_3^Tv_4)}, \forall v_1,v_2,v_3,v_4 \in V$$


이제 이 준동형 식을 이전의 GloVE식에 적용하면
$$F((w_i- w_j)^T\tilde{w_k}) = \frac{F(v_1^Tv_2)}{F(v_3^Tv_4)} = \frac{P_{ik}}{P_{jk}} ~~~~~~~\text{식A}$$
식A에서 우측 두 항에서,
$$F(w_i^T\tilde{w_k}) = P_{ik} = \frac{X_{ik}}{X_i}$$
식A의 좌측 두 항,
$$ F((w_i- w_j)^T\tilde{w_k}) = \frac{F(v_1^Tv_2)}{F(v_3^Tv_4)} $$
는 뺄셈에 대한 준동형식이므로 F의 형태를 이제 찾으면

이는 지수함수이다.
$$exp(w_i^T\tilde{w_k} - w_j^T\tilde{w_k}) = \frac{exp(w_i^T\tilde{w_k})}{exp(w_j^T\tilde{w_k})}$$
$$exp(w_i^T\tilde{w_k}) = P_{ik} = \frac{X_{ik}}{X_i}~~~~\text{식B}$$
식 B로부터
$$
w_i^T\tilde{w}_k
= \log P_{ik}
= \log\left(\frac{X_{ik}}{X_i}\right)
= \log X_{ik} - \log X_i
$$
여기에서, $w_i$와 $\tilde{w}_k$는 두 값의 위치를 서로 바꾸어도 식이 성립해야 한다.
위 식에서는 $\log X_i$ 항이 걸림돌으로, 이 부분만 없다면 이를 성립시킬 수 있는데 $\log X_i$항을 $w_i$에 대한 편향 $b_i$라는 상수항으로 대체하고 대칭을 위해 $\tilde{w}_k$에 대한 편향 $\tilde{b}_k$를 새로이 도입한다. (수학적으로 동일식이 아니라, 대칭을 위해 추가한 것)
$$w_i^T\tilde{w}_k + b_i + \tilde{b}_k = \log{X}_{ik}$$
손실 함수는 다음과 같이 일반화 될 수 있다.
$$\text{Loss Function} = \sum^V_{m,n=1}(w_m^T\tilde{w}_n + b_m + \tilde{b}_n - \log{X}_{mn})^2$$

그러나, $\log{X_{ik}}$에서 $X_{ik} = 0$일 수도 있으므로 최적의 손실함수로는 부족한데, $\log(1+X_{ik})$로 해결할 수는 있으나
동시 등장 행렬 X가 마치 DTM처럼 [[Sparse Representation|희소 행렬]]일 가능성이 높아 $X_{ik}$가 굉장히 낮아 정보에 거의 도움이 안 될 것이다.
따라서 $X_{ik}$에 영향을 받는 가중치 함수 $f(X_{ik})$를 손실 함수에 도입한다.
![[GloVe 가중치 함수.png]]
비례하되, 최대값이 정해져 있다.

가중치 함수 $f(x)$
$$f(x) = \min(1, (x/x_\text{max})^{3/4})$$
최종적인 손실함수는
$$\text{Loss function} = \sum^V_{m,n=1} f(X_{mn}) (w_m^T\tilde{w}_n + b_m + \tilde{b}_n - \log{X}_{mn})^2$$

