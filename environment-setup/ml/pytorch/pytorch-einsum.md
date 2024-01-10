# PyTorch einsum

{% embed url="https://stackoverflow.com/questions/55894693/understanding-pytorch-einsum" %}

**1) Matrix multiplication**\
Previously: `torch.matmul(aten, bten)` ; `aten.mm(bten)`\
einsum: `np.einsum("ij, jk -> ik", arr1, arr2)`

**11) Batch Matrix Multiplication**\
Previously: `torch.bmm(batch_tensor_1, batch_tensor_2)`\
einsum: `np.einsum("bij, bjk -> bik", batch_tensor_1, batch_tensor_2)`

```
# input batch tensors to work with
In [13]: batch_tensor_1 = torch.arange(2 * 4 * 3).reshape(2, 4, 3)
In [14]: batch_tensor_2 = torch.arange(2 * 3 * 4).reshape(2, 3, 4) 

In [15]: torch.bmm(batch_tensor_1, batch_tensor_2)  
Out[15]: 
tensor([[[  20,   23,   26,   29],
         [  56,   68,   80,   92],
         [  92,  113,  134,  155],
         [ 128,  158,  188,  218]],

        [[ 632,  671,  710,  749],
         [ 776,  824,  872,  920],
         [ 920,  977, 1034, 1091],
         [1064, 1130, 1196, 1262]]])

# sanity check with the shapes
In [16]: torch.bmm(batch_tensor_1, batch_tensor_2).shape 
Out[16]: torch.Size([2, 4, 4])
```

