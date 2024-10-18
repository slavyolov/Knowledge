
# Resources :

- Bayesian AB Testing - https://towardsdatascience.com/bayesian-ab-testing-ed45cc8c964d
	- Using control variables
	- pre-treatment period: this should be included in the model as a control variable, it's completely unrelated to the prior. Mu und sigma of the prior are defined by the fact that we're using an uninformative prior.
	- Testing two versions of a website. Here are the equivalents between the article and our analysis:
		- y - ad revenue: 
			- for us : average daily loss in percent during test period
		- X - past ad revenue: 
			- for us average daily loss in percent before the test period (pre treatment)
		- D - two versions of the website (infinite scrolling yes/no): 
			- for us, test vs. control group

**Other links**

- [How to Make More Money With Bayesian A/B Test Evaluation (cxl.com)](https://cxl.com/blog/bayesian-ab-test-evaluation/)
- [Essential AB Testing Terms | Dennis Meisner | Product Coalition](https://productcoalition.com/the-ab-testing-dictionary-a565acf6d260)
- [Bayesian statistics - ModelAssist ® - Model Assist (epixanalytics.com)](https://modelassist.epixanalytics.com/space/EA/26575367/Bayesian+statistics)
- [Easy as ABC: A Quick Introduction to Bayesian A/B Testing in Python (Will Barker) (youtube.com)](https://www.youtube.com/watch?v=nRLI_KbvZTQ)


# In brief

- **Prior beliefs** - Prior belief is _knowledge that one has about a parameter of interest before any events_ have been observed.
	- [Prior Distributions](https://modelassist.epixanalytics.com/space/EA/26575371/Introduction+-+Prior+Distributions)
	- 
- Posterior
- Likelihood

- Bayesian approach
	- We update our prior beliefs with new information
	- Describes hypothesis and data in terms of probability distribution

# TODO

- [Introduction to A/B Testing | Udacity](https://www.udacity.com/course/ab-testing--ud257)
- [Cameron Davidson - Probabilistic-Programming-and-Bayesian-Methods-for-Hackers: aka "Bayesian Methods for Hackers": An introduction to Bayesian methods + probabilistic programming ](https://github.com/CamDavidsonPilon/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers?tab=readme-ov-file)
- [Count Bayesie - A Probability Blog](https://www.countbayesie.com/)

# Tags
#prior , #posterior, #likelihood , #bayes , #bayesian_statistics , #ADF , #A/B_testing