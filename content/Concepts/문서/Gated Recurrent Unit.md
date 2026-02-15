---
aliases:
  - GRU
---
# 개요
[[Long Short-Term Memory|LSTM]]에는 입력, 출력, 삭제의 3개의 게이트가 존재하는 반면 GRU에는 업데이트 게이트와 리셋 게이트 2개의 게이트가 존재함.

GRU는 LSTM과 성능은 비슷하지만, 속도는 더 빠르다고 알려져있음.
그러나 기존에 LSTM이용하며 최적의 하이퍼파라미터까지 찾았다면 굳이 GRU로 바꿔서 사용할 필요는 없음

경험적으로 데이터 양이 적을때는 GRU, 데이터 양이 많아지면 LSTM이 낫다고 함

# 수식
![[GRU layout.png]]$$r_t = \sigma(W_{xr}x_t + W_{hr}h_{t-1} + b_r)$$$$z_t = \sigma(W_{xz}x_t + W_{hz}h_{t-1} + b_x)$$
$$g_t = tanh(W_{hg}(r_t \circ h_{t-1}) + W_{xg}x_t+b_g)$$
$$h_t = (1-z_t)\circ g_t + z_t \circ h_{t-1}$$
