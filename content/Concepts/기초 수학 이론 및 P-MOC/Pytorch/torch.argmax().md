최대값의 인덱스 반환.

``` Python
import torch

# 예시: 3개 샘플(행), 4개 클래스(열)의 확률 텐서
probabilities = torch.tensor([
    [0.1, 0.8, 0.05, 0.05], # Sample 1: 클래스 1이 가장 높음 (인덱스 1)
    [0.9, 0.0, 0.1, 0.0],   # Sample 2: 클래스 0이 가장 높음 (인덱스 0)
    [0.2, 0.3, 0.4, 0.1]    # Sample 3: 클래스 2가 가장 높음 (인덱스 2)
])

# dim=1 (클래스 축)을 따라 최댓값 인덱스를 찾음
predicted_classes = torch.argmax(probabilities, dim=1) 

print(predicted_classes) 
# 출력: tensor([1, 0, 2]) -> 이 모델의 최종 예측 결과입니다.
```

