# Machine learning basics

## Underfitting/Overfitting

Underfitting -&gt; High bias

Overfitting -&gt; High variance

### Solution for overfitting

**Training-validation-test split**

The training dataset is used to tune parameters.

The validation dataset is used to tune the model hyperparameters.

#### Cross validation

**Training-test split**

Randomly choose X% of the training dataset to be the actual training set and the remaining to be the validation set for each round, and iterate multiple rounds.

Test data should not used for training. It is for evaluation purpose only.

## References

1. [About Train, Validation and Test Sets in Machine Learning](https://towardsdatascience.com/train-validation-and-test-sets-72cb40cba9e7)

