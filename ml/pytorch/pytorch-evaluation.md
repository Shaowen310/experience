# PyTorch Autograd

## Training/Evaluation Environment

#### Sets a model to `train` mode in place

`model.train()`

#### Sets a model to `eval` mode in place

`model.eval()`

#### Differences between `train` and `eval` modes

changes the `forward()` behavior of the module it is called upon eg, it changes the behavior of dropout and batch normalization layers.

## Enable/Disable Gradient Calculation

#### Sets `requires_grad` flag to `True` in place

`inputs.requires_grad_()`

#### Sets `requires_grad` flag to `False` in place

`output.detach_()`

Not in place version

`output = output.detach()`

#### Temporarily sets `requires_grad` flag to `False`

`with torch.no_grad():`

## Weight Update by Gradient for One Iteration

```python
for i in range(n_batches):
    optimizer.zero_grad()
    ...
    loss = criterion(y_pred, y_true)
    
    loss.backward()
    optimizer.step()
```

