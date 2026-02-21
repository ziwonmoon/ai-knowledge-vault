---
aliases:
  - view
---

텐서의 Shape 변경. 실제 메모리 구조는 변환되지 않고 메타데이터만 변경되므로 빠르다.

example
```python
x = torch.tensor([[1, 2, 3], [4, 5, 6]])
print(x.view(6))
# [1, 2, 3, 4, 5, 6]
```

인자 -1 : 알아서 해 주세요

```python
x = torch.tensor([[1, 2, 3], [4, 5, 6]])
print(x, view(3, 2, -1))
# [[[1], [2]], [[3], [4]], [[5], [6]]]
```