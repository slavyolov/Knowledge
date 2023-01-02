Books
- Reinforcement Learning: An Introduction Second edition, in progress Richard S. Sutton and Andrew G. Barto c 2014, 2015 : https://web.stanford.edu/class/psych209/Readings/SuttonBartoIPRLBook2ndEd.pdf
- Algorithms for Reinforcement Learning :  https://sites.ualberta.ca/~szepesva/papers/RLAlgsInMDPs.pdf
Courses

- lecture 1 : https://www.youtube.com/watch?v=2pWv7GOvuf0
	- What makes reinforcement learning different from other machine learning paradigms  ?
		- There is no supervisor only a reward signal (no one tells you the right action to take. It is trial and error process)
		- Feedback is delayed, not instantaneous (the feedback comes after many iterations. Sometimes good decision at one point may be bad decision at later point) 
		- Time really matters (dynamic system, the sequence of action matter)
			- Imagine robot that goes through an environment. What he sees now it is quite related to what it saw one second ago)
		- Agent's actions affects the subsequent data it receives
			- Imagine the same robot moving to the left of the room and in contrast to the right of the room. It gets different data in the opposite directions
	- Examples :
		- atari
		- chess
		- investment portfolio
		- and many more
	- Reward
		- $R_t$ (reward) is scalar feedback signal
		- indicates how well the agent is doing at step $t$
		- the agents job is to maximise cumulative reward
		- RL is based on the "reward hypothesis"
			- 📝All goals can be described by the maximisation of expected cumulative reward
		- Example :
			- Task - defeat the world champion at Chess
				- positive reward for winning
				- negative reward for losing
	- Sequential decision making
		- Goal : select actions to maximise the total future reward
		- Actions may have long term consequences 
		- Reward may be delayed
		- It is better to sacrifice immediate reward to gain more long term reward
		- Examples :
			- financial investment (may take months to mature. Now you are losing money with the expectation that one day the trend will reverse)
			- chess (blocking opponent moves may inrease the chances for winning later)
	- Agents and environment
		- our goal is to build agent ("AI brain"/algorithm) that takes actions to maximise a reward
		- on the other side we have environment 
			- at each step $t$ the agent 🤖:
				- executes action $A_t$
				- Receives observation $O_t$
				- Receives scalar reward $R_t$
			- at each step $t$ the environment 🌎:
				- receives action $A_t$
				- emits observation $O_t$
				- emits scalar reward $R_t$
				
		- ![[0_ofIKXdtjfarwQqGW.png]]
		- Takeaways :
			- the agent has no control on the environment, expect the action stage. 
			- The agent influences the environment by taking actions. 
			- This goes on and on and the trial and error loop is the maximum time/epochs we defined for the simulation. 
	- History and state
		- the **history ⌛** is the sequence of observations, actions, rewards
			- $H_t = A_1,O_1,R_1, A_2, O_2, R_2...A_t, O_t, R_t$
			- i.e. all observable variables up to time t
		- What happens next depends on the history :
			- the agent selects actions
			- the environment selects observations/rewards 
		- **State** 💥







Training :
- on mac book it will take quite a while 
	- 3-4 days of training on GPU per game to get at the human level (atari games)

Takeaways :
- RL is the science of decision making




For presentation :

- RL in the field of machine learning
- 