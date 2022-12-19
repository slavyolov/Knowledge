
### 📝Assumptions of Linear Regression :

- Main :
	- Linearity of the data/model
	- No autocorrelation of residuals
	- mean of residuals is zero
	- Homoscedasticity (equal variance) of residuals
	- No (perfect) multicollinearity
	- The features and residuals are uncorrelated
	- The number of observations must be greater than number of features
	- There must be some variability in features
	
- These are verified on the fitted model (train data or whole dataset)
- Sources :
- https://towardsdatascience.com/verifying-the-assumptions-of-linear-regression-in-python-and-r-f4cd2907d4c0 ⭐(author: Eryk Lewinson)
- https://jeffmacaluso.github.io/post/LinearRegressionAssumptions/
- http://r-statistics.co/Assumptions-of-Linear-Regression.html
- https://godatadrive.com/blog/basic-guide-to-test-assumptions-of-linear-regression-in-r



### Residuals

- The “residuals” in a time series model are what is left over after fitting a model. For many (but not all) time series models, the residuals are equal to the **difference between the observations and the corresponding fitted values**:  $$et=yt−^yt.$$
- A good forecasting method will yield residuals with the following properties:

	1. The residuals are uncorrelated
	2. The residuals have zero mean. If the residuals have a mean other than zero, then the forecasts are biased.
			1. Adjusting for bias is easy: if the residuals have mean $\mu$, then simply add $\mu$ to all forecasts and the bias problem is solved.
	3. The residuals have constant variance.
	4. The residuals are normally distributed.

### Sources :
- https://otexts.com/fpp2/residuals.html

```
TAGS :
```
#LineareRegression; #SimpleLinearRegression;	#MultipleLinearRegression, #InteractionEffect-Synergy; #VIF-VarianceInflationFactor; #Multicollinearity
	- 
- Y ≈ β0 + β1X

## Demos :

- https://github.com/slavyolov/Linear_Regression/blob/main/multiple-linear-regression-advertising-dataset.ipynb
	- Topics : 
		- **Simple Linear Regression**, **Multiple Linear Regression**, **Interaction Effect (Synergy)**, **VIF (Variance Inflation Factor) / Multicollinearity**
	- ```
---
tags:
  - tag1
  - tag2
---

 ---
 tags: [writing/blog, ideas, blog/status/draft] 
---

---
Status : 
#🌲
Tags:
[[Linear Regression]] - [[VIF]]

# Terminal

