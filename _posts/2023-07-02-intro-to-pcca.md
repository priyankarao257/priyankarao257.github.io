---
title: Breaking the curve with PCCA (Piecewise Constant Curvature Assumption)
tags: [Modeling, Blog]
style: fill
color: light
image : /images/4bar.png
description:  Introducing the whimsical piecewise arcs for modeling our robots
---

# Breaking the curve with PCCA (Piecewise Constant Curvature Assumption)

#### Quick context setting :
This post can be thought of as a follow-up rabbit hole to a previous post written on the OpenCR blog, found [here](https://www.cs.toronto.edu/~jbk/opencontinuumrobotics/101/2023/01/06/howto-tdcr-modeling.html).  We will basically look at using a lumped parameterization using constant curvature arcs to model the backbone. 
- _Segment_ : Portion of the backbone (including disks, tendons and what have you nots) starting from the base till point of tendon termination. 
- _Subsegment_ : Portion of the backbone between two disks. Many subgsegments = 1 segment
- _TDCR_ : tendon-driven conitnuum robot
- _Lumped parameterization_ : Lumped parameterization discretizes the curve using geometrical assumption such that the curve can be represented by a finite number of parameters. 



As most students trying to model these robots, I was first introduced to the Constant curvature assumption. The premise is very simple - the entire segment is modeled as a constant cuvature arc. There is tonne of material on understanding this better - an extensive survey on different formalization routines [1], blog posts from the lab on introducing the forward kinematics ([link 1](https://www.cs.toronto.edu/~jbk/opencontinuumrobotics/101/2022/12/02/cc-kinematics.html) and [link 2](https://www.cs.toronto.edu/~jbk/opencontinuumrobotics/101/2022/12/09/tdcr-cc-model.html)). The underlying physical meaning is simple. From the Euler Bernoulli theorem we know that applied moment is directly proportional to the curvature. So constant curvature -> constant moment applied -> the TDCR effectively has a constant moment acting on it. 

==But what if we want to model more than just a constant moment == like forces from contact interactions, or external loads of cameras and tools ?

## Breaking the curve


While studying different backbone representations for our survey paper [cue : shameless plug], I came across this very interesting representation where the portion of the robot between two disks (hereon referred to as a subsegment) is modeled as a _series of four bar mechanisms stacked over each other_. A rough sketch of one such subsegment being approximated by a 4-bar linkage (marked in red) is shown below.

![](/images/4bar.png)*Sketch of 4-bar linkage imposed on a TDCR*

## Basic principle behind the forward kinematic modeling

The basic principle behind forward kinematic modeling is that, during deformation caused by loads or environment, the robot's static equilibrium shape is the one that minimizes the strain energy. According to the paper, when the robot is discretized into subsegments of equal length, the equilibrium configuration is one that minimizes the angle Ⲫ of each subsegment.

For a given tendon length, the above principle can be formulated as an optimization problem that minimizes these angles, such that the resulting tendon length is equal to the required length (see [1] for more details).

As we already know, during deformation by loads / environment, the robot's static equilibrium shape is one which minimizes the strain energy. The paper states that for this representation, when discretized into subsegments of equal length, this translates to a configuration that minimizes the angle Ⲫ of each subsegment.

For a given tendon length, the above can be written as an optimization problem that minimizes these angles, such that the resulting tendon length is equal to the required length.

## To read, read, and read
[1] R. J. Webster and B. A. Jones, “Design and kinematic modeling of constant curvature continuum robots: A review,” Int. J. Rob. Res., vol. 29, no. 13, pp. 1661–1683, Nov. 2010, doi: 10.1177/0278364910368147.
