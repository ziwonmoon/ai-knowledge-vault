---
aliases:
  - .. in ..
---
[[Term Frequency-Inverse Document Frequency|TF-IDF]]에서 나온 코드
```python
for doc in docs:
	df += t in docs
```

`df += t in docs`는 도데체 뭔가?
할당보다 in 이 먼저 계산되는 연산자.
t in docs 는 docs안에 t가 존재하는지, 존재한다면 true(1) 아니면 false(0)