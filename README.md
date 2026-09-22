# Nim Game AI

## Overview

This project implements the game of Nim and an AI agent that learns how to choose moves using Q-learning.

The game contains several piles of objects. A move removes one or more objects from a single pile. The player who takes the final object wins.

## Game Logic

The `Nim` class manages:

- The current pile sizes.
- The active player.
- Available moves.
- Player switching.
- Move validation.
- Winner detection.

An action is represented as a tuple containing the pile index and number of objects to remove.

## Q-Learning AI

The `NimAI` class stores Q-values for state-action pairs.

The implementation includes:

- Q-value lookup.
- Q-value updates.
- Best future reward calculation.
- Epsilon-greedy action selection.

The Q-learning update uses the standard form:

`Q(s,a) <- Q(s,a) + alpha * (reward + future_reward - Q(s,a))`

with `alpha` controlling the learning rate.

During exploration, the AI occasionally chooses a random valid move according to the configured epsilon value.

## Training

The `train` function makes the AI play repeated games against itself. Rewards are assigned according to the outcome of the game, allowing Q-values to improve over many training rounds.

The included `play.py` script trains the agent for 10,000 games and then starts a human-versus-AI game.

## Project Structure

| File | Purpose |
| --- | --- |
| `nim.py` | Implements the Nim game, Q-learning agent, training process, and interactive play. |
| `play.py` | Trains the AI and starts a game against a human player. |

## Running

```bash
python play.py
```

The script first trains the AI and then starts the game.

## Key Concepts

- Reinforcement learning
- Q-learning
- Epsilon-greedy exploration
- State-action values
- Reward-based learning
- Game-state modeling
