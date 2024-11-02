# Reinforcement-Learning

## Running the Code

To run this Reinforcement Learning project, ensure that Python is installed on your local machine. Install the necessary Python packages using pip with the following command:

```bash
pip install .
```

Once all packages and files are installed. Execute the script using the command:

```bash
python autograder.py
```


# Q-Learning Agent

The `qlearningAgents.py` file implements a Q-Learning Agent, a reinforcement learning algorithm that learns an optimal policy by updating Q-values based on interactions with the environment. Unlike value iteration, Q-learning does not require a model of the environment and instead learns values from trial-and-error experience.

## Key Functions Implemented

### `getQValue(state, action)`
- Returns the Q-value for a given state-action pair.
- Defaults to 0 if the state-action pair has not been encountered before.
- Enables the agent to assess the desirability of each action from each state.

### `computeValueFromQValues(state)`
- Computes the maximum Q-value available from a given state, representing the best possible outcome the agent can expect from that state.
- Guides the agent in selecting the optimal action when learning a policy.

### `computeActionFromQValues(state)`
- Identifies the action with the highest Q-value from a given state.
- Allows the agent to choose the best action according to its current knowledge of Q-values, effectively forming the agent’s policy.

### `update(state, action, nextState, reward)`
- Updates the Q-value for a state-action pair using the Bellman equation.
- Incorporates the received reward and the discounted future rewards, helping the agent learn from each experience.

### `getPolicy(state)` and `getAction(state)`
- Return the best action for a given state based on current Q-values.
- `getAction` also includes exploration via epsilon-greedy selection, balancing exploration and exploitation.

## Contributions

In `qlearningAgents.py`, my contributions centered around implementing the core Q-learning functions, including `getQValue`, `computeValueFromQValues`, `computeActionFromQValues`, and `update`. These functions enable the agent to iteratively learn an optimal policy through reinforcement, adjusting Q-values based on experiences and rewards without prior knowledge of the environment.

# Value Iteration Agent

The `valueIterationAgent.py` file implements a Value Iteration Agent for a Markov Decision Process (MDP). This agent applies value iteration, a core algorithm in reinforcement learning, to compute an optimal policy for a given environment. The agent considers future rewards through a discount factor and iteratively refines its policy to maximize cumulative rewards.

## Key Functions Implemented

### `runValueIteration()`
- Iteratively computes the value of each state over a specified number of iterations.
- At each iteration, updates the value of each state by evaluating the potential rewards from each possible action.
- The values converge to an optimal policy that the agent can then follow.

### `computeQValueFromValues(state, action)`
- Calculates the Q-value for a given state-action pair using the Bellman equation.
- Considers the probability-weighted rewards for transitioning from the current state to potential next states under the given action.

### `computeActionFromValues(state)`
- Determines the optimal action for a given state by selecting the action with the highest Q-value.

## Other Classes

The file also contains additional agents that build on `ValueIterationAgent`:

- **`AsynchronousValueIterationAgent`**: This agent performs updates on one state per iteration in a cyclic order.
- **`PrioritizedSweepingValueIterationAgent`**: A more advanced agent that applies prioritized sweeping for more efficient convergence to an optimal policy.

## Contributions

My primary contributions in `valueIterationAgent.py` involved implementing the `runValueIteration`, `computeQValueFromValues`, and `computeActionFromValues` methods. These methods form the backbone of the value iteration algorithm, ensuring that the agent can determine and follow an optimal policy across states in the MDP.
