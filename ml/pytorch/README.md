# PyTorch

## Tensor

### Initialisation

#### torch.Tensor vs torch.tensor

`torch.Tensor` overloads `torch.tensor` and `torch.empty` 

`torch.tensor(data)` initialise a tensor with data

`torch.empty(size)` initialise a tensor with size, size is tuple

Using `torch.tensor` and `torch.empty` is preferred.

### Transformation

#### Reshape

```python
torch.view(dim0, dim1, ...)
```

### Random indices

#### randint

`torch.randint(low=0, high, size)`

_high_ \(int\) - exclusive

_size_ \(int...\)

#### randperm

`torch.randperm(n, dtype=torch.int64, layout=torch.strided)`

### Type conversion

#### Data type

```python
Tensor.long()
Tensor.float()
```

#### Tensor and numpy array

Use [`torch.as_tensor()`](https://pytorch.org/docs/stable/generated/torch.as_tensor.html#torch.as_tensor) to convert a numpy array to a tensor without copying data.

Use `Tensor.numpy()` to convert a tensor to a numpy array without copying data.

Note: if conversion is done using the methods mentioned above, modification of a numpy array also changes the corresponding PyTorch tensor.

#### Tensor and python number

Use `Tensor.item()` to convert a one-element tensor to a python number.

### require\_grad flag

[`torch.tensor()`](https://pytorch.org/docs/stable/generated/torch.tensor.html#torch.tensor) always copies `data`. 

If you have a Tensor `data` and just want to change its `requires_grad` flag, use [`requires_grad_()`](https://pytorch.org/docs/stable/tensors.html#torch.Tensor.requires_grad_) or [`detach()`](https://pytorch.org/docs/stable/autograd.html#torch.Tensor.detach) to avoid a copy. 

## NN

### Weight transfer

```python
net.weight.data.copy_(w)
```

### Gradient accumulation

Gradient accumulation is on by default. Use `optimizer.zero_grad()` to stop gradient accumulation.

### Deterministic networks

```python
torch.manual_seed(SEED)
torch.backends.cudnn.deterministic = True
```

## References

1. [PyTorch Doc tensor](https://pytorch.org/docs/stable/tensors.html)
2. [Stack Overflow: What is the difference between torch.tensor and torch.Tensor?](https://stackoverflow.com/questions/51911749/what-is-the-difference-between-torch-tensor-and-torch-tensor)

