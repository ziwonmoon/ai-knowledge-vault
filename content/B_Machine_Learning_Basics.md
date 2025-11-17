

[공부노트 - Pytorch Deep Learning](공부노트%20-%20Pytorch%20Deep%20Learning.md) 

https://github.com/ziwonmoon/Study_PyTorch_DeepLearning/tree/main/B_Machine_Learning_Basics

### Dataset

- Training Dataset
- Test Dataset

### Linear Regression

$$
H(s) = Wx+b
$$

W : Weight (가중치)

b : Bias (편향)

선형 회귀에 가장 적합한 비용 함수는 MES, 옵티마이저는 Gradient Descent

### Cost Function

**cost function(비용 함수) = loss function(손실 함수)** = error function(오차 함수) = objective function(목적 함수)

다 같은 용어임

MES : Mean Squared Error *분산이랑 비슷함*

Cost Function : MES, MAE 등 다양한 오차 함수 사용

### Optimizer - Gradient Descent

경사 하강법 : Cost Function 을 최소화하는 방법

Cost Function을 미분하여 구함

예시) Bias는 무시하고, Weight 만 찾는 방법

$$
gradient = \frac{\partial cost(W)}{W}
$$

$$
W:=W-\alpha\times gradient
$$

α : Learning Rate. 

### Sample

전체 훈련 데이터를 셀 수 있는 하나의 단위

### Feature (특성)

각 샘플에서 y를 결정하게 하는 각각의 독립 변수 x의 개수

## Example Python Code

### Implementing a Model in a Class

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

## Mini Batch Gradient Descent

Mini batch gradient descent : 미니 배치 단위로 경사 하강법을 수행

속도 빠름. 최적값 수렴 안정성 조금 낮음

Batch gradient descent : 전체 데이터에 대해 한 번에 경사 하강법을 수행

계산량 많음. 최적값 수렴 안정성 높음

## Iteration
한 번의 Epoch 내에서 이루어지는 가중치의 업데이트 횟수

![image.png](Itration-Batch-and-Epoch.png)

# Revisiting Vectors and Matrices

[Calculation of Vectors and Matrices](Calculation%20of%20Vectors%20and%20Matrices.md)