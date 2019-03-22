---
layout: post
title: Policy Iteration vs. Value Iteration
excerpt: "Differences between policy iteration and value iteration reinforcement learning"
categories: reinforcement
tags: reinforcement review
comments: no
---

Policy Iteration:
- Policy evaluation + Policy improvement
- The two are repeated iteratively until policy converges

Value Iteration:
- Finding optimal value function + One policy extraction

Relationships:
- Finding optimal value function can be seen as a combination of policy improvement and truncated policy evaluation
- Policy improvement and policy extraction are identical except the former involves a stability check

[What is the difference between value iteration and policy iteration?](https://stackoverflow.com/questions/37370015/what-is-the-difference-between-value-iteration-and-policy-iteration)


[What is the difference between value iteration and policy iteration methods in reinforcement learning?](https://www.researchgate.net/post/what_is_the_difference_between_value_iteration_and_policy_iteration_methods_in_reinforcement_learning)

[Policy Networks vs Value Networks in Reinforcement Learning](https://towardsdatascience.com/policy-networks-vs-value-networks-in-reinforcement-learning-da2776056ad2)

[Tutorial of Reinforcement: A Special Focus on Q-Learning](http://www.cs.toronto.edu/~tingwuwang/RL_tutorial.pdf)