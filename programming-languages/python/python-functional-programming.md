# Python Stream

## Generators

Generators are iterators, but **you can only iterate over them once**.

### Yield

`yield` returns a generator.

The first time the `for` calls the generator object created from your function, it will run the code in your function from the beginning until it hits `yield`, then it’ll return the first value of the loop. Then, each other call will run the loop you have written in the function one more time, and return the next value, until there is no value to return.

The generator is considered empty once the function runs but does not hit yield anymore. It can be because the loop had ended, or because you do not satisfy a “if/else” anymore.

#### Example

```python
def simpleGeneratorFunc(): 
    yield 1
    yield 2
    yield 3
  
# Driver code to check above generator function
for value in simpleGeneratorFunc():  
    print(value)
```

Output

```bash
1
2
3
```

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

## Iterator

### next

#### Example

```python
gen_int = generate_int()
next(gen_int)
# 0
next(gen_int)
# 1
next(gen_int)
# 2
```

## Collectors

### Constructors

```python
list(iterable)
tuple(iterable)
set(iterable)
dict(iterable)
```

### Reduce

`Reduce` applies a rolling computation to sequential pairs of values in a list. One example is to compute the product of a list of integers.

#### Example

```python
from functools import reduce
product = reduce((lambda x, y: x * y), [1, 2, 3, 4])

# Output: 24
```

## References

1. [Stack Overflow: What does the “yield” keyword do?](https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do)
2. [Python Tips: Map, Filter and Reduce](https://book.pythontips.com/en/latest/map_filter.html)
3. [Python Documentation: Built-in Functions](https://docs.python.org/3/library/functions.html)

