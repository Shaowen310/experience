# Python Generators

 Generators are iterators, but **you can only iterate over them once**.

## Yield

`yield` returns a generator.

The first time the `for` calls the generator object created from your function, it will run the code in your function from the beginning until it hits `yield`, then it’ll return the first value of the loop. Then, each other call will run the loop you have written in the function one more time, and return the next value, until there is no value to return.

The generator is considered empty once the function runs but does not hit yield anymore. It can be because the loop had ended, or because you do not satisfy a “if/else” anymore.

### Example

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

## References

1. [Stack Overflow: What does the “yield” keyword do?](https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do)

