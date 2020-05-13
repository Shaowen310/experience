# Python String

## Single Quote or Double Quote

No difference.

## Raw String

```python
print(r"Hello\nworld")
```

The output for code above is `Hello\nworld` and `\n` will not be interpreted.

## Unicode String

```python
str = u'hello'
```

It is redundant in Python 3 as the default string type is Unicode. Versions 3.0 through 3.2 removed them, but they were [re-added in 3.3+](https://www.python.org/dev/peps/pep-0414/) for compatibility with Python 2 to aid the 2 to 3 transition.

## References

1. [Stack Overflow: What's the u prefix in a Python string?](https://stackoverflow.com/questions/2464959/whats-the-u-prefix-in-a-python-string)

