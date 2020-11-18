# PyTorch Evaluation

## Training/Evaluation Environment

`model.train()`

`model.eval()`

changes the `forward()` behaviour of the module it is called upon eg, it changes the behaviour of dropout and batch normalisation layers.

## Enable/Disable Gradient Calculation

`inputs.requires_grad_()`

`output.detach()`

`with torch.no_grad():`



