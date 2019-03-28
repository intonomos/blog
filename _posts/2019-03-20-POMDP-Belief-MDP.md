---
layout: post
title: POMDP and Belief MDP
excerpt: "A Markovian belief state allows a POMDP to be formulated as a MDP where every belief is a state."
categories: pomdp
tags: pomdp review
comments: no
---

![Markov Models](http://intonomos.com/blog/assets/markov_models_table.png)

A discrete-time POMDP models the relationship between an agent and its environment. Formally, a POMDP is a 7-tuple $$(S, A, T, R, \Omega, O, \gamma)$$, where
- $$S$$ is a set of states
- $$A$$ is a set of actions
- $$T$$ is a set of conditional transition probabilities between states
- $$R: S \times A \rightarrow \mathbb{R}$$ is the reward function
- $$\Omega$$ is a set of observations
- $$O$$ is a set of conditional observation probabilities
- $$\gamma$$ is the discount factor

At each time period
- the environment is in some state $$s \in S$$
- the agent takes an action $$a \in A$$
- the environment transits to state $$s'$$ with probability $$T(s'\vert s, a)$$
- the agent receives an observation $$o \in \Omega$$ with probability $$O(o \vert s', a)$$
- the agent receives a reward $$r = R(s, a)$$
- the goal of the agent is to choose an action that maximize its expected future discounted reward $$E\left[ \sum_{t=0}^{\infty} \gamma^t r_t \right]$$

The belief MDP is defined as a tuple $$(B, A, \tau, r, \gamma)$$, where
- $$B$$ is the set of belief states (probability distribution) over the POMDP states
- $$A$$ is the same as the original POMDP
- $$\tau$$ is the belief state transition function
- $$r: B \times A \rightarrow \mathbb{R}$$ is the reward function on belief states
- $$\gamma$$ is the same as the original POMDP

After having taken the action $$a$$ and observing $$o$$, an agent needs to update its belief in the state of the environment may (or not) be in.

Since the state is Markovian, maintaining a belief over the states solely requires knowledge of the previous belief state, the action taken and the current observation.

$$
\begin{aligned}
b'(s') &= \Tau(b(s), a, o)\\
   &=\frac{O(o' \vert s', a) \sum_{s \in S}T(s' \vert s, a)b(s)}{\sum_{s' \in S} O(o \vert s', a) \sum_{s \in S} T(s'\vert s, a) b(s)}
\end{aligned}
$$

Belief state transition function

$$
\begin{aligned}
\tau(b'(s), a, b(s)) &= \sum_{o \in \Omega} \text{Pr}(b'(s) \vert b(s), a, o)\text{Pr}(o \vert a, b(s)) \\
\text{Pr}(b' \vert b, a, o) &=
\begin{cases}
1, \text{ if } \Tau(b(s), a, o) == b'(s)\\ 
0, \text{ otherwise}
\end{cases} \\
\text{Pr}(o \vert a, b(s)) &= \sum_{s' \in S} O(o \vert s', a) \sum_{s \in S} T(s'\vert s, a) b(s)
\end{aligned}
$$

Reward function on belief states

$$
r(b(s), a) = \sum_{s \in S} b(s) R(s, a)
$$

[Wikipedia - Partially observable Markov decision process](https://en.wikipedia.org/wiki/Partially_observable_Markov_decision_process)

[Lecture Slides on POMDP by Prof. Geoff Hollinger Fall 2007](http://www.cs.cmu.edu/~ggordon/780-fall07/lectures/POMDP_lecture.pdf)

[]