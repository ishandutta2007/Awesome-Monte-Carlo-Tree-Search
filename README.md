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

### 1. UCT (Upper Confidence Bounds applied to Trees)
*   **Definition**: The standard, foundational form of MCTS.
*   **Mechanism**: Uses the Multi-Armed Bandit formula to balance exploration and exploitation:
    $$\text{UCT} = V_i + C \sqrt{\frac{\ln(N)}{n_i}}$$
    *(Where $V_i$ is node value, $N$ is parent visits, $n_i$ is child visits, and $C$ is the exploration constant).*
*   **Primary Use**: Turn-based board games and fundamental pathfinding.

### 2. AlphaGo MCTS (Deep-Reinforcement MCTS)
*   **Definition**: A hybrid algorithm made famous by DeepMind's AlphaGo and AlphaZero.
*   **Mechanism**: Replaces traditional random "rollout" simulations with Deep Neural Networks. It uses a **Value Network** to estimate state values and a **Policy Network** to guide action selection, drastically speeding up decision-making.
*   **Primary Use**: Complex combinatorial games like Chess, Shogi, and Go.

### 3. RAVE (Rapid Action Value Estimation)
*   **Definition**: A modification designed to speed up learning in large, complex trees.
*   **Mechanism**: Aggregates statistics for moves regardless of where they are played in the tree, rather than only updating the exact sequence sequence. Uses an adaptive weight factor ($\alpha$) to transition to standard MCTS stats over time.
*   **Primary Use**: The game of Go, where early moves have board-wide, long-lasting impacts.

### 4. Progressive Widening
*   **Definition**: An approach to manage extremely large or infinite branching factors (possible moves).
*   **Mechanism**: Limits the number of child nodes expanded at any given state based on the number of times that state has been visited. As visit counts increase, more action actions are unlocked for expansion.
*   **Primary Use**: Continuous action spaces in robotics or games with highly varied move types.

### 5. Open-Loop vs. Closed-Loop MCTS
*   **Open-Loop**: Records the sequence of actions taken regardless of the state reached. The tree is built purely based on *actions*.
*   **Closed-Loop**: Records both the action and the resulting state. The tree accounts for the fact that a specific action could lead to varying states.
*   **Primary Use**: Non-deterministic environments, robotics, and dynamic autonomous agent navigation.

---

## 🌍 Real-World Examples & Applications

*   **Board Games**: Tic-Tac-Toe, Chess, Checkers, and Go (AI computes future branches to guarantee a win or draw).
*   **Video Game AI**: Turn-based strategy (e.g., *Total War* campaign AI) and RTS games to plan multiple steps ahead.
*   **Robotics & Autonomous Driving**: Evaluates dynamic future scenarios (e.g., pedestrian movement) without requiring a completely predefined state space.
*   **Optimization Problems**: Logistics scheduling, vehicle routing, and chemical molecule generation.
