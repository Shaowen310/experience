# Light GBM

## Introduction

Light BGM is gradient boosting tree based, and it grows tree leaf-wise (DFS).

## Limitation

Not advisable to use LGBM on small datasets[1]. Light GBM is sensitive to overfitting and can easily overfit small data. Mandot[1] suggests to use it for data with at least 10,000 rows.

## Usage notes

1. Implementation is easy, but parameter tuning is difficult[1].

## Parameters Tuning

### Parameters

### Tuning

To get good results using a leaf-wise tree, these are some important parameters:

`num_leaves`

This is the main parameter to control the complexity of the tree model. Theoretically, we can set num_leaves = 2^(max_depth) to obtain the same number of leaves as depth-wise tree. However, this simple conversion is not good in practice. The reason is that a leaf-wise tree is typically much deeper than a depth-wise tree for a fixed number of leaves. Unconstrained depth can induce over-fitting. Thus, when trying to tune the num_leaves, we should let it be smaller than 2^(max_depth). For example, when the max_depth=7 the depth-wise tree can get good accuracy, but setting num_leaves to 127 may cause over-fitting, and setting it to 70 or 80 may get better accuracy than depth-wise.

`min_data_in_leaf` 

This is a very important parameter to prevent over-fitting in a leaf-wise tree. Its optimal value depends on the number of training samples and num_leaves. Setting it to a large value can avoid growing too deep a tree, but may cause under-fitting. In practice, setting it to hundreds or thousands is enough for a large dataset.

`max_depth`

You also can use max_depth to limit the tree depth explicitly.

#### For Faster Speed:

* Use bagging by setting bagging_fraction and bagging_freq
* Use feature sub-sampling by setting feature_fraction
* Use small max_bin
* Use save_binary to speed up data loading in future learning
* Use parallel learning, refer to parallel learning guide.

#### For better accuracy:

* Use large max_bin (may be slower)
* Use small learning_rate with large num_iterations
* Use large `num_leaves` (may cause over-fitting)
* Use bigger training data
* Try `dart`
* Try to use categorical feature directly

#### To deal with over-fitting:

* Use small max_bin
* Use small num_leaves
* Use min_data_in_leaf and min_sum_hessian_in_leaf
* Use bagging by set bagging_fraction and bagging_freq
* Use feature sub-sampling by set feature_fraction
* Use bigger training data
* Try `lambda_l1`, `lambda_l2` and `min_gain_to_split` to regularization
* Try `max_depth` to avoid growing deep tree

## Reference

1. [What is LightGBM, How to implement it? How to fine tune the parameters?](https://medium.com/@pushkarmandot/https-medium-com-pushkarmandot-what-is-lightgbm-how-to-implement-it-how-to-fine-tune-the-parameters-60347819b7fc)

2. [LightGBM's documentation](https://lightgbm.readthedocs.io/en/latest/)
