---
layout: post
title: POMDP and Belief MDP
excerpt: "A Markovian belief state allows a POMDP to be formulated as a MDP where every belief is a state."
categories: pomdp
tags: pomdp review
comments: no
---

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
- $$B$$ is the set of belief states over the POMDP states
- $$A$$ is the same as the original POMDP
- $$\tau$$ is the belief state transition function
- $$r: B \times A \rightarrow \mathbb{R}$$ is the reward function on belief states
- $$\gamma$$ is the same as the original POMDP

To be continued ...

[Wikipedia - Partially observable Markov decision process](https://en.wikipedia.org/wiki/Partially_observable_Markov_decision_process)
