- ### Train/test split
	- The train-test split is a technique for evaluating the performance of a machine learning algorithm.
		- **Train Dataset**: Used to fit the machine learning model.
		- **Test Dataset**: Used to evaluate the fit machine learning model
	- Conversely, the train-test procedure is **not appropriate when the dataset available is small**. The reason is that when the dataset is split into train and test sets, there will not be enough data in the training dataset for the model to learn an effective mapping of inputs to outputs.
	-  **deep neural network models**. In this case, the train-test procedure is commonly used.

- ### Stratified Train-Test Splits
	- One final consideration is **for classification problems only**.
	- Some classification problems do not have a balanced number of examples for each class label. As such, it is desirable to split the dataset into train and test sets in a way that preserves the same proportions of examples in each class as observed in the original dataset. (train : 50 cases of class A and 3 cases of class B; test set : 50 cases of class A and 3 cases of class B)

### 📝 Takeaways

The train-test split procedure is appropriate when you have :

- a very large dataset 
- a costly model to train
- require a good estimate of model performance quickly.
	
# In time series

# Other

### 🧠 Sources :
- https://machinelearningmastery.com/train-test-split-for-evaluating-machine-learning-algorithms/

### 👶Questions
- what is the minimum set size, in absolute numbers, when doing train_test split?
	- Would 30 be problematic -> 24 cases for training and 6 cases for evaluation ? (80% / 20%)
