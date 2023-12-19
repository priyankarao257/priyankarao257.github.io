---
name: Modeling of Rod-based locking in tendon-driven Continuum Robots
tools: [Modeling]
image: https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7083369/10102643/10093050/rao1-3264869-small.gif
description: A look into locking mechanisms and their modeling
---

# Modeling of Rod-based locking in TDCRs

#### Quick context setting :
<img align="right" src="/images/c.gif">
A single segment TDCR is limited because :
1. It can bend only in **limited shapes** : A single segment TDCR can usually only bend in a C shape as shown on the right. To achieve more complex shapes, a common solution is to stack multiple segments on top of each other as shown below

<img src="/images/multiple_segments.gif" width="200" style="transform: rotate(90deg)" />


However this can lead to quite complex actuation units and control. 
Additionally this segment has limited stiffness.


2. It has **limited stiffness** : The intrinsic compliance of TDCRs is a double-edged sword. While it allows for remarkable flexibility, it often falls short in tasks requiring rigidity. To tackle this, innovative solutions like layer jamming and stiffening sheaths have been explored, enabling these robots to alternate between stiff and compliant states.


##### Solution :
The exciting development in this field is the integration of locking mechanisms into TDCR design. My colleague, Chloe Pogue, presents a breakthrough in our recent work - a wirelessly actuated, magnetically controlled locking mechanism. Check out her presentation in this video:

<p class="text-center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/y9G-J1wP5O4?si=bcwUbfycdAw01XrF" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</p>

This innovative mechanism can be miniaturized and attached to the robot, enabling selective locking of specific robot segments. By restricting relative motion between parts of the robot, we effectively enhance its stiffness. Interestingly, when unlocked using an external magnetic field, the robot reverts to functioning like a conventional single segment TDCR.

### Modeling the above phenomenon

While the previous work focused on the mechanism design, my project was primarily concerned with modeling the behaviour of the TDCR on locking. The locking is achieved by clamping the passive backbones at both ends of a segment. This action introduces a pivotal length constraint in each of these rods. Our model posits that this length constraint generates a resistive moment within the locked portion, counteracting externally applied forces. With this moment, the robot can be modeled as a regular TDCR and its constitutive equations solved for. 

For those keen on diving into the technicalities and the comprehensive model, our findings and the detailed mathematical framework are thoroughly documented in our recent publication : {% include elements/button.html link="https://ieeexplore.ieee.org/abstract/document/10093050" text="Link to the RAL paper" %} 

### Innovating TDCR Design with Triple Locking Mechanisms: A Study of Flexibility and Stiffness

An interesting proposition would be to place three of these locking mechanism on a segment design. Lets say these three mechanisms are placed at, 1) the bottom (disk 0), 2) the end disk (disk n), and 3) somewhere in the middle (disk d). All these three mechanims can be independently actuated. Doing so offers an interesting control over the robots stiffness. 

By selectively engaging these locks, we can lock either the distal portion (between disks d and n) or the proximal portion (between disks 0 and d) of the segment. What's particularly interesting is that these TDCRs can achieve the same shape with different sequences of tendon tensions, yet exhibit different levels of stiffness depending on which portion is locked. With three locking mechanisms alternatively actuated, the robot could essentially achieve three values of stiffness.

**Proximal locking:**
<img align="text-center" src="/images/first_anim.gif">

**Distal locking:**
<img align="text-center" src="/images/second_anim.gif">


The paper also studies how the stiffness varies when the value of d ranges from 0 to n, seeking to inform the robot behaviour during locking. 


<sub>The TDCR animations were created by Bhushanraaj Kutte.</sub>