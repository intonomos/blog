---
layout: post
title: Frenet–Serret Formula
excerpt: "Frenet Frame method asserts invariant tracking performance under the action of the special Euclidean group SE(2)"
categories: planning
tags: planning coordinates
comments: true
---

Rather than formulating the trajectory generation problem directly in Cartesian Coordinates $$\vec{x}$$, the problem is formulated to generate a one-dimensional trajectory for both the root point $$\vec{r}$$ along the center line and the perpendicular offset $$d$$ with the relation:

$$
\vec{x}\left(s(t), d(t)\right) = \vec{r}\left(s(t)\right) + d(t) \vec{n}_r\left(s(t)\right)
$$

Cartesian Coordinate States:

$$
[x, y, \theta, v, a, \kappa]
$$

Reference States:

$$
[s_r, x_r, y_r, \theta_r, \kappa_r, \dot{\kappa}_r]
$$

Frenet Coordinate States:

$$
[s, \dot{s}, \ddot{s}, d, \dot{d}, \ddot{d}]
$$

Relationships:

$$
\begin{aligned}
d &= \text{sign}\left[(x - x_r) \cos(\theta_r) - (y - y_r)\sin(\theta_r)\right] \sqrt{(x - x_r)^2 + (y - y_r)^2} \\
\dot{d} &= \frac{\mathrm{d}d}{\mathrm{d}s} = (1 - \kappa_r d) \tan(\theta - theta_r)\\
\ddot{d} &= \frac{\mathrm{d}^2d}{(\mathrm{d}s)^2} \\
s &= s_r \\
\dot{s} &= \frac{\mathrm{d}s}{\mathrm{d}t} = \frac{v\cos(\delta - \delta_r)}{1 - \kappa_r d} \\
\ddot{s} &= \frac{\mathrm{d}^2s}{(\mathrm{d}t)^2}
\end{aligned}
$$

[Wikipedia: Frenet–Serret Formulas](https://en.wikipedia.org/wiki/Frenet%E2%80%93Serret_formulas){:target="_blank"}

[Werling, Moritz, Julius Ziegler, Sören Kammel, and Sebastian Thrun. "Optimal trajectory generation for dynamic street scenarios in a frenet frame." In 2010 IEEE International Conference on Robotics and Automation, pp. 987-993. IEEE, 2010.](https://ieeexplore.ieee.org/document/5509799/citations?tabFilter=papers#citations){:target="_blank"}

[Apollo项目坐标系研究](https://blog.csdn.net/davidhopper/article/details/79162385){:target="_blank"}