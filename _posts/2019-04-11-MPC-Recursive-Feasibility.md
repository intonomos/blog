---
layout: post
title: Testing for recursive feasibility in MPC
excerpt: "A method to derive a certificate that linear MPC problem is recursively feasible."
categories: control
tags: control mpc
comments: true
---

One of the most fundamental problems in model predictive control (MPC) is the lack of guaranteed stability and feasibility.

**Feasibility**

The computations of optimal inputs may work for some time, but then, all of a sudden, the MPC controller has driven the state to a region where the optimization problem has no solution.

The typical approach is to append the optimization problem with additional, somewhat artificial constraints, that will guarantee that loss of feasibility cannot occur.

It is shown how Farkas’ Lemma in combination with bilevel programming and disjoint bilinear programming can be used to search for problematic initial states which lack recursive feasibility, thus invalidating a particular MPC controller.


**Problem Formulation**
$$
X_k =
\begin{bmatrix}
x_{k \vert k} \\
x_{k+1 \vert k} \\
\vdots \\
x_{k+N \vert k}
\end{bmatrix},
U_k =
\begin{bmatrix}
u_{k \vert k} \\
u_{k+1 \vert k} \\
\vdots \\
u_{k+N-1 \vert k}
\end{bmatrix}
$$
where
$$
x_{k+i+1 \vert k} = A x_{k+i \vert k} + B u_{k+i \vert k}
$$

By stacking constraints  and variables in a suitable fashion, it is straightforward to derive a model of the following quadratic programming form:
$$
U_k^* = \text{arg } \underset{U_k}{\text{min}} \frac{1}{2} U_k^\top H U_k + U_k^\top G x_k
$$
subject to
$$
E x_k + F U_k \leq b
$$

[Löfberg, Johan. "Oops! I cannot do it again: Testing for recursive feasibility in MPC." Automatica 48, no. 3 (2012): 550-555.](https://www.sciencedirect.com/science/article/pii/S0005109811005723){:target="_blank"}