# Advantage of Decision Tree:
* Can handle learge datasets.
* Cna handle mixed predictors- Quantitative & qualitative.
* Easily ignore redundant variables.
* Handle missing of data elegantly through surrogate splits.
* Small tree are easy to interpret.
# Advantage of Decision Tree:
* Large tree are hard to interpret.
* Prediction performance in oftern poor because of high variance.
# Bagging:
* Bagging or bootstrap aggregation averages to many bootstrap sample to reduce its variance.
* Bagging reduces error by variance reduction.
# Random Forest:
* Refinement of bagged trees.
* More unrelated treed averaging bring down the variance.
* At each split random sample of m features are drawn and only those m features are used for splitting.
* For each tree grown on bootstrap sample the error rate for opservation left out of the bootstrap sample is monitored and this is called as out of bag error rate.
* There is no way we can overfit.
* Adds trees with equal weights.
# Boosting:
```This is an ensemble method that seeks to create a strong classifier (model) based on “weak” classifiers. In this context, weak and strong refer to a measure of how correlated are the learners to the actual target variable. By adding models on top of each other iteratively, the errors of the previous model are corrected by the next predictor, until the training data is accurately predicted or reproduced by the model.```
* Averages of many trees each grown to re-weighted versions of the training data.
* Wighting decorrelates the trees by focusing on the regions missed by past trees.
* Final classifies is weighted average of calssifiers.
* Boosting does not only uses training error on basis of learning the trees.
* Stagewise fitting(no backfitting like neural networks) slow downs overfitting.
* Shrinkage further slow downs overfitting.
* Chances of overfitting.
* Stumps does the best.
* Depth of the controls interaction order of the model.
* Boosted stumps via dragient boosting returns reasonable approximations to the quadratic function thats why single stumps works the best.
* Boosting some time adds tree with variable weights.
* Decission stump are good as they have low variance and does not overfit.
# AdaBoost:
## Data preparation for AdaBoost:
This section lists some heuristics for best preparing your data for AdaBoost.
• Quality Data: Because the ensemble method continues to attempt to correct misclassifications in the training data, you need to be careful that the training data is of a high-quality.
• Outliers: Outliers will force the ensemble down the rabbit hole of working hard to correct for cases that are unrealistic. These could be removed from the training dataset.
• Noisy Data: Noisy data, specifically noise in the output variable can be problematic. If possible, attempt to isolate and clean these from your training dataset.
# XGBoost:
```Gradient boosting also comprises an ensemble method that sequentially adds predictors and corrects previous models. However, instead of assigning different weights to the classifiers after every iteration, this method fits the new model to new residuals of the previous prediction and then minimizes the loss when adding the latest prediction. So, in the end, you are updating your model using gradient descent and hence the name, gradient boosting.```
* This is supported for both regression and classification problems. 
* XGBoost specifically, implements this algorithm for decision tree boosting with an additional custom regularization term in the objective function.
# PostProcessing ensembles using Lassso:(using glmnet)
