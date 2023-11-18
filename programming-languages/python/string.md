# Python String

## String constants

```python
string.ascii_letters
string.ascii_lowercase
# abcdefghijklmnopqrstuvwxyz
string.ascii_uppercase
# ABCDEFGHIJKLMNOPQRSTUVWXYZ
string.digits
# 0123456789
string.hexdigits
# 0123456789abcdefABCDEF
string.punctuation
# !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~.
string.whitespace
```

## Str utils

### Judge character type

```python
"str".isalpha()
"str".isdigit()
"str".isalnum()
```

### Trim

```python
"str".strip()
"str".lstrip()
"str".rstrip()
```

### static str.maketrans(x\[ ,y\[, z]])

It returns a translation table for `str.translate()`

`x`: characters that need to be replaced

`y`: characters with which the characters to be replaced

`z`: characters that need to be deleted

## String types

### Raw string

```python
print(r"Hello\nworld")
```

The output for the code above is `Hello\nworld` and `\n` will not be interpreted.

The raw string is usually used for regex.

### Unicode string

```python
str = u'hello'
```

It is redundant in Python 3 as the default string type is Unicode. Versions 3.0 through 3.2 removed them but were [re-added in 3.3+](https://www.python.org/dev/peps/pep-0414/) for compatibility with Python 2 to aid the 2 to 3 transition.

## String concatenation

### join()

Preferred

```python
str = ''.join([str_a, str_b])
```

### +

```python
str = str_a + str_b
```

## Tricks

### Removes punctuations

```python
s.translate(str.maketrans('', '', string.punctuation))
```

## Q & A

### Single Quote or Double Quote

No difference.

## References

1. [Stack Overflow: What's the u prefix in a Python string?](https://stackoverflow.com/questions/2464959/whats-the-u-prefix-in-a-python-string)
