# SARSA - Cliff Walking
Cliff Walking problem implemented using the SARSA Reinforcement Learning algorithm.

This project is part of my learning journey in **Reinforcement Learning**, where I implemented SARSA from scratch using a Q-table and trained an agent to navigate the Cliff Walking environment.

## About the Project

SARSA stands for:

**State → Action → Reward → State → Action**

It is an **on-policy Temporal Difference (TD) learning algorithm**.

The agent learns by interacting with the environment and updating its Q-values based on the action that it actually chooses in the next state.

The SARSA update rule is:

```text
Q(s, a) ← Q(s, a) + α [r + γ Q(s', a') - Q(s, a)]
```
Where:

s = Current state
a = Current action
r = Reward received
s' = Next state
a' = Next action
α = Learning rate
γ = Discount factor
## Environment
The project uses the CliffWalking-v1 environment provided by Gymnasium.

The environment consists of a grid where:

* The agent starts at the bottom-left.
* The goal is at the bottom-right.
* The cells between the start and goal represent the cliff.
* The agent receives a negative reward for normal movement.
* Falling into the cliff results in a large negative reward.
* Reaching the goal terminates the episode.

The objective of the agent is to learn a policy that allows it to reach the goal while avoiding the cliff.

## How SARSA Learns

The learning process is:

* Initialize the Q-table.
* Reset the environment and obtain the initial state.
* Select an action using an epsilon-greedy policy.
* Perform the action in the environment.
* Receive a reward and observe the next state.
* Select the next action using the same policy.
* Update the Q-value using the SARSA update rule.
* Move to the next state and action.
* Continue until the episode terminates.
* Repeat the process for multiple episodes.
* Epsilon-Greedy Policy

The agent uses an epsilon-greedy policy to balance exploration and exploitation.

With probability ε, the agent explores by selecting a random action.
Otherwise, the agent exploits the current knowledge by selecting the action with the highest Q-value.

This allows the agent to discover better paths while gradually using what it has learned.

## Training

The agent was trained for:

* 500 episodes
* Environment: CliffWalking-v1
* Algorithm: SARSA
* Learning method: Q-table
* Action selection: Epsilon-greedy

Example final training result:

Episode 500/500 : Total reward = -17 & Episode length = 17
Trained Agent Visualization

The GIF below shows the trained SARSA agent navigating the Cliff Walking environment using the learned Q-values.

## Visualization
<img width="682" height="257" alt="image" src="https://github.com/user-attachments/assets/98b7cbf1-3cf1-4dab-b009-b1571b16e1d8" />


## Technologies Used
Python
NumPy
Gymnasium
Reinforcement Learning
SARSA
Q-Table
Epsilon-Greedy Policy
