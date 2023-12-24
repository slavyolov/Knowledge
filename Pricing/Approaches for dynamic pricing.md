
# Typical approach

1. Collect historical data about the price of an item and the demand of item at different price points
2. Posit a statistical model for the demand as a function of price, and estimate the model parameters using historical data
3. Using the learned demand function, optimize some metric of interest (e.g. revenue) to get the new optimal price
4. Apply the obtained optimal price to the item for the next few days and repeat the above.

## Characteristic's

❗️Such approaches **are myopic and try to optimize for the metric in the short term without trying to make an active effort to learn the demand function**. In fact such approaches have shown to lead to incomplete learning (Harrison et al., 2012), and have poor performance, and lose revenue on the long run.

❗️**Parametric modeling** has been particularly popular because it allows one **to build simple, explainable models and also allows for simple pricing algorithms**. However, commonly used models, both parametric and nonparametric, in demand modeling tend to **assume that the underlying demand function is stationary**
## Tags

#dynamic_pricing #approaches #passive_learning

