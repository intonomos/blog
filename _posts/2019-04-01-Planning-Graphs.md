---
layout: post
title: Graphs Used in Planning
excerpt: "Comparison of search space for planning"
categories: planning
tags: planning graphs
comments: true
---

Voronoi Diagrams or Dirichlet tessellation techniques
- Advantages:
  - They generate paths which **maximize the distance** between the vehicle and surrounding obstacles.
  - Searching on Voronoi Diagram is **complete** in the sense that, if a path exists in the free space, it would also appear on the Voronoi Diagram.
- Disadvantages:
  - They are typically used for planning in **static environment**, such as parking lots.
  - Voronoi edges, along which a vehicle navigates, can potentially be **discontinuous** and unsuitable for non-holonomic vehicle.

Occupancy grids and cost maps both discretize the state space into a grid and each cell of the grid is associated with a probability of the cell being occupied by an obstacle ot a cost proportional to the feasibility or risk level.
- Advantages:
  - Discretization of continuous space using repetition of rectangles and squares is **fast**.
  - Grid-based approaches are fast in finding a solution with **low computation power**.
- Disadvantages:
  - They have difficulty in accounting for **nonlinear dynamics** in a robust way, and in the presence of **obstacles**.

State Lattices can be seen as a generalization of grids. Lattices are constructed by regularly repeating primitive paths which connect possible states for the vehicle, in terms of position, curvature or time.
- Advantages:
  - They overcome the limitations of grid-based techniques in **efficiency** without increasing computational power.
  - **Pre-computation of edges** is possible.
- Disadvantages:
  - Problems with curvature
  - Restrict motion
  - Difficulties in dealing with evasive maneuvers

Driving Corridors represents a continuous collision-free space, bounded by road and lane boundaries as well as other obstacles, where a vehicle is expected to move.
- Advantages:
  - They generate **continuous collision-free space** for the vehicle to move.
- Disadvantages:
  - **Intensive computation power** is needed for planning for the entire range of coordinates regarding the road network.
  - Representation of roads or lanes may **constrain the motion** of the vehicle.

[Katrakazas, Christos, Mohammed Quddus, Wen-Hua Chen, and Lipika Deka. "Real-time motion planning methods for autonomous on-road driving: State-of-the-art and future research directions." Transportation Research Part C: Emerging Technologies 60 (2015): 416-442.](https://www.sciencedirect.com/science/article/pii/S0968090X15003447){:target="_blank"}