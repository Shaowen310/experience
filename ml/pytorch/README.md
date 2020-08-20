# PyTorch

## Tensor

### Transformation

```python
torch.view(dim0, dim1, ...)
```

### Random indices

```python
torch.randint(low=0, high, size)
```

high\(int\) - exclusive

size\(tuple\)

## NN

### Weight transfer

```python
net.weight.data.copy_(w)
```

### Deterministic networks

```python
torch.manual_seed(SEED)
torch.backends.cudnn.deterministic = True
```



