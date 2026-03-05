---
aliases:
  - SGD
---
# 개요
[[Gradient Descent|경사 하강법]]의 확률적(Stochastic) 변형

# 일반적인 [[Gradient Descent]]와의 비교
| 경사 하강법                                             | SGD                                                           |
| -------------------------------------------------- | ------------------------------------------------------------- |
| 매 스텝마다 전체 데이터셋의 평균 Gradient 계산해서 업데이트              | 매 스텝마다 데이터 한 개 또는 작은 샘플로 Gradient를 근사해서 업데이트                  |
| 안정적이지만 데이터가 크면 계산이 매우 느림                           | 훨씬 빠르지만 Gradient가 노이즈가 있어서 경로가 흔들림                            |
| $\theta \leftarrow \theta - \eta \nabla L(\theta)$ | $\theta \leftarrow - \eta \nabla L_i(\theta)$<br>(i번째 샘플만 사용) |

# 여담
실제 딥러닝에서는 이 중간 형태인 Mini-batch Gradient Descent를 사용한다.
* 1개 샘플 - SGD
* 전체 데이터 - GD
* 32, 64, 128개 묶음 - Mini-Batch GD

