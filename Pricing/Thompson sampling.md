
**Information**

The main idea of Thompson sampling is to control the amount of exploration by sampling the model parameters for a probabilistic distribution that is refined over time. 

If the variance of the distribution is high, we will tend to explore a wider range of possible demand functions. If the variance is low, we will mostly use functions that are close to what we think is the most likely demand curve (that is, the curve defined by the mean of the distribution), and explore more distant shapes only occasionally. 

Note that the demand distribution incorporates both the dependency between the price and demand (which can be composed of deterministic and random components).

**Papers :**

- [1802.03050v1.pdf (arxiv.org)](https://arxiv.org/pdf/1802.03050v1.pdf)

**Main information :**
- [Thompson sampling - Wikipedia](https://en.wikipedia.org/wiki/Thompson_sampling)
- 1️⃣ [Effective dynamic pricing in practice | ML6team (medium.com)](https://medium.com/ml6team/dynamic-pricing-in-practice-99fe2216a93d)
- 2️⃣ [Dynamic Pricing Algorithms using Reinforcement Learning (griddynamics.com)](https://blog.griddynamics.com/dynamic-pricing-algorithms/)

**Code / Demos :**
	- [Thompson sampling.ipynb](https://colab.research.google.com/drive/1ZbQBr2qYTxVQBcafLMJhqUYn5qndfRWv?usp=sharing)
		- [tensor-house/pricing/dynamic-pricing-thompson.ipynb](https://github.com/ikatsov/tensor-house/blob/master/pricing/dynamic-pricing-thompson.ipynb)
	- [ml6team/dynamic-pricing](https://huggingface.co/spaces/ml6team/dynamic-pricing/tree/main)
**Tags**

#reinforcement_learning #thompson_sampling #dynamic_pricing #active_learning 