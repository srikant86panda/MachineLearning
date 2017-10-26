# Support Vector Machine(SVM)

## Advantage of SVM:
* Memory efficient.
* Effective in higher dimension dataset.
* Effective when number of feature are greater then sample size.
* Different kernel function for different decision function.
* Different kernel can be added to achieve complex function.

## Disadvantage of SVM:
* Doesn’t perform well, when we have large data set because the required training time is higher
*	Doesn’t perform very well, when the data set has more noise i.e. target classes are overlapping
*	Doesn’t directly provide probability estimates,

## Tunning parameters for SVM

### Kernel Types:
*	Linear
*	sigmoid
*	RBF
*	Polynomial

### C 
* For large values of C, the penalty for misclassifying points is very high, so the decision boundary will perfectly separate the data if possible. So risking of overfitting.
* Smaller value of C means penalty for misclassifying points is low, so the model may not fully learn leading to underfitting.
### Gamma
* For a low gamma, the model will be too constrained and include all points of the training dataset, without really capturing the shape. for a higher gamma, the model will capture the shape of the dataset well.



