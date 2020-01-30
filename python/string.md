# Python string

## String comparison

Python string comparison is performed using the characters in both strings. The characters in both strings are compared one by one. When different characters are found then their Unicode value is compared. The character with lower Unicode value is considered to be smaller.

Examples:

```python
fruit1 = 'Apple'

print(fruit1 == 'Apple')
```

Output:

```text
True
```

## Raw string

```python
print(r"Hello\nworld")
```

The output for code above is "Hello\nworld" and "\n" will not be interpreted.

