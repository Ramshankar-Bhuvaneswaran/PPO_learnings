
# Proximal Policy Optimization (PPO) Explained

## Overview
Proximal Policy Optimization (PPO) is a policy gradient method for reinforcement learning, which balances the twin goals of sample efficiency (learning as much as possible from limited data) and ease of implementation. It is widely used due to its robustness and effectiveness across a variety of environments and tasks.

## Theoretical Background
PPO aims to improve the policy of an agent by optimizing a surrogate objective function. This function is designed to prevent the policy from changing too quickly and significantly, which can lead to unstable training dynamics and poor performance.

The core idea behind PPO is to take small, controlled steps to update the policy. This is achieved by clipping the probability ratio of the old and new policies, which bounds the amount of change that can be applied to the policy at each update.

## Practical Example

### Environment
Consider a simple game where an agent can move either left or right to reach a goal. The state is the position of the agent, and the actions are [left, right]. The reward is +1 for reaching the goal, and -1 for moving away from it.

### Algorithm Steps
1. **Initialize**: Start with a random policy \( \pi_{\theta_{old}} \).
2. **Collect Data**: Run the policy to collect data on states, actions, and rewards.
3. **Estimate Advantage**: Compute the advantage \( \hat{A}_t \), which measures how much better or worse an action is compared to the average.
4. **Optimize**: Update the policy by optimizing the clipped surrogate objective \( L^{CLIP}(\theta) \).
5. **Repeat**: Use the updated policy to collect new data, and repeat the process.


# Actor-Critic Method Explained

## Introduction
The Actor-Critic method is a type of reinforcement learning algorithm that combines aspects of both policy-based and value-based approaches. It involves two main components:
- **The Actor**: Determines the best action to take given a state.
- **The Critic**: Evaluates the action taken by the actor by computing the value function, which estimates how good a particular state or action is in terms of expected future rewards.


## Practical Example: Balancing a Cartpole

### Scenario Description
Consider the classic cartpole problem, where the goal is to balance a pole on a cart that moves along a track. The agent (actor) decides to either move the cart left or right, aiming to keep the pole upright.

### Steps:
1. **Initialize the Actor and Critic**: Both components are initialized with random weights.
2. **Collect Data**: The actor takes an action based on the current policy, and the state of the system changes.
3. **Compute the TD Error**: The critic evaluates the new state to compute the temporal difference error.
4. **Update the Critic**: Adjust the critic's parameters to better predict the value of each state.
5. **Update the Actor**: Use the TD error to improve the actor's policy, guiding it towards actions that lead to higher returns.
6. **Repeat**: This process repeats for many episodes, with the policy and value function progressively improving.
