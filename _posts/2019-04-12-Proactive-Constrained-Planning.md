---
layout: post
title: Proactive Autonomous Driving with Road Users
excerpt: "For motion planning and control of autonomous vehicles to be proactive and safe, pedestrians’ and other road users’ motions must be considered."
categories: planning
tags: planning mpc
comments: true
---

The objective of the vehicle is to safely follow any given path as close as possible, while driving comfortably and satisfying constraints arising from the physical limitations, but also other road users, e.g pedestrians, cyclists and other vehicles.

Nonlinear Program
$$
\begin{aligned}
\underset{x, u}{\text{minimize }}
& \sum_{k = 0}^{N - 1}
\begin{bmatrix}
x_k - x_k^r \\
u_k - u_k^r
\end{bmatrix}^\top
W_k
\begin{bmatrix}
x_k - x_k^r \\
u_k - u_k^r
\end{bmatrix} +
\begin{bmatrix}
x_N - x_N^r
\end{bmatrix}^\top
W_N
\begin{bmatrix}
x_N - x_N^r
\end{bmatrix}\\
\text{subject to }
& x_0 = \hat{x}_0 \\
& x_{k + 1} = f(x_k, u_k) \\
& h(x_{k}, u_{k}) \leq 0
\end{aligned}
$$

Quadratic Program
$$
\begin{aligned}
\underset{x, u}{\text{minimize }}
& \sum_{k = 0}^{N - 1}
\begin{bmatrix}
x_k - x_k^r \\
u_k - u_k^r
\end{bmatrix}^\top
\begin{bmatrix}
Q_k & S_k \\
S_k^\top & R_k
\end{bmatrix}
\begin{bmatrix}
x_k - x_k^r \\
u_k - u_k^r
\end{bmatrix} +
\begin{bmatrix}
x_N - x_N^r
\end{bmatrix}^\top
Q_N
\begin{bmatrix}
x_N - x_N^r
\end{bmatrix}\\
\text{subject to }
& x_0 = \hat{x}_0 \\
& x_{k + 1} = A x_k + B u_k + b_k \\
& d_k^{\min} \leq C_k x_k + D_k u_k \leq d_k^{\max} \\
& d_N^{\min} \leq C_N x_N \leq d_N^{\max}
\end{aligned}
$$

- Reference Generation
- Cost Function
  - Penalize the lateral deviation from the path
- System Constraints
  - Road boundary constraints
  - Pedestrain constraints


[Batkovic, Ivo, Mario Zanon, Mohammad Ali, and Paolo Falcone. "Real-time constrained trajectory planning and vehicle control for proactive autonomous driving with road users." arXiv preprint arXiv:1903.07743 (2019).](https://arxiv.org/abs/1903.07743){:target="_blank"}