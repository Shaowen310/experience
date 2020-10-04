# PyTorch Evaluation

## Training/evaluation environment

`model.train()`

`model.eval()`

changes the `forward()` behaviour of the module it is called upon eg, it changes the behaviour of dropout and batch normalisation layers.

## Enable/disable gradient calculation

`inputs.requires_grad_()`

`output.detach()`

`with torch.no_grad():`



