---
layout: post
title: Dubins Path
excerpt: "Shortest curve that connects two points in 2D Euclidean plane."
categories: planning
tags: planning graphs
comments: true
---

Dubins path is the shortest curve that connects two points in the 2D Euclidean plane with a constraint on the curvature of the path and with prescribed initial and terminal tangents to the plant, and an assumption that the vehicle traveling the path can only travel forward.

If the vehicle can also travel in reverse, then the path follows the Reeds-Shepp Curve.

The optimal path type can be described using an analogy with cars of making a 'right turn (R)' , 'left turn (L)' or driving 'straight (S).' An optimal path will always be at least one of the six types: RSR, RSL, LSR, LSL, RLR, LRL.

![dubins paths](https://intonomos.com/blog/assets/dubins_paths.png)

[Wikipedia: Dubins Path](https://en.wikipedia.org/wiki/Dubins_path){:target="_blank"}

[Time-Optimal Trajectories - Algorithms for Planning and Control of Robot Motion](http://www.robotmotion.org/time-optimal){:target="_blank"}

[Dubins car shortest paths: Decidable?](https://mathoverflow.net/questions/182142/dubins-car-shortest-paths-decidable){:target="_blank"}

[Huifang Elizabeth Wang's PhD thesis](https://sites.google.com/site/elizabethhw/research){:target="_blank"}