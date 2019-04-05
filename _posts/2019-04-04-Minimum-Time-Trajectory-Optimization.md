---
layout: post
title: Minimum Time Trajectory Optimization
excerpt: "Discretization of minimum time trajectory optimization problem."
categories: optimization
tags: time optimization discretization
comments: true
---

Original Formulation:

$$
\begin{aligned}
\underset{x, u, t_f}{\text{minimize }}
& t_f\\
\text{subject to }
& \dot{x}(t) = f(x(t), u(t)) \\
& g(x(t), u(t)) \leq 0 \\
& x(0) = x^0 \\
& t_f > 0 \\
& t \in [0, t_f]
\end{aligned}
$$

Approach 1:

$$
\begin{aligned}
\underset{u_0, \cdots, u_{N-1}, \Delta t}{\text{minimize }}
& N \Delta t\\
\text{subject to }
& x_i  - x_{i-1} = f(x_{i-1}, u_{i-1}) \Delta t \\
& g(x_i, u_i) \leq 0 \\
& x_0 = x^0 \\
& \Delta t > 0 \\
& i = 1, \cdots, N
\end{aligned}
$$

Approach 2:

$$
\begin{aligned}
\underset{u(t_0), \cdots, u(t_{N-1}), t_f}{\text{minimize }}
& t_f\\
\text{subject to }
& \sum_{j=1}^{N} x(t_j) D_{ij} = f(x(t_i), u(t_i))\\
& g(x(t_i), u(t_i)) \leq 0 \\
& x(0) = x^0 \\
& t_f > 0 \\
& t_i = \frac{t_f}{2} \tau_i +\frac{t_f}{2} \\
& i = 1, \cdots, N
\end{aligned}
$$

where $$\tau_i \in [-1, 1]$$ are collocation points, for example, Legendre-Gauss points are roots of Legendre polynomial of order $$N$$.

The state is approximated using a basis of $$N+1$$ Lagrange interpolating polynomials $$L_i(t), i = 0, \cdots, N$$

$$
\begin{aligned}
x(t) &= \sum_{j=1}^{N} x(t_j) L_j(t) \\
L_j(t) &= \prod_{k = 1, k \neq j}^{N} \frac{t - t_k}{t_j - t_k} \\
\dot{x}(t) &= \sum_{j=1}^{N} x(t_j) \dot{L}_j(t) \\
\\
\dot{L}_j(t_k) &= D_{kj} = \sum_{m=1}^{N} \frac{\prod_{n = 1, n \neq j, m}^{N} (t_k - t_n)}{\prod_{n = 1, n \neq j}^{N} (t_j - t_n)}
\end{aligned}
$$

Thus, the following is the differential form.

$$
\dot{x}(t_i) = \sum_{j=1}^{N} x(t_j) D_{ij} = f(x(t_i), u(t_i))
$$

Alternatively, there is integral form.

$$
x(t_i)  - x(0) =  \frac{t_f}{2} \sum_{j=1}^{N} A_{ij}f(x(t_{j}), u(t_{j}))
$$

and $$A = D^{-1}$$

Integral form of differential dynamics:

$$
\begin{aligned}
\dot{x}(t) &= f(x(t), u(t)) \\
\int_{0}^{t} \dot{x}(\tau) \text{d} \tau &= \int_{0}^{t} f(x(\tau), u(\tau)) \text{d} \tau \\
x(t) & = x(0) + \frac{t_f}{2} \int_{-1}^{\tau} f(x(\hat{\tau}), u(\hat{\tau})) \text{d} \hat{\tau} \\
\end{aligned}
$$

[Wikipedia: Gaussian Quadrature](https://en.wikipedia.org/wiki/Gaussian_quadrature){:target="_blank"}
