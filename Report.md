# Report

Following document describes solution algorithm and its results in detail.

Implementation is based on the code provided in Udacity github repo for solving pendulum environment.

## Learning Algorithm

Agent is trained using Deep Deterministic Policy Gradient (DDPG) algorithm, 
which finds both Q-function and policy using 2 neural networks trained concurrently.

This algorithm works well for continuous action spaces.

Policy network is called "Actor" and returns actions. Q-function network is called "Critic".
Networks are trained on data collected in replay buffer.
Same trick with target/local networks (as in DQN) is used to avoid training networks on direct outputs of themselves.

Additionally, during training noise is added to agent output to have exporation/exploitation balance. 
Amount of noise is gradually reduced during training.

Following hyper-params used:
 * Experience Replay buffer size: 10000
 * Batch size: 256
 * Gamma (discount factor): 0.99
 * Target/local networks update rate: 1e-3
 * Actor learning rate: 1e-3
 * Critic learning rate: 1e-3
 * Noise theta: 0.15
 * Noise sigma: 0.05
 * Noise decay: 0.999
 * Networks training frequency: 20 updates / every 20 steps

### Actor Network
Actor has following layers:
 * input: 33 features (environment state vector dimension)
 * linear (fully connected) layer: 37 x 128, with ReLU activation
 * Batch norm
 * linear (fully connected) layer: 128 x 128, with ReLU activation
 * linear (fully connected) layer: 128 x 4 (action vector size) with Tanh activation

### Critic Network
Critic has following layers:
 * input: 33 features (environment state vector dimension), 4 action vector
 * linear (fully connected) layer: 33 x 128, with ReLU activation
 * Batch norm
 * Action vector is concatenated with layer output
 * linear (fully connected) layer: 132 x 128, with ReLU activation
 * linear (fully connected) layer: 128 x 1

## Results
With given algorithm, Actor/Critic architecture and hyperparameters, the environment was solved in 126 episodes.

Following plot shows recorded episodes score and score averaged over 100 episodes:

![DDPG Score Plot](images/plot.jpg?raw=true "DDPG Score Plot")

## Ideas for Future Work
 * Try different algorithms: TRPO, TNPG, PPO
 * Try prioritized experience replay
 * Try different network architectures
 
 