When forecasting or predicting the future, most time series models assume that each point is independent of one another. The best indication of this is when the dataset of past instances is stationary. For data to be stationary, the statistical properties of a system do not change over time.


- #ADF, #Augmented-Dickey-Fuller
	- ADF (Augmented Dickey-Fuller) test is a statistical significance test which means the test will give results in [hypothesis tests](https://analyticsindiamag.com/importance-of-hypothesis-testing-in-data-science/) with null and alternative hypotheses. As a result, we will have a p-value from which we will need to make inferences about the time series, whether it is stationary or not.
	- Run code :
	
	```
	# ADF Test
	
	from statsmodels.tsa.stattools import adfuller
	
	# Where 'y' (target variable) must be pandas.core.series.Series 
	
	result = adfuller(y, autolag='AIC')
	
	print('ADF Statistic: %f' % result[0])
	print('p-value: %f' % result[1])
	print('Critical Values:')
	
	for key, value in result[4].items():
	    print('\t%s: %.3f' % (key, value))
	
	if result[0] < result[4]["5%"]:
	    print ("Reject Ho - Time Series is Stationary")
	else:
	    print ("Failed to Reject Ho - Time Series is Non-Stationary")
	```
	
	- Guides : 
			- https://analyticsindiamag.com/complete-guide-to-dickey-fuller-test-in-time-series-analysis/#:~:text=The%20augmented%20dickey%20fuller%20test,level%20in%20the%20time%20series.
			- https://towardsdatascience.com/why-does-stationarity-matter-in-time-series-analysis-e2fb7be74454
			- 