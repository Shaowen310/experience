# PyTorch Classification

## Binary Classification

### Sigmoid

`torch.nn.Sigmoid()`

$$
\mathrm{Sigmoid}(x) = \frac{1}{1+\mathrm{exp}(-x)}
$$

### Loss functions

`loss = criterion(input, target)`

`torch.nn.BCELoss(weight: Optional[torch.Tensor] = None, reduction: str = 'mean')`

`torch.nn.BCEWithLogitsLoss(weight: Optional[torch.Tensor] = None, reduction: str = 'mean')`

_target_ should be numbers between 0 and 1. Type torch.float

### Relationships

The following are equivalent

* Sigmoid + BCELoss
* BCEWithLogitsLoss

## Multi-class Classification

### Softmax and LogSoftmax

#### Softmax

`torch.nn.Softmax(dim: Optional[int] = None)`

`torch.nn.functional.softmax(x, dim: Optional[int] = None)`

$$
\mathrm{Softmax}(x_i) =\frac{\exp(x_i)}{\sum_j \exp(x_j)}
$$

#### LogSoftmax

`torch.nn.LogSoftmax(dim: Optional[int] = None)`

`torch.nn.functional.log_softmax(x, dim: Optional[int] = None)`

$$
\mathrm{LogSoftmax}(x_i) =\log(\frac{\exp(x_i)}{\sum_j \exp(x_j)})
$$

### Loss functions

`loss = criterion(input, target)`

#### Negative Log-Likelihood Loss

`torch.nn.NLLLoss(weight: Optional[torch.Tensor] = None, reduction: str = 'mean')`

The _input_ given through a forward call is expected to contain log-probabilities of each class. input has to be a Tensor of size either \(minibatch, C\) or \(minibatch, C, $d\_1$, $d\_2$, ..., $d\_K$\) with K ≥ 1 for the K-dimensional case.

The _target_ that this loss expects should be a class index in the range \[0,C−1\] where C = number of classes. Type torch.long

Loss for an instance

$$l_n = - w_{y_n} x_{n,y_n}$$

What it does is just taking the negative of the log-probability corresponding to the ground truth class. The goal is to make the inferenced probability distribution fit the ground truth probability distribution.

#### Cross Entropy Loss

`torch.nn.CrossEntropyLoss(weight: Optional[torch.Tensor] = None, reduction: str = 'mean')`

### Relationships

The following are equivalent

* Softmax + Log + NLLLoss
* LogSoftmax + NLLLoss
* CrossEntropyLoss

## Notes

Possible to use CrossEntropyLoss for binary classification, but the _target_ should be ground-truth labels.

