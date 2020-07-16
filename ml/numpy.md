# Numpy

## Initializtion

```python
np.zeros()
np.empty()
np.full()
np.arange()
np.asarray()
```

## Random

```python
np.random.rand()
np.random.random()
np.random.randint()
```

## Transform

```python
np.reshape()
np.transpose()
```

## Map

```python
np.sum(x1, x2)
np.prod(x1, x2)
```

## Reduction

```python
np.sum(x)
np.prod(x)
np.argmax(x)
np.nanargmax(x)
np.var(x)
np.nanvar(x)
```

### Compare and set

```python
np.clip()
np.where()
```

## Indexing

```python
np._ix()
# Get the nonzero indices of the given input
np.nonzero()
```

### Slicing

```python
# Slice first n rows
arr[:n, :]
# Slice last n rows
arr[:-n, :]
# Slice first n rows, step m
arr[0:n:m, :]
# ... <=> :,:,:...
arr[:n, ...]
```

## Broadcasting utilities

```python
np.repeat()
np.tile()
np.expand_dims()
```

## Item selection

```python
np.where(idx, x, np.nan)
```

## CSV

```python
np.loadtxt()
```

