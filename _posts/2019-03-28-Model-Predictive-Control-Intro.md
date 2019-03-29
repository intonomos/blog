---
layout: post
title: Model Predictive Control Introduction
excerpt: "Introduction to MPC"
categories: control
tags: control mpc intro
comments: true
---

**Advantages of MPC**:
- Multi-Input Multi-Output (MIMO) Systems
- Input-Output Interactions
- Constraints
- Preview Capability

MPC requires a powerful, fast process with large memory.

The goal of the controller is to calculate the input to the plant such that the plant output follows a desired reference.

The MPC's strategy to compute this input is by predicting the future.
- MPC uses a **model** of the plant to make predictions about future plant output behavior.
- MPC uses an **optimizer**, which ensures that the predicted future plant output tracks the desired reference.
- **Prediction horizon** is how far ahead MPC looks into future.
- MPC tries to find the best predicted path that is closet to the reference. It simulates multiple future scenarios in a systematic way.
  - By solving an **optimization** problem, MPC tries to minimize the error between reference and the predicted value. It also tries to minimize the change in the input front one step to next

$$
J = \sum_{i = 1}^{p} w_e e_{k+i}^2 + \sum_{i=1}^{p} w_{\Delta u} \Delta u_{k+i}^2
$$

  - While minimizing the cost function, MPC also makes sure the inputs and states stay within prescribed limits.


**MPC Operation Cycle**
- At the current time step, MPC solves an optimization problem over prediction horizon while satisfying constraints. The predicted path with the smallest cost function value gives the optimal solution, therefore determines the optimal input that will track the reference as close as possible.
- MPC applies the first step of the optimal sequence and discards the rest.
- At next time step, MPC gets a new measurement of the state. It might be different than what the MPC predicts before. This could be due to some unmeasured disturbances.
- The prediction horizon shifts forward by one time step and the controller repeats the same cycle of calculate.

**MPC Design Parameters**
- Sampling time $$T_s$$, which is the controller execution time
  - Too large: will not react to disturbance or set point change fast enough
  - Too small: excessive computation load
  - Rise time $$T_r$$: time it takes for the response to rise from 10% to 90% of steady state response.
  - Typically, $$\frac{T_r}{20} \leq T_s \leq \frac{T_r}{10}$$
- Prediction Horizon $$p$$
  - Need to be long enough to cover the significant dynamics of the systems
  - If it's too long, when unexpected things happen, a significant part of the planning need to be throw away, which is a wast of computation power.
  - Settling time $$T_t$$: time it takes for error $$\vert y(t) - y_\text{final}$$ to fall within 2% of $$y_\text{final}$$
  - Typically, $$p T_s \geq T_t$$. 20-30 points covering the open loop transient system response.
- Control Horizon
  - The number of control moves to time step $$m$$ are called control horizon. The rest of inputs are held constant.
    - Only the first couple of control moves have a significant effect on the predicted output behavior, while the remaining only have a minor effect.
    - Each control move in the control horizon is a free variable that needs to be computed by optimizer.
  - Increasing control horizon can get better predictions but at the cost of increasing complexity.
  - Typically, 10-20% of the prediction horizon and minimum 2-3 steps
- Constraints
  - Hard constraints: cannot be violated
  - Soft constraints: can be violated
  - Having hard constraints on both inputs and outputs is not a good idea because these constraints may conflict with each other, leading to an infeasible solution for optimization problem.
  - To keep the violation of soft constraint small, it is being minimized by the optimization problem.
- Weights
  - Const function weights


**Speeding Up MPC**
- Model order reduction
- Shorter prediction horizon
- Shorter control horizon
- Reduced number of constraints
- Lower precision operations and data representations

[Understanding Model Predictive Control by Mathworks](https://www.mathworks.com/videos/series/understanding-model-predictive-control.html){:target="_blank"}