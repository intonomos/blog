---
layout: post
title: Least Squares Auto-Tuning
excerpt: "Parametrizing the least squares problem and automatically adjusting these parameters using an optimization algorithm."
categories: optimization
tags: optimization
comments: true
---

The **matrix least squares problem** that depends on a hyper-parameter vector $$\omega \in \Omega \subseteq \mathbb{R}^p$$ has the form

$$
\text{minimize } \|A(\omega) \theta - B(\omega) \|_F^2
$$

where the variable $$\theta \in \mathbb{R}^{n \times m}$$, the least squares optimization variable or parameter matrix, and $$A: \omega \rightarrow \mathbb{R}^{k \times n}$$ and $$B: \omega \rightarrow \mathbb{R}^{k \times m}$$ map the hyper-parameter vector to the least squares problem data. $$\| \cdot \|_F$$ denotes the Frobenius norm, i.e., the squareroot of the sum of squares of the entries of a matrix. It is assumed that $$ k \geq n$$.

The least squares solution is unique, given by

$$
\theta^{\text{ls}}(\omega) = A(\omega)^\dagger B(\omega) = \left(A(\omega)^\top A(\omega)\right)^{-1} A(\omega)^\top B(\omega)
$$

where $$A(\omega)^\dagger$$ denotes the Moore-Penrose pseudo-inverse.

In a **least squares tuning problem**, the goal is to choose the hyper-parameters to achieve some goal. The problem is formalized as

$$
\text{minimize } F(\omega) = \psi \left(\theta^{\text{ls}}(\omega)\right) + r(\omega)
$$

with variable $$\omega \in \Omega$$ and objective $$F: \Omega \rightarrow \mathbb{R} \cup +\infty$$.

where $$\psi: \mathbb{R}^{n \times m} \rightarrow \mathbb{R}$$ is the true objective function and $$r: \Omega \rightarrow \mathbb{R} \cup +\infty$$ is the hyper-parameter regularization function.

[Least Squares Auto-Tuning by Shane Barratt, Stephen Boyd](https://arxiv.org/abs/1904.05460){:target="_blank"}