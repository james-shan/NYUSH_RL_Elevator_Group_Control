# Elevator Group Control Systems via Deep Reinforcement Learning

This repository contains the code and documentation for the final project of CSCI-SHU 375 (Reinforcement Learning) at NYU Shanghai. The project explores the application of Deep Reinforcement Learning (DRL) algorithms to optimize Elevator Group Control Systems (EGCS). The project was supervised by Mathieu Laurière.

---

## Project Overview

Elevators are essential in modern high-rise buildings, and optimizing their operation is a complex yet crucial task. This project investigates the use of Deep Reinforcement Learning to develop efficient elevator scheduling policies, minimizing Average Waiting Time (AWT) and addressing the challenges of multi-agent environments.

The study includes:
- Single-agent implementations of Proximal Policy Optimization (PPO) and Advantage Actor-Critic (A2C) using the RLevator environment.
- Multi-agent Deep Q-Network (DQN) and PPO implementations in a complex elevator environment.

Despite promising results in simplified environments, challenges in scalability and partial observability were observed in multi-agent implementations.

---

## Environment

### State Space
The state includes:
- Hall calls and car calls.
- Elevator positions.
- Passenger queues and waiting times.

### Action Space
Each elevator can:
- Stay idle, move up or down, load/unload passengers, or take no action.
- Actions are constrained by passenger demands and system rules.

### Reward Function
The reward function is designed to:
- Incentivize passenger destination reach and movement towards destinations.
- Penalize long waits, full queues, and inefficient elevator usage.

---

## Algorithms

### Implemented Algorithms
1. **Deep Q-Network (DQN)**: Modified for multi-discrete action spaces.
2. **Advantage Actor-Critic (A2C)**: Stable in high-dimensional spaces with reduced variance using TD error-based advantage estimation.
3. **Proximal Policy Optimization (PPO)**: Incorporates clipping to maintain policy stability.

### Key Features
- Custom modifications to adapt algorithms for EGCS.
- Multi-agent setup for decentralized decision-making.

---

## Results

The training results demonstrated:
- **DQN** converges faster due to sample efficiency via replay buffers.
- **A2C** showed higher fluctuations compared to **PPO**, due to its sensitivity in policy space updates.
- Limited success in multi-agent settings due to high-dimensional action spaces and partial observability.

---

## Implementation Details

- **Environment Configuration**: 3 elevators, 6 floors, 10-passenger capacity per elevator.
- **Training Parameters**:
  - DQN: Learning rate `1e-3`, replay buffer size `1e5`, batch size `256`.
  - A2C & PPO: Learning rate `3e-4`, total timesteps `5M`, batch size `256`.

---

## Challenges

1. **State Space Complexity**: Limited observations hinder agent learning.
2. **Action Space Expansion**: Larger action spaces increase difficulty in policy learning.
3. **Multi-Agent Settings**: Coordination between agents proved challenging.

---

## Future Work

To address the observed limitations, future directions include:
- Enhancing agent observability.
- Exploring hierarchical or meta-learning approaches for multi-agent coordination.
- Adapting reward shaping techniques to simplify learning.

---

## References

1. RLevator: A Farama Gymnasium Environment for Elevator Control ([link](https://mwburke.github.io/RLevator))
2. Siikonen, M.-L., "Elevator Traffic Simulation," 1993.
3. Crites, R. H., & Barto, A. G., "Elevator Group Control Using Multiple Reinforcement Learning Agents," 1998.

---

## Contact

For questions or collaborations, please reach out to the project contributors:

- David Li
- Keith Wang
- Michael Yuan
- Zhihao Shan
  
