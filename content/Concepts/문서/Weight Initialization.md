---
aliases:
  - 가중치 초기화
date created: Friday, February 13th 2026, 5:41:33 pm
date modified: Tuesday, March 17th 2026, 2:31:27 pm
---
가중치가 초기에 어떤 값을 가졌느냐에 따라서 모델의 훈련 결과가 달라진다
그렇다고 모든 값을 0으로 두고 시작하냐?
그건 아니다. 모든 뉴런이 동일한 값을 출력하고 모든 그라디언트가 동일하고 업데이트가 같고.. 그러니까 랜덤 초기화가 필요하다.

근데 진짜 랜덤은 되냐? 그건또아니다. 기울기 소실이 발생하기가 매우 쉽기 때문에



![[Xavier Initialization]]

![[He Initialization]]