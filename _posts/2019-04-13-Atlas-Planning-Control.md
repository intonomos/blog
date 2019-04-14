---
layout: post
title: Planning, Estimation, and Control for the Atlas Humanoid Robot
excerpt: ""
categories: humanoid
tags: humanoid
comments: true
---

**Motion Planning**

Motion planning for legged systems is a fundamentally mixed discrete and continuous optimization problem. 

Planning algorithms must decide where and when contacts with the environment are initiated or broken and, during periods of unchanging contact, the system must typically move smoothly while maintaining balance and achieving a desired motion or interaction with the environment. 

For typical walking tasks, the discrete phase are decomposed into two parts. 
- analyze the environment and compute a set of convex regions where contacts are allowed.
- solve an optimization problem that assigns contacts to these regions in a way that minimizes cost while respecting kinematic and dynamic constraints.

**Control**

Given a planned trajectory for a reduced model of the dynamics (e.g., centroidal dynamics), a time-varying linearization is computed around the trajectory and derive a stabilizing controller using time-varying linear-quadratic regulator (TV-LQR) design. 

But rather than using the closed-form optimal controller from LQR, a quadratic program (QP) is formulated and solved that additionally captures the instantaneous dynamics, input, and contact constraints of the full walking system.

**State Estimation**

The controller requires a high-rate, low-latency estimate of the full state of the robot at every control step.

The sensors that are available for use in state estimation comprise an accurate inertial measurement unit (IMU) attached to the pelvis, joint position sensors at each joint, as well as exteroceptive sensors: LIDAR and vision.


[Kuindersma, Scott, Robin Deits, Maurice Fallon, Andrés Valenzuela, Hongkai Dai, Frank Permenter, Twan Koolen, Pat Marion, and Russ Tedrake. "Optimization-based locomotion planning, estimation, and control design for the atlas humanoid robot." Autonomous Robots 40, no. 3 (2016): 429-455.](https://link.springer.com/article/10.1007/s10514-015-9479-3){:target="_blank"}