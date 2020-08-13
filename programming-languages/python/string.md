# Python String

## Single Quote or Double Quote

No difference.

## String Types

### Raw string

```python
print(r"Hello\nworld")
```

The output for code above is `Hello\nworld` and `\n` will not be interpreted.

Raw string is usually used for regex.

### Unicode string

```python
str = u'hello'
```

It is redundant in Python 3 as the default string type is Unicode. Versions 3.0 through 3.2 removed them, but they were [re-added in 3.3+](https://www.python.org/dev/peps/pep-0414/) for compatibility with Python 2 to aid the 2 to 3 transition.

## String Concatenation

### join\(\)

Preferred

```python
str = ''.join([str_a, str_b])
```

### +

```python
str = str_a + str_b
```

## References

1. [Stack Overflow: What's the u prefix in a Python string?](https://stackoverflow.com/questions/2464959/whats-the-u-prefix-in-a-python-string)

