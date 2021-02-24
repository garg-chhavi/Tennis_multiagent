# Tennis playing agents 

## Learning Algorithm

The learning algorithm used in this project is Multi Agent Deep Deterministic Policy Gradients (MADDPG). The algorithm consists of 2 seperate agents each with set of 2 neural networks - actor and critic.

The actor network takes observation as an input and outputs actions. The critic network is used to compute state-action values. It outputs 1 real number - state value estimate for the given agent. It takes actions and observations from each agent as an input.

## Stopping Criteria

The environment was considered solved when the agent achieved average of 0.5+ over 100 episodes.


## Model Architecture and hyperparameters

### Layers

Both actor & critic use two fully connected layers followed by batch normalization

### Activations

Actor network: RELU activation is used for the hidden layers and tanh activation for the final layer for the actor network.

Critic network: RELU activation is used for the hidden layers.

### Hyperparameters

Hyperparameters used are

# Training hyperparameters

| Hyperparameter                      | Value |
| ----------------------------------- | ----- |
| Replay buffer size                  | 1e5   |
| Batch size                          | 512  |
| gamma (discount factor)          | 0.99  |
| tau                              | 1e-3  |
| Actor Learning rate                 | 1e-3  |
| Critic Learning rate                | 1e-3  |

## Rewards

The best performance was achieved by **MADDPG** where the reward of +0.5 was achieved in 3710 episodes (Environment solved in 3610 episodes). 

![maddpg](./score.png?raw=true "Title") 

## Future Improvements:

Implement Prioritized Experience Replay from the DQN paper to further reduce training time.
Test other weight initialization methods, to see if training time can be systematically reduced.
