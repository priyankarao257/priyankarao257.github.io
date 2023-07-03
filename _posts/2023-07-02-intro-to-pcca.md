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

<span style="color:grey">
- _Segment_ : Portion of the backbone (including disks, tendons and what have you nots) starting from the base till point of tendon termination. 
- _Subsegment_ : Portion of the backbone between two disks. Many subgsegments = 1 segment
- _TDCR_ : tendon-driven conitnuum robot
- _Lumped parameterization_ : Lumped parameterization discretizes the curve using geometrical assumption such that the curve can be represented by a finite number of parameters. 
- CC : Constant curvature arcs
- </span>.



As most students trying to model these robots, I was first introduced to the Constant curvature assumption. The premise is very simple - the entire segment is modeled as a constant cuvature arc. There is tonne of material on understanding this better - an extensive survey on different formalization routines [1], blog posts from the lab on introducing the forward kinematics ([link 1](https://www.cs.toronto.edu/~jbk/opencontinuumrobotics/101/2022/12/02/cc-kinematics.html) and [link 2](https://www.cs.toronto.edu/~jbk/opencontinuumrobotics/101/2022/12/09/tdcr-cc-model.html)). The underlying physical meaning is simple. From the Euler Bernoulli theorem we know that applied moment is directly proportional to the curvature. So constant curvature -> constant moment applied -> the TDCR effectively has a constant moment acting on it. 

</mark>But what if we want to model more than just a constant moment == like forces from contact interactions, or external weight of cameras and tools ?</mark>

## Breaking the curve
To model these intermediate forces, the segment is now _broken_ into a series of constant curvature arcs, each representing a subsegment. So now, the backbone no longer has a constant curvature along its length, and can accomodate different forces that make it deviate from its C-shape. We call this the piecewise constant curvature assumption! The beauty of this representation is you can represent the curve discretely, and use the curvature components along the local _x_, _y_, and _z_ axes to represent not just bending, but also twist in the robot. {% include elements/button.html link="" text="Rabbit hole leading to modeling twists using CC arcs [to follow soon]" %}, 


[insert picture here]

## Equivalence of the 4-bar representation and CC arcs
There are of course many ways to represent just the piecewise arcs as well [1]. One of these approaches that caught my eye was the 4-bar representation proposed by
If we look at the planar case, th



While studying different backbone representations for our survey paper [cue : shameless plug], I came across this very interesting representation where the portion of the robot between two disks (hereon referred to as a subsegment) is modeled as a _series of four bar mechanisms stacked over each other_. A rough sketch of one such subsegment being approximated by a 4-bar linkage (marked in red) is shown below.

![](/images/4bar.png)*Sketch of 4-bar linkage imposed on a TDCR*



## To read, read, and read
[1] R. J. Webster and B. A. Jones, “Design and kinematic modeling of constant curvature continuum robots: A review,” Int. J. Rob. Res., vol. 29, no. 13, pp. 1661–1683, Nov. 2010, doi: 10.1177/0278364910368147.

[2] K. Ashwin, S. K. Mahapatra, and A. Ghosal, "Profile and contact force estimation of cable-driven
continuum robots in presence of obstacles," Mechanism and Machine Theory, vol. 164, p. 104404, 2021.