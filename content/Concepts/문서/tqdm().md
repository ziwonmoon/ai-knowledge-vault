---
date created: Wednesday, March 18th 2026, 10:27:29 am
date modified: Wednesday, March 18th 2026, 10:29:46 am
---
```python
from tqdm import tqdm

for i in tqdm(range(10000)):
	...
```

tqdm(iterable)
이렇게 래핑하여 사용하면 간단하게 프로그레스 바가 표시됨.