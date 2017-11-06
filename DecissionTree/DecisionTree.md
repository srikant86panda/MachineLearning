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
# AdaBoost:

# PostProcessing ensembles using Lassso:(using glmnet)
