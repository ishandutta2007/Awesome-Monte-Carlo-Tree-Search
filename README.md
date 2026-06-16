# Awesome-Monte-Carlo-Tree-Search
## Monte Carlo Tree Search (MCTS)

Monte Carlo Tree Search (MCTS) is a heuristic search algorithm used for decision-making and optimal control. It builds a tree of potential actions and outcomes, using random sampling (rollouts) and statistical analysis to balance the **exploration** of new options with the **exploitation** of promising paths.

---

## 🔄 The 4 Phases of MCTS

MCTS relies on an iterative four-step loop to evaluate decisions:

1. **Selection**: Navigate from the root to a promising leaf node using a tree policy (like UCT).
2. **Expansion**: Add one or more unvisited child nodes to the selected leaf.
3. **Simulation (Playout)**: Play out the domain randomly from the new node to a terminal state (win/loss).
4. **Backpropagation**: Update visit counts and win/loss statistics on all nodes along the path back to the root.

---

## 🛠️ Core Types & Variants

| Variant | Year | Paper Link | Description & Primary Use |
| :--- | :--- | :--- | :--- |
| **UCT** (Upper Confidence Bounds applied to Trees) | 2006 | [Bandit based Monte-Carlo Planning](https://link.springer.com/chapter/10.1007/11871842_29) | Standard form using UCB1 formula to balance exploration and exploitation. Used in turn-based board games. |
| **AlphaGo MCTS** (Deep-Reinforcement MCTS) | 2016 | [Mastering the game of Go with deep neural networks and tree search](https://www.nature.com/articles/nature16961) | Replaces rollouts with Value/Policy networks. Used for complex combinatorial games like Chess and Go. |
| **RAVE** (Rapid Action Value Estimation) | 2007 | [Combining Online and Offline Knowledge in UCT](https://icml.cc/Conferences/2007/proceedings/papers/387.pdf) | Aggregates move statistics globally to speed up learning. Primarily used in the game of Go. |
| **Progressive Widening** | 2007 | [Computing Elo Ratings of Move Patterns in the Game of Go](https://www.remi-coulom.fr/publications/alife-2007.pdf) | Manages large branching factors by limiting child expansion. Used in continuous action spaces and robotics. |
| **Open-Loop vs. Closed-Loop MCTS** | 2010 | [Open Loop Optimistic Planning](https://hal.archives-ouvertes.fr/hal-00520428/document) | Open-Loop stores action sequences; Closed-Loop stores states. Used in non-deterministic environments. |

---

## 🌍 Real-World Examples & Applications

*   **Board Games**: Tic-Tac-Toe, Chess, Checkers, and Go (AI computes future branches to guarantee a win or draw).
*   **Video Game AI**: Turn-based strategy (e.g., *Total War* campaign AI) and RTS games to plan multiple steps ahead.
*   **Robotics & Autonomous Driving**: Evaluates dynamic future scenarios (e.g., pedestrian movement) without requiring a completely predefined state space.
*   **Optimization Problems**: Logistics scheduling, vehicle routing, and chemical molecule generation.
