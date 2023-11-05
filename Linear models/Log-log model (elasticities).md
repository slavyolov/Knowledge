======================================================================
# Important considerations

★ price variation must be purely exogenous. For example, unexpected promotion in random timing can be one of them.

★ Arguably the most important econometric problem for estimation of the demandsupply model is posed by the output price being likely endogenous. More here : [demand_final_slides11.pdf (soderbom.net)](http://www.soderbom.net/demand_final_slides11.pdf)

=====================================================================

- log-log model was motivated by the interest to capture the non-linear relationship between the independent and dependent variables.
- There are a few common uses of this model:
	- To identify X elasticity of Y (for eg, price elasticity of demand)
	- To find the % change in Y given % change in X


=====================================================================
**Constant elasticity model using Simple Linear Regression**

[(1) Implementing Constant Elasticity Model using Simple Linear Regression - YouTube](https://www.youtube.com/watch?v=s8fqKYRp3_8)

Formula : 

$$Log (D) = Log (C) - e * Log (P)$$

Where :
D - demand
P - price
C - constant (Y intercept ==> $\beta0$ )
e - negative epsilon (slope ==> $\beta1$ )

The task is to estimate the Log(C) using linear regression

Hypothesis :

- Null : regression is not significant
- Alternative : regression is significant

if p_value < 0.05 we accept the Alternative hypothesis (or reject the Null hypothesis)

**Interpretation of the coefficients :**

[FAQ How do I interpret a regression model when some variables are log transformed? (ucla.edu)](https://stats.oarc.ucla.edu/other/mult-pkg/faq/general/faqhow-do-i-interpret-a-regression-model-when-some-variables-are-log-transformed/)
expected_change_in_sales (change in price by 1% ** beta_coefficient ($\beta1$)) - 1

=====================================================================




Resources : 
- 🍎 [Log-log model, elasticity, percentage change (dancingwithstatistics.com)](https://www.dancingwithstatistics.com/statistics/log-log-model%2C-elasticity%2C-percentage-change)
- 🍎 [Price Elasticity of Demand with a Simple Linear Regression (Part I) | by Ileana Cabada | Medium](https://ileanacabada.medium.com/price-elasticity-of-demand-using-linear-regression-in-python-part-1-a28c844c1656)
- 🍎 [Price Elasticity of Demand with a Simple Linear Regression (Part II) | by Ileana Cabada | Geek Culture | Medium](https://medium.com/geekculture/price-elasticity-of-demand-using-linear-regression-in-python-part-2-8adb654328e7)
- 🍎 [Food for Regression: Using Sales Data to Identify Price Elasticity (statworx.com)](https://www.statworx.com/en/content-hub/blog/food-for-regression-using-sales-data-to-identify-price-elasticity/)
- 🍎 [Food for Regression: Mixing in Cross-Elasticities and Promotional Effects (statworx.com)](https://www.statworx.com/en/content-hub/blog/food-for-regression-mixing-in-cross-elasticities-and-promotional-effects/)
- Optimizing product price using regression : http://webcache.googleusercontent.com/search?q=cache:https://towardsdatascience.com/optimizing-product-price-using-regression-2c17688e65ea
- Markdowns: From Descriptive to Prescriptive : http://webcache.googleusercontent.com/search?q=cache:https://towardsdatascience.com/markdowns-from-descriptive-to-prescriptive-ec729c4cce82
- [Price elasticity’s credibility has been stretched! (occstrategy.com)](https://www.occstrategy.com/usa/our-insights/insight/id/3336/price-elasticitys-credibility-has-been-stretched)
- [Topic11_LR.pdf (uc3m.es)](https://www.eco.uc3m.es/docencia/EconomiaAplicada/materiales/Topic11_LR.pdf)
- [Price Elasticity of Demand #RegressionModel #DataAnalytics | LinkedIn](https://www.linkedin.com/pulse/price-elasticity-demand-regressionmodel-dataanalytics-rohan-shetty/)
- [(PDF) Modeling Elasticity: A Brief Survey of Price Elasticity of Demand Estimation Methods (researchgate.net)](https://www.researchgate.net/publication/344075440_Modeling_Elasticity_A_Brief_Survey_of_Price_Elasticity_of_Demand_Estimation_Methods)
- [Elasticity_JORM.pdf](file:///Users/syol07091/Downloads/Elasticity_JORM.pdf)
- [(3) Multi-Period Markdowns: The Food Retailer’s Ticket to Maximize Revenues | LinkedIn](https://www.linkedin.com/pulse/multi-period-markdowns-food-retailers-ticket-maximize-oded-omer/)
- [Price elasticity - The holy grail of pricing strategy? - Yieldigo](https://www.yieldigo.com/price-elasticity-the-holy-grail-of-pricing-strategy/)
- [Demand elasticities and price-cost margin ratios for grocery products in different socioeconomic groups (agriculturejournals.cz)](https://www.agriculturejournals.cz/pdfs/age/2006/05/04.pdf)
- [Price elasticity - the key to optimal prices - 7Learnings](https://7learnings.com/blog/price-elasticity/)
- [Optimal real time pricing in an agent-based retail market using a comprehensive demand response model (adme.com.uy)](https://adme.com.uy/db-docs/Docs_secciones/nid_150/DR_p006_OptimalRealTimePricing_AgentBasedRetailMarket.pdf)
- [1265_Li_Dec2015.pdf;sequence=2 (umich.edu)](https://deepblue.lib.umich.edu/bitstream/handle/2027.42/116278/1265_Li_Dec2015.pdf;sequence=2)
- [The price elasticity of electricity demand in South Australia and Victoria ESIPC and VenCorp (robjhyndman.com)](https://robjhyndman.com/papers/Elasticity2010.pdf)
- [Hourly price elasticity pattern of electricity demand in the German day-ahead market (econstor.eu)](https://www.econstor.eu/bitstream/10419/144865/1/865176043.pdf)
- http://webcache.googleusercontent.com/search?q=cache:https://towardsdatascience.com/predicting-price-elasticity-of-demand-with-python-implementing-stp-framework-part-4-646b025b8b34
- [Price Elasticity of Demand, Statistical Modeling with Python | by Susan Li | Towards Data Science](https://towardsdatascience.com/calculating-price-elasticity-of-demand-statistical-modeling-with-python-6adb2fa7824d)
- 

Books :
[Ch. 5 Introduction to Elasticity - Principles of Economics 3e | OpenStax](https://openstax.org/books/principles-economics-3e/pages/5-introduction-to-elasticity)

# Forums :
- [econometrics - price elasticity and time series modelling - Cross Validated (stackexchange.com)](https://stats.stackexchange.com/questions/260112/price-elasticity-and-time-series-modelling)
	- What you need is a real or quasi experiment, that makes your price variation purely exogenous. Unexpected promotion in random timing can be one of them.
- [econometrics - Instrumental variables regression Vs Linear Regression for price elasticity - Cross Validated (stackexchange.com)](https://stats.stackexchange.com/questions/197838/instrumental-variables-regression-vs-linear-regression-for-price-elasticity)
	- 🍎 [demand_final_slides11.pdf (soderbom.net)](http://www.soderbom.net/demand_final_slides11.pdf)
		- We can obtain an instrumental variable estimate by means of a two-stage procedure
			- 1st we predict the price
			- 2nd we predict
- Two stage LR model for elasticity (Estimating Demand Elasticity with Many Instruments: a Machine Learning Approach) [demand_estimation_final.pdf (tum.de)](https://www.ep.mgt.tum.de/fileadmin/w00cgd/cem/Publikationen/demand_estimation_final.pdf)
- [regression - Price Elasticity Calculation - Cross Validated (stackexchange.com)](https://stats.stackexchange.com/questions/207949/price-elasticity-calculation)
- 

# **Advantages**:

- Relatively simple method
- Provides guidance on which level of budget to invest in markdowns, and expected impact, based on the historical price elasticity
- Rooted in data about price sensitivity of demand, which increases the amount of customer-centricity of the process.

**Disadvantages**:

- Poor predictive power: the R-squared of these methods is relatively poor, so the model is not completely fit for purpose
- Predictions only feasible at intermediate levels of aggregation, e.g. store/category, as item-level elasticity is often impossible to determine
- Limited input signals, as price is not the only factor influencing sales, and product prices have inter-related effects e.g. due to cannibalization.
# Features for modeling :
- promotion_fg
- calendar features (e.g. week, month)
- 


# Tags
#demand_elasticity, #price_elasticity, #markdowns