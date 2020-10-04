# PyTorch Template

## Configuration

```python
device = torch.device("cuda")
model.to(device)
criterion = nn.CrossEntropyLoss()
```

## Training

```python
for epoch in range(n_epochs):
    # learning rate strategy : divide the learning rate by 1.5 every 10 epochs
    if epoch%10 == 0 and epoch > 10: 
        lr = lr/1.5
    
    # create a new optimizer at the beginning of each epoch: give the current learning rate.   
    optimizer=torch.optim.SGD(net.parameters(), lr=lr)
    
    running_loss = 0
    num_batches = 0
    
    shuffled_indices = torch.randperm(n_samples)
    
    for i in range(0, n_samples, bs):
        optimizer.zero_grad()
    
        indices = shuffled_indices[i:i+bs]
        minibatch_data = train_data[indices]
        minibatch_label = train_label[indices]
        
        minibatch_data = minibatch_data.to(device)
        minibatch_label = minibatch_label.to(device)
    
        inputs = minibatch_data.view(bs,784)
        inputs.requires_grad_()
    
        scores = model(inputs)
    
        loss = criterion(scores, minibatch_label)
        loss.backward()
        optimizer.step()
    
        running_loss += loss.detach().item()
    
        num_batches+=1
    
total_loss = running_loss/num_batches
```

## Evaluation

```python
for epoch in range(n_epochs):    
    # create a new optimizer at the beginning of each epoch: give the current learning rate.   
    optimizer=torch.optim.SGD( net.parameters() , lr=lr )
    
    running_loss = 0
    num_batches = 0
    
    model.eval()
    with torch.no_grad():
        for i in range(0, n_samples, bs):
            minibatch_data = test_data[i:i+bs]
            minibatch_label = test_label[i:i+bs]
        
            inputs = minibatch_data.view(bs,784)
        
            scores = model(inputs)
        
            loss = criterion(scores, minibatch_label)
        
            running_loss += loss.item()
        
            num_batches+=1
    model.train()
    
total_loss = running_loss/num_batches

```

## References

1. [https://github.com/xbresson/CE7454\_2020](https://github.com/xbresson/CE7454_2020)

