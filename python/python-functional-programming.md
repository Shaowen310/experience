# Python functional programming

## Map, Filter and Reduce

### Map

`Map` applies a function to all the items in an input\_list.

#### Blueprint

```python
map(function, iterable) : iterable
```

#### Example

One function, list of items' case

```python
items = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, items))
```

One list of items, list of functions' case

```python
def multiply(x):
    return (x*x)
def add(x):
    return (x+x)

funcs = [multiply, add]
for i in range(5):
    value = list(map(lambda x: x(i), funcs))
    print(value)

# Output:
# [0, 0]
# [1, 2]
# [4, 4]
# [9, 6]
# [16, 8]
```

### Filter

`filter` creates a list of elements for which a function returns true.

#### Example

```python
number_list = range(-5, 5)
less_than_zero = list(filter(lambda x: x < 0, number_list))
print(less_than_zero)

# Output: [-5, -4, -3, -2, -1]
```

The filter resembles a for loop but it is a builtin function and faster.

**Note:** If map & filter do not appear beautiful to you then you can read about `list/dict/tuple` comprehensions.

### Reduce

`Reduce` applies a rolling computation to sequential pairs of values in a list. One example is to compute the product of a list of integers.

#### Example

```python
from functools import reduce
product = reduce((lambda x, y: x * y), [1, 2, 3, 4])

# Output: 24
```

## References

1. [Python Tips: Map, Filter and Reduce](https://book.pythontips.com/en/latest/map_filter.html)

