---
layout: post
title: Continuous System Discretization
excerpt: "Brief overview of discretization methods."
categories: overview modeling
tags: overview modeling discretization
comments: true
---

### Continues-Time System

Linear System:

$$
\dot{x} = Ax + Bu\\
A \in \mathbb{R}^{n \times n}, B \in \mathbb{R}^{n \times m} \\
x \in \mathbb{R}^{n \times 1}, u \in \mathbb{R}^{m \times 1}
$$

Nonlinear System:

$$
\dot{x} = f(x, u) \\
f: \mathbb{R}^{n} \times \mathbb{R}^{m} \rightarrow \mathbb{R}^{n}\\
x \in \mathbb{R}^{n}, u \in \mathbb{R}^{m}
$$

### Discretization

Exact for linear system

$$
\begin{aligned}
x(k+1) &= A_d x(k) + B_d u(k)\\
A_d &= e^{A \Delta t}\\
B_d &= A^{-1}(A_d - I) B
\end{aligned}
$$

$$e^{A \Delta t}$$ Approximation

$$
e^{A \Delta t} \approx (I - A \Delta t)^{-1}
$$

$$
e^{A \Delta t} \approx \left(I + \frac{1}{2} A \Delta t\right)\left(I - \frac{1}{2} A \Delta t\right)^{-1}
$$

which is known as bilinear transform or Tustin transform, and it preserves the (in)stability of the continuous-time system.

Forward Euler

$$
x(k+1) \approx (A \Delta t + I) x(k) + (B \Delta t) u(k)
$$

$$
x(k+1) \approx  x(k) + f(x(k), u(k)) \Delta t
$$

Explicit midpoint method

$$
x(k+1) \approx x(k) + f\left(x(k) + \frac{\Delta t}{2}f(x(k), u(k)), u(k)\right) \Delta t
$$

Classic fourth-order method

$$
\begin{aligned}
x(k+1) &\approx x(k) + \frac{\Delta t}{6}(v_1 + 2v_2 + 2v_3 + v_4)\\
v_1 &= f\left(x(k), u(k)\right) \\
v_2 &= f\left(x(k) + \frac{v_1}{2}, u(k)\right) \\
v_3 &= f\left(x(k) + \frac{v_2}{2}, u(k)\right) \\
v_4 &= f\left(x(k) + v_3, u(k)\right)
\end{aligned}
$$


[Wikipedia: Discretization](https://en.wikipedia.org/wiki/Discretization){:target="_blank"}

[Wikipedia: Euler method](https://en.wikipedia.org/wiki/Euler_method){:target="_blank"}

[Wikipedia: Midpoint method](https://en.wikipedia.org/wiki/Midpoint_method){:target="_blank"}

[Wikipedia: Runge–Kutta methods](https://en.wikipedia.org/wiki/Runge%E2%80%93Kutta_methods){:target="_blank"}

[Wikipedia: List of Runge–Kutta methods](https://en.wikipedia.org/wiki/List_of_Runge%E2%80%93Kutta_methods){:target="_blank"}

[Pepy, Romain, Alain Lambert, and Hugues Mounier. "Path planning using a dynamic vehicle model." In 2006 2nd International Conference on Information & Communication Technologies, vol. 1, pp. 781-786. IEEE, 2006.](http://www.cs.cmu.edu/~motionplanning/reading/PlanningforDynamicVeh-1.pdf){:target="_blank"}

[Lecture on Sampling by Prof. Alberto Bemporad](http://cse.lab.imtlucca.it/~bemporad/teaching/ac/pdf/AC2-03-Sampling.pdf){:target="_blank"}

[Lempio, Frank, and Vladimir Veliov. "Discrete approximations of differential inclusions." Bayreuther Mathematische Schriften 54 (1998): 149-232.](http://num.math.uni-bayreuth.de/en/publications/1998/lempio_et_al_bms_54_1998/index.html){:target="_blank"}

[Discussion: Discretization of Nonlinear Dynamical Systems](https://www.researchgate.net/post/Discretization_of_nonlinear_dynamical_systems){:target="_blank"}
