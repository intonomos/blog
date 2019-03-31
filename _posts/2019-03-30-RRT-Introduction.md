---
layout: post
title: Introduction to RRT
excerpt: "A brief introduction to rapidly-exploring random tree."
categories: planning
tags: rrt planning
comments: true
---

A rapidly exploring random tree (RRT) is an algorithm designed to efficiently search non-convex, high-dimensional spaces by randomly building a space-filling tree. The tree is constructed incrementally from samples drawn randomly from the search space and is inherently biased to grow towards large unsearched areas of the problem.

An RRT can be viewed as a technique to generate open-loop trajectories for nonlinear systems with state constraints.

An RRT can be considered as a Monte-Carlo method to bias search into the largest Voronoi regions of a graph in a configuration space.

```
Algorithm BuildRRT
  Input: initial configuration qinit,
         number of vertices in RRT K,
         incremental distance Δq
  Output: RRT graph G

  G.init(qinit)
  for k = 1 to K
    qrand ← RAND_CONF()
    qnear ← NEAREST_VERTEX(qrand, G)
    qnew ← NEW_CONF(qnear, qrand, Δq)
    G.add_vertex(qnew)
    G.add_edge(qnear, qnew)
  return G
```

```RAND_CONF``` grabs a random configuration ```qrand``` in ```C```.

```NEAREST_VERTEX``` is a function that runs through all vertices ```v``` in graph ```G```, calculates the distance between ```qrand``` and ```v``` using some measurement function thereby returning the nearest vertex.

```NEW_CONF``` selects a new configuration ```qnew``` by moving an incremental distance ```Δq``` from ```qnear``` in the direction of ```qrand```. 


[Wikipedia: Rapidly-exploring random tree](https://en.wikipedia.org/wiki/Rapidly-exploring_random_tree){:target="_blank"}

[Sampling-based Motion Planning in Theory and Practice by Wolfgang A. Pointner](https://static1.squarespace.com/static/559921a3e4b02c1d7480f8f4/t/585c2dc6e6f2e1539f382f7e/1482436048661/Pointner.pdf){:target="_blank"}

[The Rapidly-Exploring Random Tree (RRT) Page - Steven M. LaValle](http://msl.cs.uiuc.edu/rrt/){:target="_blank"}