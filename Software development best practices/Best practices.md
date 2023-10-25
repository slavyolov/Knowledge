
- **trunk-based-development** :[Trunk-based Development | Atlassian](https://www.atlassian.com/continuous-delivery/continuous-integration/trunk-based-development)
- **small PRs and merge often, even if it's not finished work**
- Add changes under a feature flag :
	- **A feature flag** could be implemented in a few ways, for instance.  

		1. You could add if-else statements depending on a configuration parameter.
		2. You could add new separate DAG tasks that deprecate the current ones. In this case, changing between the "main" way of execution and your "way", consists of just swapping some tasks.  
		3. You could add new separate jobs that deprecate the current one (be careful here though, too much code duplication will also become a problem).