Books:
- Reinforcement Learning: An Introduction Richard S. Sutton and Andrew G. Barto c 2014, 2015 : https://web.stanford.edu/class/psych209/Readings/SuttonBartoIPRLBook2ndEd.pdf
- Reinforcement Learning An Introduction second edition Richard S. Sutton and Andrew G. Barto https://www.andrew.cmu.edu/course/10-703/textbook/BartoSutton.pdf
- Algorithms for Reinforcement Learning :  https://sites.ualberta.ca/~szepesva/papers/RLAlgsInMDPs.pdf
-
Courses :
	- Author : David Silver⭐ https://www.davidsilver.uk/teaching/

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
		- **State** 💥is the information used to determine what happens next
			- formaly, **state💥**  is a function of the history :
				- $S_t = f(H_t)$
				- For example, it could be : 
					- look at the last observation
					- or look at the last four observations (what is is done in Atari)
			- **environment state** $S_t^e$ is the environment private representatiion
				- i.e. whatever data the environment uses to pick the next observation/reward
				- the environment state is not usually visible to the agent 🤖
				- even if $S_t^e$ is visible it may contain irrelevant information
			- **agent state**  $S_t^a$ is the agent's internal representation
				- i.e. whatever information the agent uses to pick the next action
				- i.e. it is the information used by reinforcement learning algorithms
				- it can be any function of the history:
					- $S_t^a = f(H_t)$
			- **information state (a.k.a Markov state)** contains all useful information from the history
				- 📝A state $S_t$ is Markov if an only if :
					- $P[S_{t+1}\;\;|\;\;S_t] = P[S_{t+1}\;\;|\;\;S_1, S_2, ..., S_t]$
				- "The future is independent of the past given the present"
					- $H_{1:t} \rightarrow S_t \rightarrow H_{t+1:\infty}$
				- once the state is known, the history may be thrown away
				- the state is sufficient statistic of the the future
				- Example : helicopter 
					- Markov state - curent position, velocity, angular velocity, angular position of the helicopter, wind speed and other. If you know all this things NOW it does not matter for the next movement of the helicopter what was the position of the helicopter 10 minutes ago
					- In contrast, if you have imperfect state (you just have the position but not the velocity). Now where the helicopter is it does not fully determine where the helicopter will be next and you have to consider the history to understand what is the velocity and the momentum of the helicopter. 
				- The **environment state** $S_t^e$ is Markov (by definition)
				- The history $H_t$ is Markov (by definition)

	- **Full observability:** agent 🤖 **directly** observes environment state 
		- $O_t = S^a_t = S^e_t$
		- Agent state = environment state = information state 
		- Formally, this is a Markov decision process (MDP)
		- this is the best case, we have an environment 🌎 where we can see everything.
	- **Partial observability**: agent 🤖**indirectly** observes environment 🌎: 
		- Examples :
			- A robot with camera vision isn’t told its absolute location 
			- A trading agent only observes current prices 
			- A poker playing agent only observes public cards
		- Now agent state $\neq$ environment state
		- Formally this is a partially observable Markov decision process (POMDP)
		- Agent must construct its own state representation $S^a_t$ , options to do so are :
			- Complete history (a.k.a. naive approach): $S^a_t = H_t$ 
			- Beliefs of environment state (a.k.a. bayes): $S^a_t = (P[S^e_t = s^1 ], ..., P[S^e_t = s^n])$
			- Recurrent neural network: $S^a_t = σ(S^a_{t-1}W_s + O_tW_o )$
	- Inside an RL agent 
		- An RL agent may include one or more of these components: 
			- Policy: agent’s behaviour function 
			- Value function: how good is each state and/or action 
			- Model: agent’s representation of the environment
		- Policy
			- A policy is the agent’s behaviour It is a map from state to action, e.g. 
			- Deterministic policy: $a = π(s)$
				- we  want this policy to be such that we get the most possible reward
			- Stochastic policy: $π(a|s) = P[A_t = a|S_t = s]$ 
				- probability to take particular action conditioned on being in some state
		- Value function
			- Value function is a prediction of future reward 
			- Used to evaluate the goodness/badness of states 
			- And therefore to select between actions, e.g.
				- $v_π(s) = E_π\;\;[R_{t+1} + γR_{t+2} + γ^2R_{t+3} \;+\; ... | S_t = s]$
		  - Model
			  - A model predicts what the environment will do next
			  - Transitions: $P$ predicts the next state 
			  - Rewards: $R$ predicts the next (immediate) reward, e.g.
				  - ![[Screenshot 2023-01-04 011631.png]]
			
			  - it could be optional to have model. It is quite common to use model free RL approach
		- Maze example :
			- https://youtu.be/2pWv7GOvuf0?t=4089
			- https://www.davidsilver.uk/wp-content/uploads/2020/03/intro_RL.pdf
				- check from page 30 to 33
		-  Categorizing RL agents (Taxonomy):
			- Value Based 
				- No Policy (Implicit)
				- **Value Function**
			- Policy Based 
				- **Policy** 
				- No Value Function 
			- Actor Critic 
				- **Policy** 
				- **Value Function**
			- Model Free 
				- **Policy and/or Value Function**
				- No Model 
			- Model Based 
				- **Policy and/or Value Function**
				- **Model**
		- Two fundamental problems in sequential decision making 
			- Reinforcement Learning: 
				- The environment is initially unknown 
				- The agent interacts with the environment 
				- The agent improves its policy 
			- Planning: 
				- A model of the environment is known 
				- The agent performs computations with its model (without any external interaction) 
				- The agent improves its policy 
				- a.k.a. deliberation, reasoning, introspection, pondering, thought, search	
		- Exploration vs Exploatation trade off
			- Exploration finds more information about the environment 
			- Exploitation exploits known information to maximise reward
			- It is usually important to explore as well as exploit (there should be a good balance)
		- Predictiion vs Control
			- Prediction: evaluate the future
				- Given a policy 
			- Control: optimise the future 
				- Find the best policy
			- typically, we have to solve the prediction problem in order to solve the control problem 
- lecture 2 : 
	- video : https://www.youtube.com/watch?v=lfHX2hHRMVQ
	- slides : https://www.davidsilver.uk/wp-content/uploads/2020/03/MDP.pdf
	- State Transition Matrix
		- For a Markov state s and successor state s 0 , the state transition probability is defined by : $Pss^\prime = P[S_{t+1} = s^\prime \;\;|\;\; S_t = s]$
		- State transition matrix $P$  defines transition probabilities from all states $s$  to all successor states $s^\prime$ 
		- ![[state_transition_matrix.png]]
		- where each row of the matrix sums to 1.
		- if we start at $P_{11}$, then by this matrix we get the probability to land in $P_{12}$, $P_{13}$ and so on
			- the matrix tells from any state how likely I am about to end in other state
	- **Markov Process**
		- A Markov process is a memoryless random process, i.e. a sequence of random states S1, S2, ... with the Markov property.
		- A Markov Process (or Markov Chain) is a tuple $<S,P>$  
			- S is a (finite) set of states 
			- P is a **state transition probability matrix**
				- $Pss^\prime = P[S_{t+1} = s^\prime \;\;|\;\; S_t = s]$
		- See the examples of the markov chain (process) from there : https://youtu.be/lfHX2hHRMVQ?t=450
	- **Markov Reward Process (MRP)**
		- A Markov reward process is a Markov chain with values
			- S is a (finite) set of states 
			- P is a **state transition probability matrix**
				- $Pss^\prime = P[S_{t+1} = s^\prime \;\;|\;\; S_t = s]$
			- $R$ is a rewarded function, $R_s = E[R_{t+1}\;|\; S_t = s]$ 
			- γ (gamma) is a discount factor, γ ∈ [0, 1]
			- ![[example_students_markov_reward_process.png]]
		- Return
			- The return Gt is the total discounted reward from time-step t. 
				- ![[return_Gt.png]]
			- The discount γ ∈ [0, 1] is the present value of future rewards 
			- The value of receiving reward R after k + 1 time-steps is $γ^kR$.
			- This values immediate reward above delayed reward. 
				- γ close to 0 leads to ”myopic” evaluation 
				- γ close to 1 leads to ”far-sighted” evaluation
				- a γ (gamma) close to 0 indicates preference to get reward now while reward close to 1 means to get it later
		- discount factor (Most Markov reward and decision processes are discounted. Why?)
			- Mathematically convenient to discount rewards 
			- Avoids infinite returns in cyclic Markov processes 
			- Uncertainty about the future may not be fully represented 
			- If the reward is financial, immediate rewards may earn more interest than delayed rewards 
			- Animal/human behaviour shows preference for immediate reward 
			- It is sometimes possible to use undiscounted Markov reward processes (i.e. γ = 1), e.g. if all sequences terminate.
		- Value function
			- The value function v(s) gives the long-term value of state $s$
			- The state value function v(s) of an MRP is the expected return starting from state s is : $v(s) = E [Gt\; |\; St = s]$
			- ![[example_MRP_returns.png]]
		- Bellman equation
			- The Bellman equation is a linear equation
			- ![[bellman_equation.png]]
			- Direct solution only possible for small MRPs 
			- There are many iterative methods for large MRPs, e.g. 
				- Dynamic programming 
				- Monte-Carlo evaluation 
				- Temporal-Difference learning

DOTUUK : https://youtu.be/lfHX2hHRMVQ?t=2580




https://people.cs.umass.edu/~barto/courses/cs687/Chapter%201.pdf
https://github.com/agrawal-rohit/tic-tac-toe-bot



DOTUK : https://youtu.be/2pWv7GOvuf0?t=2878
https://www.davidsilver.uk/teaching/



Training :
- on mac book it will take quite a while 
	- 3-4 days of training on GPU per game to get at the human level (atari games)

Takeaways :
- RL is the science of decision making




For presentation :

- RL in the field of machine learning

https://medium.datadriveninvestor.com/contemporary-classification-of-machine-learning-techniques-part-3-f7e3b9de0570