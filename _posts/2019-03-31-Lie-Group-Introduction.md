---
layout: post
title: Introduction to Lie Group
excerpt: " "
categories: math
tags: lie math
comments: true
---

- A Lie group is a group that is also a differentiable manifold, with the property that the group operations are smooth.
- A Lie group is a continuous group, that is, one whose elements are described by several real parameters.

| Group | Description | Dim. | Matrix Representation |
| -- | -- | -- | -- |
| SO(2) | 2D Rotations | 1 | 2D Rotation matrix |
| SE(2) | 2D Rigid transformations | 3 | Linear transformation on homogeneous 3-vectors |
| SO(3) | 3D Rotations | 3 | 3D Rotation matrix |
| SE(3) | 3D Rigid transformations | 6 | Linear transformation on homogeneous 4-vectors |
| Sim(3) | 3D Similarity transformations (rigid motion + scale) | 7 | Linear transformation on homogeneous 4-vectors |

Classification of Kinematic Pairs According to Their DoF

| Group | Dim. | Notes |
| -- | -- | -- |
| Unit Matrix E | 0 | Rigid connection, no relative motion |
| SO(2) | 1 | Rovolute pair / Hinged joint 转动副 |
| T(1) | 1 | Prismatic joint / Slider 移动副 |
| SO$$_p$$(2) | 1 | Screw Pair 螺旋副 |
| T(2) | 2 | 2D Translational motion |
| SO(2) $$\times$$ T(1) | 2 | Cylindrical joint 圆柱副 |
| SE(2) or SO(2) $$\times$$ T(2) | 3 | Planer joint 平面副 |
| T(3) | 3 | 3D Translational motion |
| SO(3) | 3 | Spherical joint 球面副 |
| SO$$_p$$(2) $$\times$$ T(2) | 3 | 2D Translational motion +  Helical motion about the norm vector|
| SE(2) $$\times$$ T(1) or SO(2) $$\times$$ T(3) | 4 | 3D Translational Motion + Rotation about vectors parallel to a given vector|
| SE(3) | 6 | General rigid body motion: 3D Translational motion + 3D Ratational motion|


[Wikipedia: Lie Group](https://en.wikipedia.org/wiki/Lie_group){:target="_blank"}

[Lie Groups for 2D and 3D Transformations by Ethan Eade](http://ethaneade.com/lie.pdf){:target="_blank"}

[Lecture Notes in Lie Groups](https://arxiv.org/abs/1104.1106){:target="_blank"}

[Wikipedia: Kinematic Pair](https://en.wikipedia.org/wiki/Kinematic_pair){:target="_blank"}