# Nim AI - Reinforcement Learning with Q-Learning

## Overview
This project is an implementation of an AI that learns to play the game of Nim using **reinforcement learning**. Specifically, it employs **Q-learning**, a model-free reinforcement learning algorithm, to develop an optimal strategy by playing against itself repeatedly. It was developed as part of the CS50’s Introduction to Artificial Intelligence with Python course.

## Game Rules - Nim
Nim is a mathematical strategy game where:
- The game starts with multiple piles of objects.
- Players take turns removing **any number of objects** from a **single non-empty pile**.
- The player who takes the **last object** loses the game.

## AI Approach
The AI learns to play Nim using **Q-learning**, a method that assigns a **Q-value** (expected future reward) to each **(state, action)** pair. The AI improves its strategy over time by:
1. **Exploring and Exploiting** - Choosing actions based on learned Q-values while occasionally making random choices (epsilon-greedy strategy).
2. **Updating Q-values** - Using the Q-learning formula:

      Q(s, a) = Q(s, a) + α * (r + max Q(s', a') - Q(s, a))
     
      Where:
      - **α (alpha)** – learning rate, determining how much new information overrides old knowledge.
      - **r** – immediate reward received after taking action **a** in state **s**.
      - **max Q(s', a')** – highest expected reward from the next state **s'**.

   
4. **Training via Self-Play** - The AI plays thousands of games against itself to refine its decision-making.

## Installation and Setup
To get started, you need Python 3.12 installed.

1. Clone this repository
   ```sh
    git clone https://github.com/ognjenvujovic04/nim-ai.git
   ```
3. Run training and play against the AI:
   ```sh
   python play.py
   ```
   This will train the AI by playing 10,000 games against itself.

## Key Functions Implemented
### `NimAI` Class
- `get_q_value(state, action)`: Retrieves the Q-value for a given state-action pair.
- `update_q_value(state, action, old_q, reward, future_rewards)`: Updates the Q-value using the Q-learning formula.
- `best_future_reward(state)`: Returns the highest possible future reward from a given state.
- `choose_action(state, epsilon=False)`: Selects an action based on the epsilon-greedy strategy.

### Training and Playing
- `train(n)`: Runs `n` self-play games to train the AI.
- `play(ai)`: Allows a human player to compete against the trained AI.

## Future Improvements
- Implementing a **GUI** for a more interactive experience.

## Credits
This project is part of **Harvard’s CS50 AI** course.

