# LSTM

## Import

`torch.nn.lstm` 

## Model Arguments

| Argument | Description |
| :--- | :--- |
| input\_size | n\_features |
| batch\_first | See training |

## Training

`output, (hidden, cell) = lstm(x, (hidden, cell) )` 

### Arguments

| Argument | Description |
| :--- | :--- |
| x | \(seq\_len, batch\_size, input\_size\) |
|  | if batch\_first==True, \(batch\_size, seq\_len, input\_size\) |

### Output

| Variable | Description |
| :--- | :--- |
| output | \(seq\_len, batch\_size, hidden\_size\) |
|  | if batch\_first==True, \(batch\_size, seq\_len, hidden\_size\) |



