# Machine Learning in Python
1 -> Simple Linear Regression
2 -> Multiple Linear Regression
3 -> Building a Regression
4 -> Interpret results of Regression
5 -> Compare and choose the best Models for any given problem


**Feature selection**

	Use statsmodel to get a descriptive statistics of the whole linear Regression or calculate 
	
	#### Add a constant. Esentially, we are adding a new column (equal in lenght to x), which consists only of 1s	
	x = sm.add_constant(_xi_)
	
	#### Fit the model, according to the OLS (ordinary least squares) method with a dependent variable y and an idependent x
	results = sm.OLS(y,x).fit()
	
	#### Print a nice summary of the regression.
	results.summary() # _Get statistics from summary_
	
	$R^2$ from reg.score(_xi_,y)
	
	#### Number of observations is the shape along axis 0
	n = _xi_.shape[0]
	
	#### Number of features (predictors, p) is the shape along axis 1
	p = _xi_.shape[1]
	
	$R^2_{adj.} = 1 - (1-R^2)*\frac{n-1}{n-p-1}$
	
	#### P-value
	from sklearn.feature_selection import f_regression
	
	p-value = f_regression(_xi_,y)[1]
	
	if p-value > 0.05:
		Reject Null Hypothesis
	else:
		Accept Null Hypothesis