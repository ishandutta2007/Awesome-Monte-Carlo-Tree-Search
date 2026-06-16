# UCT (Upper Confidence Bounds applied to Trees)

UCT is the foundational algorithm of modern Monte Carlo Tree Search. It treats the selection of moves as a multi-armed bandit problem.

## 📊 How it Works
The selection policy uses the UCT formula:
$$\text{UCT} = \bar{X}_j + C \sqrt{\frac{\ln N}{n_j}}$$

## 🟦 Diagram
```mermaid
graph TD
    Root((Root)) --> A((A: 10/20))
    Root --> B((B: 5/20))
    Root --> C((C: 1/20))
    A --> A1[Selection]
    B --> B1[Exploration]
    C --> C1[Highly Unlikely]
```

## 📝 Details
- **First Used:** 2006
- **Seminal Paper:** [Bandit based Monte-Carlo Planning](https://link.springer.com/chapter/10.1007/11871842_29)
- **Strengths:** Mathematically sound, balances exploration and exploitation effectively.
- **Weaknesses:** Can be slow in games with very large branching factors.
