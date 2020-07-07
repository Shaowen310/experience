# Python Regex

## Search

```python
>>> import re
>>> m = re.search('(?<=abc)def', 'abcdef')
>>> m.group(0)
'def'
```

## References

1. [Library doc: re](https://docs.python.org/3/library/re.html)
2. [Python Regex Partial Replace](https://code.luasoftware.com/tutorials/python/python-regex-partial-replace/)

