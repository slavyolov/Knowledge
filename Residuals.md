
- The “residuals” in a time series model are what is left over after fitting a model. For many (but not all) time series models, the residuals are equal to the **difference between the observations and the corresponding fitted values**:  $$et=yt−^yt.$$
- A good forecasting method will yield residuals with the following properties:

	1. The residuals are **uncorrelated**
	2. The residuals have **zero mean**. If the residuals have a mean other than zero, then the forecasts are biased.
			1. Adjusting for bias is easy: if the residuals have mean $\mu$, then simply add $\mu$ to all forecasts and the bias problem is solved.
	3. The residuals have **constant/equal variance**.
	4. The residuals are **normally distributed**.


- Calculate them on the TEST set : **Model selection**
- Calculate them on the WHOLE set (all data) after the model selection is done: **Model fitting**

### Sources :
- https://otexts.com/fpp2/residuals.html
- https://ema.drwhy.ai/residualDiagnostic.html
- https://stats.stackexchange.com/a/147132
- https://stats.stackexchange.com/a/296020
- 