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
  - 

## Ongoing development and tuning

## General tuning strategies for RL

## Policy gradient strategies

## Q-Learning strategies

## Miscellaneous advice