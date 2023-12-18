---
name: Modeling of Rod-based locking in tendon-driven Continuum Robots
tools: [Modeling]
image: https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7083369/10102643/10093050/rao1-3264869-small.gif
description: A model proposed for a locking based actuation for TDCR
---

# Modeling of Rod-based locking in TDCRs

#### Quick context setting :
A single segment TDCR is limited because :
<p>1. It can bend only in limited shapes : A single segment TDCR can usually only bend in a C shape as shown in this gif :<img align="right" src="/images/c.gif">. To achieve more complex shapes, a common solution is to stack multiple segments on top of each other as shown below :
<img align="right" src="/images/multiple_segment.gif">
However this can lead to quite complex actuation units and control. 
Additionally this segment has limited stiffness.
</p> 

<p>2. It has limited stiffness : Additionally this segment has limited stiffness. While TDCR compliance is its strong suit, multiple approahces like layer jamming, stiffening sheaths have been devised to allow it to switch between stiff and compliant states.
</p> 

<p class="text-center">
<iframe width="560" height="315" src="https://www.youtube.com/watch?v=y9G-J1wP5O4" title="IROS 2022" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</p>


For more details, there's always some good old-fashioned paper reading : 
{% include elements/button.html link="https://ieeexplore.ieee.org/abstract/document/10093050" text="Link to the RAL paper" %} 