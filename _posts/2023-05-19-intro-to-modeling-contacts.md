---
title: Modeling TDCR contacts - the Kinematic way
tags: [Modeling, PCCA, Contact modeling, CC]
style: fill
color: light
image : /images/4bar.png
description:  Introducing a kinematic model proposed by Ashwin et al., 2021, rewritten the PCCA way
---

# Modeling TDCR contacts - the Kinematic way

While studying different backbone representations for our survey paper [cue : shameless plug], I came across this very interesting representation where the portion of the robot between two disks (hereon referred to as a subsegment) is modeled as a _series of four bar mechanisms stacked over each other_. A rough sketch of one such subsegment being approximated by a 4-bar linkage (marked in red) is shown below.

![](/images/4bar.png)*Sketch of 4-bar linkage imposed on a TDCR*


Anyway I digress. The point of this blogpost is to rewrite the proposed model using the PCCA model, introduced here - {% include elements/button.html link="https://priyankarao257.github.io/projects/2-eas" text="Rabbit hole to backbone representation using piecewise constant curvature arcs" %}, to instead model contacts. 

## Basic principle behind the forward kinematic modeling

The basic principle behind forward kinematic modeling is that, during deformation caused by loads or environment, the robot's static equilibrium shape is the one that minimizes the strain energy. According to the paper, when the robot is discretized into subsegments of equal length, the equilibrium configuration is one that minimizes the angle θ of each subsegment (marked as Ⲫ in the diagram) of each subsegment. For the PCCA representation, this translates to simply minimizing the angle subtended by each arc.

For a given tendon length, the above principle can be formulated as an optimization problem that minimizes these angles, with the equality constraint the resulting tendon length is equal to the required length (see [1] for more details).

## Optimization problem

![](https://latex.codecogs.com/svg.image?%5Cmin%7B%5Csum%5En_j%5Cmathbf%7B%5Ctheta_j%7D%7D%5E2%20)
[1] K. Ashwin, S. K. Mahapatra, and A. Ghosal, "Profile and contact force estimation of cable-driven
continuum robots in presence of obstacles," Mechanism and Machine Theory, vol. 164, p. 104404, 2021.