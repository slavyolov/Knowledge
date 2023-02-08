
# Date gaps
- How To Identify Date Gaps in Time Series Data with Pandas https://www.rasgoml.com/feature-engineering-tutorials/how-to-solve-date-gaps-in-time-series-data-with-pandas
- Filling Gaps in Time Series Data : https://towardsdatascience.com/filling-gaps-in-time-series-data-2db7366f1965
- 4 Techniques to Handle Missing values in Time Series Data : https://towardsdatascience.com/4-techniques-to-handle-missing-values-in-time-series-data-c3568589b5a8

# Calendar features : 
- Cyclical features encoding, it’s about time! | by Pierre-Louis Bescond | Towards Data Science : https://towardsdatascience.com/cyclical-features-encoding-its-about-time-ce23581845ca
- https://www.mikulskibartosz.name/time-in-machine-learning/
- https://feature-engine.trainindata.com/en/1.3.x/user_guide/creation/CyclicalFeatures.html

# Auto Correlation
- https://towardsdatascience.com/interpreting-acf-and-pacf-plots-for-time-series-forecasting-af0d6db4061c
- https://towardsdatascience.com/interpreting-acf-and-pacf-plots-for-time-series-forecasting-af0d6db4061c
	- ACF
		- Can the observed time series be modeled with an **MA model**? If yes, what is the order?
	- PACF :
		- used to check if the observed time series be modeled with an **AR model**? If yes, what is the order?
	- To determine the order of the model, you check:
		 - “How many lollipops are above or below the confidence interval before the next lollipop enters the blue area?”


Window Features :
	- rolling mean grouped per key (e.g. day_of_week) : https://medium.com/@alexander.mueller/rolling-aggregations-on-time-series-data-with-pandas-80dee5893f9