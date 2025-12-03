nn.Module 층을 차례로 쌓을 수 있도록 함.

```
nn.Sequential(
	nn.Linear(2, 1),
	nn.Sigmoid()
)
```

생성하는 `nn.Sequential`객체는 `nn.Module`을 상속받음


``` Python
model = nn.Sequential(
	nn.Linear(2, 2),  #Input > Hidden
	nn.LeakyReLU(),
	nn.Linear(2, 1),  #Hidden > Output
	nn.Sigmoid()
	).to(device)
```
햇갈릴 수 있지만 이건 3-Layers 구조임
* 활성화 함수는 안 셈
* 함수 전후로 한 계층씩인거임.
보통은 3계층이라고 보긴하는데 다른 방법으로 보면 2-Layers 이기도 함 ㅋㅋ 너무 신경쓰지마. 