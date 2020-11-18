# PyTorch LSTM

## Model Arguments

`lstm_layer = nn.LSTM(*args, **kwargs)`

| Argument | Description |
| :--- | :--- |
| input\_size | n\_features |
| hidden\_size | See training |
| num\_layers | Number of recurrent layers |
| batch\_first | See training |
| dropout | dropout ratio |

## Training

`hidden_seq, (hidden_final, cell_final) = lstm(x_seq, (hidden_init, cell_init))` 

### Arguments

| Argument | Description |
| :--- | :--- |
| x\_seq | \(seq\_len, batch\_size, input\_size\) |
|   | if batch\_first==True, \(batch\_size, seq\_len, input\_size\) |

### Output

| Variable | Description |
| :--- | :--- |
| hidden\_seq | \(seq\_len, batch\_size, hidden\_size \* n\_directions\) |
|   | if batch\_first==True, \(batch\_size, seq\_len, hidden\_size \* n\_directions\) |

## With Embedding

```python
class recurrent_net(nn.Module):

    def __init__(self, hidden_size):
        super(three_layer_recurrent_net, self).__init__()
        
        self.layer1 = nn.Embedding(vocab_size, hidden_size)
        self.layer2 = nn.LSTM(hidden_size, hidden_size)
        self.layer3 = nn.Linear(hidden_size, vocab_size)

        
    def forward(self, word_seq, h_init, c_init ):
        
        g_seq = self.layer1(word_seq)  
        h_seq, (h_final,c_final) = self.layer2(g_seq , (h_init,c_init))      
        score_seq = self.layer3(h_seq)
        
        return score_seq, h_final, c_final
```

