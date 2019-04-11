---
layout: post
title: ChauﬀeurNet
excerpt: "Learning to Drive by Imitating the Best and Synthesizing the Worst"
categories: learning
tags: learning behavior
comments: true
---

The goal is to train a policy for autonomous driving via imitation learning that is robust enough to drive a real vehicle.
- Standard behavior cloning is insufficient for handling complex driving scenarios
- Proposed approach:
  - Synthesize data in the form of perturbations to the expert's driving, which creates interesting situations such as collision and/or going off the road
  - Augment the imitation loss with additional losses that penalize undesirable events and encourage progress

ChauﬀeurNet is a deep recurrent neural network (RNN) that is trained to emit a driving trajectory by observing a mid-level representation of the scene.

Inputs:
- Roadmap
- Traffic lights
- Speed-limit
- Route
- Current agent box
- Dynamic boxes
- Past agent poses

Output:
- Future agent poses

[Bansal, Mayank, Alex Krizhevsky, and Abhijit Ogale. "Chauffeurnet: Learning to drive by imitating the best and synthesizing the worst." arXiv preprint arXiv:1812.03079 (2018).](https://arxiv.org/abs/1812.03079){:target="_blank"}

[Learning to Drive: Beyond Pure Imitation](https://medium.com/waymo/learning-to-drive-beyond-pure-imitation-465499f8bcb2){:target="_blank"}