# Python List Set Dict

## Dict

### Key existence

#### in

```python
if 'key1' in d:
    print('key:"key1" exists')
```

#### get

If a default value is required

```python
d.get(key, 0)
```

### Traversing

```python
D1 = {1:'a', 2:'b', 3:'b'} 
for k in D1.keys():
   print(k, D1[k])
for k, v in D1.items():
   print(k, v)
for v in D1.values():
   print(v)
   # ['a', 'b']
```

### Sorting

#### Sort by keys

```python
sorted(d.keys(), reverse=False)
```

#### Sort by values

```python
sorted(d.items(), key=lambda item:item[1])
```

### Construction

#### Index map

Index to object map. Prefer to use a list if index starts from 0.

```python
dict(enumerate(lst, start=0))
```

Object to index map, or reverse map

```python
inv_map = {v: k for k, v in enumerate(lst, start=0)}
```

## References

1. [python 的 sorted 函数对字典按 key 排序和按 value 排序](https://blog.csdn.net/tangtanghao511/article/details/47810729)

