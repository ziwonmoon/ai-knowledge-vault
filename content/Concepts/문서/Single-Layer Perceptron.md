# 개요
![[Single-Layer Perceptron.png]]
입력층과 출력층 두 레이어만 있음.

단층 퍼셉트론으로 AND, NAND, OR 게이트를 쉽게 구현할 수 있음

# 단층 퍼셉트론으로는 XOR 게이트는 구현할 수 없다.

| AND Gate                             | NAND Gate                            |
| ------------------------------------ | ------------------------------------ |
| ![[AND Gate Plot.png]]               | ![[NAND Gate Plot.png]]              |
| OR Gate                              | XOR Gate                             |
| ![[OR Gate Plot.png]] | ![[XOR Gate Plot.png]] |

>단층 퍼셉트론은 직선 하나로 두 영역을 나눌 수 있는 문제에서만 답을 구할 수 있다.
>**단층 퍼셉트론은 선형 영역에 대해서만 분리가 가능하다**

*XOR Gate는 곡선, 비선형 영역으로 분리하면 구현이 가능함*
![[XOR Gate Non-Linear Plot.png]]

