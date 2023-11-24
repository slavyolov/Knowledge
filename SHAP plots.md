- **Guides :**
	- 🍒[Explaining Machine Learning Models: A Non-Technical Guide to Interpreting SHAP Analyses (aidancooper.co.uk)](https://www.aidancooper.co.uk/a-non-technical-guide-to-interpreting-shap-analyses/)
	- https://towardsdatascience.com/how-to-easily-customize-shap-plots-in-python-fdff9c0483f2
	- [Explainable AI (XAI) with SHAP - regression problem | by Idit Cohen | Towards Data Science](https://towardsdatascience.com/explainable-ai-xai-with-shap-regression-problem-b2d63fdca670)
	- [Interpreting complex models with SHAP values | by Gabriel Tseng | Medium](https://medium.com/@gabrieltseng/interpreting-complex-models-with-shap-values-1c187db6ec83)
	- [All You Need to Know About SHAP for Explainable AI? | by Isha Choudhary | Medium](https://medium.com/@shahooda637/all-you-need-to-know-about-shap-for-explainable-ai-8ad35a05e6ec)
	- [A new perspective on Shapley values, part I: Intro to Shapley and SHAP | Cake or Math: A Data/Science Blog (edden-gerber.github.io)](https://edden-gerber.github.io/shapley-part-1/)
	- [Using SHAP Values for Model Interpretability in Machine Learning - KDnuggets](https://www.kdnuggets.com/2023/08/shap-values-model-interpretability-machine-learning.html#:~:text=What%20are%20SHAP%20Values%3F,is%20considered%20a%20%22player%22.)
		- [SHAP](https://shap.readthedocs.io/en/latest/index.html) values are based on Shapley values from game theory. In game theory, Shapley values help determine how much each player in a collaborative game has contributed to the total payout.
		- For a machine learning model, each feature is considered a "player".

- **Plots :** 
	- **Force plot :**
		- [SHAP Force Plots for Classification | by Max Steele (they/them) | MLearning.ai | Medium](https://medium.com/mlearning-ai/shap-force-plots-for-classification-d30be430e195)

	- **Dependence plot :**
		- A dependence plot is a scatter plot that shows the effect a single feature has on the predictions made by the model.
			- [Documentation by example for shap.dependence_plot — SHAP latest documentation (shap-lrjball.readthedocs.io)](https://shap-lrjball.readthedocs.io/en/latest/example_notebooks/plots/dependence_plot.html)

	- **Decision plot :** 
		- SHAP decision plots show how complex models arrive at their predictions (i.e., how models make decisions).
			- [Documentation by example for shap.plots.decision_plot — SHAP latest documentation (shap-lrjball.readthedocs.io)](https://shap-lrjball.readthedocs.io/en/latest/example_notebooks/plots/decision_plot.html#)

	- Waterfall plot :
		- Waterfall plots are designed to display explanations for individual predictions, so they expect a single row of an Explanation object as input. The bottom of a waterfall plot starts as the expected value of the model output, and then each row shows how the positive (red) or negative (blue) contribution of each feature moves the value from the expected model output over the background dataset to the model output for this prediction.
			- [Documentation by example for shap.plots.waterfall — SHAP latest documentation (shap-lrjball.readthedocs.io)](https://shap-lrjball.readthedocs.io/en/latest/example_notebooks/plots/waterfall.html)

**Base value :**
- For **regression models**, the base value is equal to the mean of the target variable (e.g. the mean house price in the dataset), 
- whereas for **classification models**, the base value is equal to the prevalence of the positive class (e.g. the percentage of tumours in the dataset that are malignant).

**Tips :**
- LGBM
	In order to match predictions between SHAP values and model.predict we have to set the `raw_scores = True` :
		- [Interpretation of Base Value and Predicted Value in SHAP Plots · Issue #352 · shap/shap · GitHub](https://github.com/shap/shap/issues/352)
		- Solution : https://github.com/shap/shap/issues/352#issuecomment-502771556

**Know how :**

- [Be Careful When Interpreting Predictive Models in Search of Causal Insights | by Scott Lundberg | Towards Data Science](https://towardsdatascience.com/be-careful-when-interpreting-predictive-models-in-search-of-causal-insights-e68626e664b6)
	- Flexible predictive models like XGBoost or LightGBM are powerful tools for solving _prediction_ problems. However, they are not inherently causal models, so interpreting them with SHAP will fail to accurately answer _causal_ questions in many common situations. Unless features in a model are the result of experimental variation, applying SHAP to predictive models without considering confounding is generally not an appropriate tool to measure causal impacts used to inform policy.

- [A Unified Approach to Interpreting Model Predictions (neurips.cc)](https://proceedings.neurips.cc/paper_files/paper/2017/file/8a20a8621978632d76c43dfd28b67767-Paper.pdf)

