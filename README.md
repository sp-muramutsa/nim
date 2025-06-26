# 🧠 Q-Learning AI Agent in Nim Game
---

## 📖 Project Overview

This project implements a reinforcement learning agent that learns to play the classic game of **Nim** using **Q-learning**, one of the foundational algorithms in model-free **Reinforcement Learning (RL)**.

The AI learns by self-play and gradually builds an optimal strategy through reward-driven experience, using key concepts like:

* **Q-values** for estimating action quality
* **Epsilon-greedy exploration** for balancing learning vs exploiting knowledge
* **Learning rate (α)** to control how fast the agent adapts
* **State-action value updates** using temporal-difference learning

---

## 🎯 Core Concepts

| Concept           | Description                                                                |
| ----------------- | -------------------------------------------------------------------------- |
| **State**         | A tuple representing the number of items in each pile.                     |
| **Action**        | A tuple `(i, j)` representing the removal of `j` items from pile `i`.      |
| **Q-value**       | Estimate of expected future reward for a given `(state, action)` pair.     |
| **α (alpha)**     | Learning rate controlling how much new info overrides old knowledge.       |
| **ε (epsilon)**   | Probability of choosing a random action (exploration vs. exploitation).    |
| **Greedy policy** | Choosing the action with the highest known Q-value (best-so-far strategy). |

---

## 🧠 Q-Learning Algorithm

At the heart of the agent is the **Q-learning update rule**:

```
Q(s, a) ← Q(s, a) + α [reward + max(Q(s', a')) - Q(s, a)]
```

* `s` is the current state
* `a` is the action taken
* `s'` is the resulting state after the action
* `a'` is the next best action
* `α` is the learning rate
* `reward` is +1 (win), -1 (loss), or 0 (intermediate)

- Over thousands of training episodes, the agent refines its Q-values to approximate the optimal strategy.

- The AI uses a **greedy policy** (no exploration) during gameplay for optimal performance.

---

## 📊 Visual Example

```
PILES
Pile 0: ● 
Pile 1: ● ● ● 
Pile 2: ● ● ● ● ● 
Pile 3: ● ● ● ● ● ● ● 

Your Turn
Choose Pile: 2
Choose Count: 3

AI's Turn
AI chose to take 1 from pile 1.
```

---

## ⚙️ No Dependencies

The project uses **only Python standard libraries**:

* `random` for exploration
* `math`, `time` for utility and pacing
* No external packages or ML frameworks

---

## 🧱 Project Structure

```
nim_qlearning_ai/
├── nim.py         # Game logic and Q-learning implementation
├── play.py        # Calls the functions for self-play training loop and the agent-vs-human match-up 
└── README.md      # Project documentation
```

