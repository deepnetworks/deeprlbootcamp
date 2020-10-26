# Lecture 6. Nuts and Bolts of Deep RL (John Schulman)

## Approaching new problems 
- New algorithms
  - Run experiments quickly using small test problems
  - Visualize everything
    - State visitation
    - Value function
  - Construct toy problems where the algorithm is strong/weak
  - Have medium sized problems you're familiar with
    - Pong
    - Hopper
- New task
  - Make it easier until learning algorithms learns anything
    - Provide good (easier) input features
    - Shape the reward function
  - POMDP design
    - Visualize the random policy -> does it sometimes exhibit desired behavior
    - Make sure a human could complete the task given the observations
    - Plot time series for observations and rewards (make sure scaling is appropriate)
    - Histogram of observations and rewards
- Run your baselines
  - Cross-entropy method
  - Well-turned policy gradient method
    - [openai/baselines](https://github.com/openai/baselines)
    - [openai/spinningup](https://github.com/openai/spinningup)
    - [garage](https://github.com/rlworkgroup/garage)
  - Well-turned Q-learning + SARSA method
- Run with more samples than expected
  - Early in tuning process, may need huge number of samples
  - **Try using larger batch sizes**

## Ongoing development and tuning
- It works! But don't be satisfied
  - Explore sensitivity to each parameter
  - Look for health indicators
    - VF fit quality
    - Policy entropy
    - Update size in output space and parameter space
    - Standard diagnostics for deep networks
- Continually benchmark (and test) your code
  - Run a battery of benchmarks occasionally
- Always use multiple random seeds
- Always be ablating

## General tuning strategies for RL
- Whitening and standardizing data
  - Rescale rewards, but don't shift
- Generally important parameters
  - Effective time horizon = 1 / (1 - gamma) => convert this to real time
  - Check the action frequency; can the environment even be solved at this time discretization?
- Statistics
  - Look at min, max, mean, stdev of episode returns
  - Look at episode lengths

## Policy gradient strategies
- Policy entropy
  - Use entropy bonus or KL penalty
- KL divergence between policies
- Explained variance
  - (1 - Var(empirical return - predicted return)) / Var(empirical return)
- Policy initialization
  - More important that in supervised laerning -> determines initial state visitation
  - Zero or tiny final layer to maximize entropy

## Q-Learning strategies
- Optimize memory usage
- Learning rate schedules
- Exploration schedules

## Miscellaneous advice
- Read older textbooks and theses
- Don't get stuck on problems
  - RL algorithms don't always solve all the problems
- Techniques from supervised learning don't necessarily work in RL
  - Batch norm
  - Dropout
  - Big networks