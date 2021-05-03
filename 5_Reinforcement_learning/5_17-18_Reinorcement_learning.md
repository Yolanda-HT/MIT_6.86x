## Reinforcement Learning

- Markov decision processes (MDP)
- Bellman equations
- Value Iteration Algorithm

## RL Terminology

**A Markov desicion process (MDP) is defined by:**
- A set of states s belong to S;
- A set of actins a belong to A;
- Action dependent transition probabilities T(s, a, s') = P(s' | s, a). For each state s and action a, sum of T(s, a, s') = 1
- Reward function R(s, a, s'), representing the reward for starting in state s, taking action a and ending up in state s' after one step (The reward function may also depend only on s, or only s and a). 
- MDP = <S, A, T, R>

MDPs satisfy the Markov property in that the transition probabilities and rewards depend only on the current state and action, and remain unchanged regardless of the history (i.e. past states and actions) that leads to the current state.

*[Introduction to Markov chains](https://towardsdatascience.com/brief-introduction-to-markov-chains-2c8cab9c98ab)*

## Utility Function

Bounded utility function:
- Final horizon: U([s(0), s(1), ..., s(N+k)]) = U([s(0), s(1), ..., s(N)]) for any k
- (Infinite horizon) discounted reward: U([s(0), s(1), ..., ]) = R(s(0)) + gamma * R(s(1)) + gamma^2 * R(s(2)) ...

## Policy

## Bellman Equations

