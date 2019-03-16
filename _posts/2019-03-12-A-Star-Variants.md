---
layout: post
title: A* Variants Overview
excerpt: "Brief overview of A* path planning algorithms."
categories: overview planning
tags: overview planning a-star
comments: no
---

$$
f = w_g g + w_h h
$$

- $$w_g = 1$$, $$w_h = 0$$: Dijkstra's Algorithm.
- $$w_g = 0$$, $$w_h = 1$$: Greedy Best-First Search.
- $$w_g = 1$$, $$w_h = 1$$: Regular A* Algorithm.
- $$w_g = 1$$, $$w_h = w > 1$$: Weighted A* Algorithm.

- Anytime Repairing A* (ARA*)
- Block A*
- D*
- Field D*
- Fringe Saving A* (FSA*)
- Generalized Adaptive A* (GAA*)
- Iterative Deepening A* (IDA*)
- Lifelong Planning A* (LPA*)
- Theta*
- Anytime A*
- Anytime Dynamic A*