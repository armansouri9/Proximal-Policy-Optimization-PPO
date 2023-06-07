# PPO Algorithm for Reinforcement Learning

This repository contains an implementation of the Proximal Policy Optimization (PPO) algorithm using PyTorch. PPO is a policy optimization algorithm commonly used in reinforcement learning tasks.

## Prerequisites
- Python 3.x
- PyTorch
- OpenAI Gym

## Usage
1. Install the required dependencies:
   ```bash
   pip install torch gym
   ```

2. Clone the repository:
   ```bash
   git clone https://github.com/your-username/repo-name.git
   ```

3. Navigate to the repository directory:
   ```bash
   cd repo-name
   ```

4. Run the PPO algorithm:
   ```bash
   python ppo.py
   ```

## PPO Algorithm Details
The PPO algorithm is implemented in the `ppo` function in the `ppo.py` file. It takes the following parameters:
- `env`: The environment for the RL task (e.g., 'CartPole-v1').
- `num_episodes`: The number of episodes to run.
- `max_steps`: The maximum number of steps per episode.
- `learning_rate`: The learning rate for the policy optimization.
- `clip_epsilon`: The epsilon value used for clipping the surrogate objective.

The `ppo` function executes the PPO algorithm by performing the following steps:
1. Define the policy model using a neural network architecture.
2. Initialize the optimizer for updating the policy.
3. Iterate over the specified number of episodes:
   - Reset the environment and initialize episode-specific variables.
   - Iterate over the maximum number of steps:
     - Select an action based on the current policy.
     - Calculate the log probability of the selected action.
     - Execute the action in the environment and observe the next state and reward.
     - Store the collected rewards, log probabilities, and predicted values.
     - If the episode is done, exit the inner loop.
   - Calculate the returns and advantages for each time step.
   - Update the policy using the PPO objective.
   - Print the actor and critic loss for the current episode.

The `calculate_returns` and `calculate_advantages` functions are used to compute the returns and advantages, respectively. The `update_policy` function performs the policy update using the PPO objective and returns the actor and critic loss.

## Acknowledgements
This implementation is inspired by the PPO algorithm described in the original paper ["Proximal Policy Optimization Algorithms"](https://arxiv.org/abs/1707.06347) by Schulman et al.

## License

This project is licensed under a Free License.
