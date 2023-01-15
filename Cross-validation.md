Cross-validation is a statistical method used **to estimate the performance of machine learning models. It is a method for assessing how the results of a statistical analysis will generalize to an independent data set**

## Takeaways :

- **HoldOut Cross-validation or Train-Test Split**
	- ![[Pasted image 20230108101517.png]]
- **K_-Fold** :
	- The training data used in the model is split, into k number of smaller sets, to be used to validate the model. The model is then trained on k-1 folds of training set. The remaining fold is then used as a validation set to evaluate the model.
	- ![[Pasted image 20230108095700.png]]
- **Stratified K-Fold** :
	- In cases **where classes are imbalanced** we need a way to account for the imbalance in both the train and validation sets. To do so we can stratify **the target classes**, meaning that both sets will have an equal proportion of all classes.
	- Splits the data into k folds, making sure each fold is an appropriate representative of the original data. (class distribution, mean, variance, etc)
	- ![[Pasted image 20230108095923.png]]
- **Leave-One-Out (LOO)**
	- Instead of selecting the number of splits in the training data set like k-fold LeaveOneOut, utilize 1 observation to validate and n-1 observations to train. This method is an exaustive technique.
	 - ![[Pasted image 20230108100742.png]]
	- **WHEN TO USE : **when you have a small dataset or when an accurate estimate of model performance is more important than the computational cost of the method
- ## Leave-P-Out (LPO)
	- Variation of Leave-One-Out where we can specify the value of p (e.g. 2 observations instead of one)
- **Monte Carlo Cross-Validation(Shuffle Split)**
	- In `ShuffleSplit`, the data is shuffled every time, and then split. This means the test sets may overlap between the splits.
- **Time Series Cross-Validation**
	- temproal order of the data matters
	- we cannot choose random samples and assign them to either training or validation set as it makes no sense
	- Different techniques : https://medium.com/@soumyachess1496/cross-validation-in-time-series-566ae4981ce4#:~:text=Cross%20Validation%20on%20Time%20Series,for%20the%20forecasted%20data%20points.
	- Monte Carlo CV - https://towardsdatascience.com/monte-carlo-cross-validation-for-time-series-ed01c41e2995
	- **“Forward chaining”** method or rolling cross-validation 
		- ![[Pasted image 20230108102306.png]]
		- ![[Pasted image 20230108102312.png]]

## Links

- https://www.w3schools.com/python/python_ml_cross_validation.asp
- https://www.analyticsvidhya.com/blog/2021/11/top-7-cross-validation-techniques-with-python-code/
- https://medium.com/@soumyachess1496/cross-validation-in-time-series-566ae4981ce4#:~:text=Cross%20Validation%20on%20Time%20Series,for%20the%20forecasted%20data%20points.

## Tags :
#cross_validation

## Libraries :
- time series cross validation : https://pypi.org/project/timeseries-cv/
