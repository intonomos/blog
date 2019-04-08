---
layout: post
title: Model Learning for Robot Control
excerpt: "A survey of model learning for robot control."
categories: overview modeling
tags: overview modeling
comments: true
---

A model describes how the system is expected to react
- Implicit Models: coded into the rules of the controller
- Explicit Models

Model Types:
- Forward: given the current state and an action, predicts the next state
- Inverse: given the current state and the desired state, predicts the action
- Mixed: paired a forward and inverse model together
- Multi-step prediction: predicts multiple future states/actions

Learning Architectures
- Direct Modelling
- Indirect Modelling
- Distal Teacher Learning

[Presentation on the paper "Model learning for robot control: a survey"](http://cse.unl.edu/~lksoh/Classes/CSCE990AMAS_Fall16/Seminars/Seminar09_RobotLearning.pdf){:target="_blank"}

[Nguyen-Tuong, Duy, and Jan Peters. "Model learning for robot control: a survey." Cognitive processing 12, no. 4 (2011): 319-340.](https://link.springer.com/article/10.1007/s10339-011-0404-1){:target="_blank"}