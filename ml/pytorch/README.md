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

high: int - exclusive

size: tuple

### Type conversion

#### Data type

```python
Torch.long()
Torch.float()
```

#### require\_grad flag

[`torch.tensor()`](https://pytorch.org/docs/stable/generated/torch.tensor.html#torch.tensor) always copies `data`. 

If you have a Tensor `data` and just want to change its `requires_grad` flag, use [`requires_grad_()`](https://pytorch.org/docs/stable/tensors.html#torch.Tensor.requires_grad_) or [`detach()`](https://pytorch.org/docs/stable/autograd.html#torch.Tensor.detach) to avoid a copy. 

#### Tensor and numpy array

Use [`torch.as_tensor()`](https://pytorch.org/docs/stable/generated/torch.as_tensor.html#torch.as_tensor) to convert a numpy array to a tensor without copying data.

Use `Tensor.numpy()` to convert a tensor to a numpy array.

#### Tensor and python number

Use `Tensor.item()` to convert a one-element tensor to a python number.

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

## References

1. [PyTorch Doc tensor](https://pytorch.org/docs/stable/tensors.html)

