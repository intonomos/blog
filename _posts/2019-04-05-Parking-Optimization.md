---
layout: post
title: Autonomous Parking using Optimization-Based Collision Avoidance
excerpt: "A hierarchical parking algorithm that combines Hybrid A* path planner and optimization-based obstacle avoidance algorithm."
categories: optimization
tags: optimization parking
comments: true
---

On the higher level, Hybrid A* and a simplified vehicle model is used to quickly generate a coarse path that approximately satisfies the vehicle dynamics.

- Starting from the best expanded node, measured in terms of a heuristic function and a cost function, Hybrid A* uses a simplified vehicle model to create candidate nodes.
- All collision-free candidate nodes are connected to the goal node using analytical node expansion. If the path is collision-free, Hybrid A* terminates; otherwise, it goes back to the previous step.

Heuristic function: solution of the A* algorithm.

Cost function: penalizes path length, number of switchback points and steering angle.

On the lower level, optimization-based collision avoidance algorithm uses a full vehicle model to generate a high-quality collision-free parking path with the coarse path as initial solution.

Cost function:
- Final time
- Control efforts

Constraints:
- Initial condition
- Terminal condition
- Vehicle dynamics
- Input and state constraints
- Obstacle constraints defined using signed distance

[Zhang, Xiaojing, Alexander Liniger, Atsushi Sakai, and Francesco Borrelli. "Autonomous parking using optimization-based collision avoidance." In 2018 IEEE Conference on Decision and Control (CDC), pp. 4327-4332. IEEE, 2018.](https://ieeexplore.ieee.org/abstract/document/8619433/){:target="_blank"}