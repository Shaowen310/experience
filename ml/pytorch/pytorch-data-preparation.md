# PyTorch Data Preparation

## Minibatch

```python
shuffled_indices = torch.randperm(n_samples)
for i in range(0, n_samples, bs):
    indices = shuffled_indices[i:i+bs]
    minibatch_data = train_data[indices]
    minibatch_label = train_label[indices]
```

