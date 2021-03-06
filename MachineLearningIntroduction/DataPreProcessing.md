# Scaling and Normalization: [source](http://sebastianraschka.com/Articles/2014_about_feature_scaling.html)

## standardization:
The result of standardization (or Z-score normalization) is that the features will be rescaled so that they’ll have the properties of a standard normal distribution with μ=0 and σ=1
where μ is the mean (average) and σ is the standard deviation from the mean
Standard scores (also called z scores) of the samples are calculated as: z=(x−μ)/σ
Standardizing the features so that they are centered around 0 with a standard deviation of 1 is not only important if we are comparing measurements that have different units, but it is also a general requirement for many machine learning algorithms. Intuitively, we can think of gradient descent as a prominent example (an optimization algorithm often used in logistic regression, SVMs, perceptrons, neural networks etc.); with features being on different scales, certain weights may update faster than others since the feature values xjxj play a role in the weight updates. Other intuitive examples include K-Nearest Neighbor algorithms and clustering algorithms that use, for example, Euclidean distance measures – in fact, tree-based classifier are probably the only classifiers where feature scaling doesn’t make a difference.

In fact, the only family of algorithms that I could think of being scale-invariant are tree-based methods. Let’s take the general CART decision tree algorithm. Without going into much depth regarding information gain and impurity measures, we can think of the decision as “is feature x_i >= some_val?” Intuitively, we can see that it really doesn’t matter on which scale this feature is (centimeters, Fahrenheit, a standardized scale – it really doesn’t matter).

Some examples of algorithms where feature scaling matters are:

k-nearest neighbors with an Euclidean distance measure if want all features to contribute equally
k-means (see k-nearest neighbors)
logistic regression, SVMs, perceptrons, neural networks etc. if you are using gradient descent/ascent-based optimization, otherwise some weights will update much faster than others
linear discriminant analysis, principal component analysis, kernel principal component analysis since you want to find directions of maximizing the variance (under the constraints that those directions/eigenvectors/principal components are orthogonal); you want to have features on the same scale since you’d emphasize variables on “larger measurement scales” more. There are many more cases than I can possibly list here … I always recommend you to think about the algorithm and what it’s doing, and then it typically becomes obvious whether we want to scale your features or not.
In addition, we’d also want to think about whether we want to “standardize” or “normalize” (here: scaling to [0, 1] range) our data. Some algorithms assume that our data is centered at 0. For example, if we initialize the weights of a small multi-layer perceptron with tanh activation units to 0 or small random values centered around zero, we want to update the model weights “equally.” As a rule of thumb I’d say: When in doubt, just standardize the data, it shouldn’t hurt.

## Min-Max scaling or Normalization:
An alternative approach to Z-score normalization (or standardization) is the so-called Min-Max scaling (often also simply called “normalization” - a common cause for ambiguities).
In this approach, the data is scaled to a fixed range - usually 0 to 1.
The cost of having this bounded range - in contrast to standardization - is that we will end up with smaller standard deviations, which can suppress the effect of outliers.

A Min-Max scaling is typically done via t:Xnorm=(X−Xmin)/(Xmax−Xmin)

Z-score standardization or Min-Max scaling?
“Standardization or Min-Max scaling?” - There is no obvious answer to this question: it really depends on the application.

For example, in clustering analyses, standardization may be especially crucial in order to compare similarities between features based on certain distance measures. Another prominent example is the Principal Component Analysis, where we usually prefer standardization over Min-Max scaling, since we are interested in the components that maximize the variance (depending on the question and if the PCA computes the components via the correlation matrix instead of the covariance matrix; but more about PCA in my previous article).

```However, this doesn’t mean that Min-Max scaling is not useful at all! A popular application is image processing, where pixel intensities have to be normalized to fit within a certain range (i.e., 0 to 255 for the RGB color range). Also, typical neural network algorithm require data that on a 0-1 scale.```
# Example of preprocessing:
* Converting continuous variable to tenure variable. Example tenure variable to factor variable with range in 0-6, 6-12, 12-36 months so on.
* Converting categorical variables to a single refrence.For example, “Error encountered” feature has possible values as “No, Technical Error, Non Technical Error” convert them all to Yes.

# Prediction Accuracy:
## Categorical varaible: 
### Confusion metrics
* True Positive: Number of customer correctly classified as churn.
* True Negeative: Number of customer correct classified as engaged.
* False positive: Number of predicted churn, but they are engage user. (Also known as a "Type I error.")
* False Negative: Number of predicted engage, but they are churn user. (Also known as a "Type II error.")

* Accuracy: Overall, how often is the classifier correct```(TP+TN)/total```
* Misclassification Rate: Overall, how often is it wrong```(FP+FN)/total```
* True Positive Rate(Sensitivity" or "Recall"): When it's actually yes, how often does it predict yes```TP/actual yes```
* False Positive Rate: When it's actually no, how often does it predict yes?```FP/actual no```
* Specificity: When it's actually no, how often does it predict no```TN/actual no```
* Precision: When it predicts yes, how often is it correct```TP/predicted yes```
* F Score: This is a weighted average of the true positive rate (recall) and precision```2(Precision * Recall)/(precission+Recall)```
* ROC Curve: This is a commonly used graph that summarizes the performance of a classifier over all possible thresholds. It is generated by plotting the True Positive Rate (y-axis) against the False Positive Rate (x-axis) as you vary the threshold for assigning observations to a given class. 

### ROC Curve:
* For ROC or AUC matters is how well 2 classes are separated.
* AUC is useful even when dataset is highly imbalanced.
* ROC can be extended to problem with more then 2 classes using one versus all approach.
* Eg for 3 calss problem 3 ROC curves are generated.
  Class1 vs class2 & 3, Class2 vs class1 & 3, Class3 vs class1 & 2
* Choosing Threshold is business decission whther to minimize false postive rate or maximize true positive rate.

