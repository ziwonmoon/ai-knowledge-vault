---
date created: Wednesday, March 18th 2026, 10:35:23 am
date modified: Wednesday, March 18th 2026, 10:49:08 am
---
`map(len, data)` : data안의 각 원소에 대해 len()을 적용하라
iterator 형태로 len이 적용된 값이 반환됨 `[3, 2, 1]`

같은 걸 이렇게도 쓸 수 있다.
```python
[len(x) for x in tokenized_data]
```
