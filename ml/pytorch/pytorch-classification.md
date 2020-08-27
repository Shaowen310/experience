# PyTorch Classification

## Softmax vs LogSoftmax

### Softmax

`torch.nn.Softmax(dim: Optional[int] = None)`

`torch.nn.functional.softmax(x, dim: Optional[int] = None)`

$$
\mathrm{Softmax}(x_i) =\frac{\exp(x_i)}{\sum_j \exp(x_j)}
$$

### LogSoftmax

`torch.nn.LogSoftmax(dim: Optional[int] = None)`

`torch.nn.functional.log_softmax(x, dim: Optional[int] = None)`

$$
\mathrm{LogSoftmax}(x_i) =\log(\frac{\exp(x_i)}{\sum_j \exp(x_j)})
$$



