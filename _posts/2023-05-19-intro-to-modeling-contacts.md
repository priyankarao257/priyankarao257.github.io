---
title: Modeling TDCR contacts - the Kinematic way
tags: [Modeling, Blog]
style: fill
color: dark
image : 
description:  Introducing a kinematic model proposed by Ashwin et al., 2021, rewritten the PCCA way
---

# Modeling TDCR contacts - the Kinematic way

While studying different backbone representations for our survey paper [cue : shameless plug], I came across this very interesting representation where the portion of the robot between two disks (hereon referred to as a subsegment) is modeled as a _series of four bar mechanisms stacked over each other_. A rough sketch of one such subsegment being approximated by a 4-bar linkage (marked in red) is shown below.

![](/images/4bar.png)*Sketch of 4-bar linkage imposed on a TDCR*

## Basic principle behind the forward kinematic modeling

The basic principle behind forward kinematic modeling is that, during deformation caused by loads or environment, the robot's static equilibrium shape is the one that minimizes the strain energy. According to the paper, when the robot is discretized into subsegments of equal length, the equilibrium configuration is one that minimizes the angle Ⲫ of each subsegment.

For a given tendon length, the above principle can be formulated as an optimization problem that minimizes these angles, such that the resulting tendon length is equal to the required length (see [1] for more details).

As we already know, during deformation by loads / environment, the robot's static equilibrium shape is one which minimizes the strain energy. The paper states that for this representation, when discretized into subsegments of equal length, this translates to a configuration that minimizes the angle Ⲫ of each subsegment.

For a given tendon length, the above can be written as an optimization problem that minimizes these angles, such that the resulting tendon length is equal to the required length.

[1] K. Ashwin, S. K. Mahapatra, and A. Ghosal, "Profile and contact force estimation of cable-driven
continuum robots in presence of obstacles," Mechanism and Machine Theory, vol. 164, p. 104404, 2021.