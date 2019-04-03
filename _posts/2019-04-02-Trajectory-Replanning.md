---
layout: post
title: Real-time Trajectory Replanning for Autonomous Driving
excerpt: "a new scheme that simultaneously modifies the desired path and speed profile in emergency situations."
categories: planning
tags: paper planning
comments: true
---

The method for trajectory modification closely approximates the finite horizon optimal control problem by a convex QCQP which can be solved quickly on an autonomous vehicle.
- A nominal trajectory for the vehicle is decomposed into a path and a speed profile.
- Formulation
  - Kinematics and Dynamics
  - Constraints
    - Longitudinal force is limited by engine power.
    - The friction limit of a single tire is expressed by a friction circle.
    - Road topology has a dramatic effect on the tire normal loads.
    - Vehicle's acceleration limits can be improved by considering the friction limits of each axle independently and modeling longitudinal weight transfer.
  - Objective function: minimum lap time
- Implementation
  - Linearization
  - Discretization
    - Discretization points are evenly spaced in time along the nominal trajectory.
  - Slack variables
    - To ensure a solution always exists to the replanning problem, the friction circle constraint at each stage is implemented with a slack variable.
  - Terminal constraints and cost
    - To ensure that the transition between the replanned and nominal trajectory at the end of the planning horizon is seamless, terminal constraints are added,


[John K. Subosits and J. Christian Gerdes, From the Racetrack to the Road: Real-time Trajectory Replanning for Autonomous Driving, IEEE Transactions on Intelligent Vehicles, 2019](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8671749){:target="_blank"}