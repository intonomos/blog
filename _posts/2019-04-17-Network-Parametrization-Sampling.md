---
layout: post
title: Network Parametrization Sampling for GPU-Accelerated Motion Planning
excerpt: "Sample online in the parameter space of a neural network parameterizing the controller."
categories: planning
tags: planning sampling
comments: true
---

Neural networks are used as controller parametrization since they can handle nonlinear non-convex systems and their complexity does not scale with prediction horizon length.

Network parametrizations are sampled at each sampling time and then held constant throughout the prediction horizon.

Controls still vary over the prediction horizon due to varying feature vectors fed to the network.

This paper is motivated by the desire for a simple control scheme that can
- be based on arbitrarily complex nonlinear non-convex vehicle models
- work for general all-purpose trajectory planning (i.e., is equally applicable to scenarios from parking to road centerline tracking)
- can generate collision-free trajectories accounting for the full vehicle dimensions
- can exploit continuing advancement in computation hardware, in particular, for parallelization.

[Online Sampling in the Parameter Space of a Neural Network for GPU-accelerated Motion Planning of Autonomous Vehicles by Mogens Graf Plessen](https://arxiv.org/abs/1904.06680){:target="_blank"}