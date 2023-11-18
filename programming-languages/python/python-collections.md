# Python collections

## Counter

Counter is a `defaultdict(lambda: 0)`

```python
from collections import Counter

counter = Counter("mississippi")
# counter := Counter({'i': 4, 's': 4, 'p': 2, 'm': 1})

counter['a'] += 1
# counter := Counter({'i': 4, 's': 4, 'p': 2, 'm': 1, 'a': 1})
```
