# Principal Component Analysis(PCA)
* Aim of PCA is to maximize rate of decrease of variance
* PCA preserves variance in the original data
* PCA as a output gives new variables that are from new transformed coordinates which is linear combination of original data
* First Principal component has maximum variance. Second Principal component has second maximum variance that is orthogonal to first Principal Component
* Out of total P features in a dataset, Principal Component generates D Principal Component. Generall P > D or at maximum P == D
* Cross-validation should be done in order to find out what choice of features would yield a optimal balance between “preserving information” and “over fitting” for different classifiers

# Flow chart
* Step 1: Standardize the variables: Else as data will be in different scale with different variance this will lead in higher loading for this variable with maximum variance. Hence Principal Component will be based on such variables which is not desirable.
* Step 2: Determine covariance matrix of all features.(Note: Covariance matrix has variance across principal diagonals and covariance for others)
* Step 3: Deduce Eigens
	1. Eigen Values: Represents how much variance there is in data on that particular direction. 
	2. Eigen Vector: Represents direction in space
					 They are orthogonal to each other
					 Eigen vector with maximum Eigen value is first Principal Component
* Step 4: Reorient the data by multiplying Eigen vectors to the original dataset