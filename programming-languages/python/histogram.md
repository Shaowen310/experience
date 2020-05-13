# Python Histogram

## Counting elements

### No library

```python
def hist(seq) -> dict:
    """Tally elements from `seq`."""
    hist = {}
    for i in seq:
        hist[i] = hist.get(i, 0) + 1
    return hist

hist = hist(seq)
```

### collection.Counter

```python
from collections import Counter

hist = Counter(seq)
```

## References

1. [5 种方法教你用 Python 玩转 histogram 直方图](https://blog.csdn.net/weixin_33858485/article/details/87989778)

