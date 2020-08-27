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

## Loss functions

### Negative Log-Likelihood Loss

``
output = loss(input, target)
``

`torch.nn.NLLLoss(weight: Optional[torch.Tensor] = None, reduction: str = 'mean')`

The *input* given through a forward call is expected to contain log-probabilities of each class. input has to be a Tensor of size either (minibatch, C) or (minibatch, C, $d_1$, $d_2$, ..., $d_K$) with K ≥ 1 for the K-dimensional case.

The *target* that this loss expects should be a class index in the range [0,C−1] where C = number of classes.

### Cross Entropy Loss

`torch.nn.CrossEntropyLoss(weight: Optional[torch.Tensor] = None, reduction: str = 'mean')`

## Relationships

The following three networks are equivalent

* Softmax + Log + NLLLoss

* LogSoftmax + NLLLoss

* CrossEntropyLoss
