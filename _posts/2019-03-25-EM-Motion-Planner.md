---
layout: post
title: Baidu Apollo EM Motion Planner
excerpt: "A motion planner based on expectation maximization-type iterative algorithm."
categories: planning
tags: paper planning
comments: true
---

This planner targets safety and ride experience with a multi-lane, path-speed iterative, traffic rule and decision combined design.

Architecture
- Reference Line Generator
- For each of reference line in Frenet Frame
  - SL projection (E-step)
  - Path optimization (M-step)
    - Path decision using Dynamic Programming
      - Cost functional: vehicle dynamics + SL map & obstacle information + traffic regulations
      - Path lattice: lattice sampling strategy
      - Results: DP path + feasible tunnel + nudge decision
    - Path planning using Quadratic Programming
      - Cost functional: DP path + smooth functional
      - Linearized constraints: feasible tunnel + vehicle dynamics
      - Result: smooth path
  - ST projection (E-step)
  - Speed optimization (M-step)
    - Speed decision using Dynamic Programming
      - Cost functional: vehicle dynamics + ST map & obstacle information + traffic regulations
      - Discretized ST grid
      - Results: DP speed + feasible tunnel + speed decisions
    - Speed planning using Quadratic Programming
      - Cost functional: DP speed + smooth functional
      - Linearized constraints: feasible tunnel + vehicle dynamics + traffic regulations
      - Result: smooth speed
- Reference Line Trajectory Decider

[Baidu Apollo EM Motion Planner](https://arxiv.org/abs/1807.08048)