---
layout: post
title: Data Driven Approach for Motion Planning Under Complex Scenario
excerpt: "Optimal and long term efficient policy under complex scenarios."
categories: planning
tags: planning data-driven
comments: true
---

Challenges:
- Optimal planning trajectory sacrifices planning efficiency.
- Search-based planning method cannot find desired trajectory in extreme scenarios.

Approach:
- Transform the lane change mission into Mixed Integer Quadratic Problem (MIQP) with logical constraints, which provides feasible, safe and comfort actions in more complex scenarios.
- Use of a hierarchical learning structure with *classification layer* and *action learning layer* to guarantee online, fast, and more generalized motion planning.

[Chenyang Xi, Tianyu Shi, and Jie Chen. "A Data Driven Approach for Motion Planning of Autonomous Driving Under Complex Scenario." arXiv preprint arXiv:1904.08784 (2019).](https://arxiv.org/abs/1904.08784){:target="_blank"}