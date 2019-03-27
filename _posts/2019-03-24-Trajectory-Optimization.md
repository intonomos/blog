---
layout: post
title: Trajectory Optimization Formulation
excerpt: "Trajectory optimization problem assumptions and formulation."
categories: optimization
tags: overview optimization
comments: no
---

**Assumptions**
- Trajectory optimization problem is
    - continuous time
    - single phase

The violations of above assumptions are easy to deal with.

- Dynamics, objective, and constraints are all:
    - smooth
    - consistent
    - potentially non-linear

The violations of above assumptions require special techniques to handle, and should be avoided where possible.

**Formulation**

$$
\min \limits_{t_0, t_f, x(t), u(t)} J_{\text{boundary}} + J_{\text{integral}}
$$

Boundary objective function:

$$
J_{\text{boundary}} = J\left(t_0, t_f, x(t_0), x(t_f)\right)
$$

Integral objective function:

$$
J_{\text{integral}} = \int_{t_0}^{t_f} w\left(\tau, x(\tau), u(\tau) \right) \text{d}\tau
$$

Subject to:

Boundary constraints:

$$
g\left(t_0, t_f, x(t_0), x(t_f)\right) \leq 0
$$


Bound on initial and final time:

$$
t_{\min} \leq t_0 \leq t_f \leq t_{\max}
$$

Bound on initial state:

$$
x_{0, \min} \leq x(t_0) \leq x_{0, \max}
$$

Bound on final state:

$$
x_{f, \min} \leq x(t_f) \leq x_{f, \max}
$$

Continuous dynamics:

$$
\dot{x}(t) = f\left(t, x(t), u(t)\right)
$$

Path constraints:

$$
h\left(t, x(t), u(t)\right) \leq 0
$$

Continuous bounds on state:

$$
x_{\min} \leq x(t) \leq x_{\max}
$$

Continuous bounds on control:

$$
u_{\min} \leq u(t) \leq u_{\max}
$$

**Transcription**

Transcription from Trajectory Optimization Problem to Constrained Parameter Optimization is necessary.

Trajectory Optimization Problem:
- Decision variables are vector functions
- Infinite dimensional
- Differential equations

Constrained Parameter Optimization:
- Decision variables are real numbers
- Finite dimensional
- Algebraic Equations

**Nonlinear Programming (NLP)**

$$
\begin{aligned}
\underset{z}{\text{minimize }}
& f(z) \\
\text{subject to }
& g(z) \leq 0 \\
& h(z) = 0 \\
& z_{\min} \leq z \leq z_{\max}
\end{aligned}
$$

[Trajectory Optimization Tutorial by Matthew Kelly](http://www.matthewpeterkelly.com/tutorials/trajectoryOptimization/)