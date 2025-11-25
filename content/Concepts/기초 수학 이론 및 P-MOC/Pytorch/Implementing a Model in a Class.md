
지금은 불편해 보여도 이렇게 사용하는 방법 꼭 알아야함

```python
#model = nn.Linear(3, 1)

#nn.Modulue is Callable -> this class is also Callable!
class LinearRegressionModel(nn.Module):
  def __init__(self):
    super().__init__()
    self.linear = nn.Linear(3, 1)

	# nn.Model의 __call__ 안에 self.forward(param) 을 호출시키는 코드가 있음
	# 그래서 이 forward는 내가 명시적으로 호출해야 하는 매서드가 아님
	# model(param)하면 nn.Module의 __call__(param) 실행 -> 거기에서 self.forward(param) 호출
  def forward(self, x):
    return self.linear(x)
    
    
model = LinearRegressionModel()
```


``` Python
class BinaryClassifier(nn.Module):
	def __init__(self):
		super().__init__()
		self.linear = nn.Linear(2, 1)
		self.sigmoid = nn.Sigmoid()

  

def forward(self, x):
	return self.sigmoid(self.linear(x))
```