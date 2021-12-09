---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-10-08
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 5
tags:
title:
visibility: public



---




#  Autonomous Racing Drones Dodge Through Forests at 40 kph

Training in simulation gives these drones impressive flying skills 

![](https://spectrum.ieee.org/media-library/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpbWFnZSI6Imh0dHBzOi8vYXNzZXRzLnJibC5tcy8yNzYyMDcwNi9vcmlnaW4uZ2lmIiwiZXhwaXJlc19hdCI6MTY3NzUzOTQxM30.ORBEB8H20xrhR9jajGDn0n0VpAF_Ckft9QwLJI83YGA/image.gif?width=1280&height=720)


It seems inevitable that sooner or later, the performance of autonomous drones will [surpass the performance of even the best human pilots](https://spectrum.ieee.org/ai-powered-drone-extreme-acrobatics). Usually things in robotics that seem inevitable happen later as opposed to sooner, but drone technology seems to be the exception to this. We've seen an astonishing amount of progress over the past few years, even to the extent of [sophisticated autonomy](https://spectrum.ieee.org/skydio-2-review-this-is-the-drone-you-want-to-fly) making it into the hands of consumers at an affordable price.

The cutting edge of drone research right now is putting drones with relatively simple onboard sensing and computing in situations that require fast and highly aggressive maneuvers. In a paper [published yesterday in _Science Robotics_](http://rpg.ifi.uzh.ch/AgileAutonomy.html), roboticists from [Davide Scaramuzza's Robotics and Perception Group at the University of Zurich](http://rpg.ifi.uzh.ch/) along with partners at Intel demonstrate a small, self-contained, fully autonomous drone that can aggressively fly through complex environments at speeds of up to 40kph.

___

Video on Youtube:

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/m89bNn6RFoQ/0.jpg)](https://www.youtube.com/watch?v=m89bNn6RFoQ)


<iframe width="880" height="495" src="https://www.youtube.com/embed/m89bNn6RFoQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


The trick here, to the extent that there's a trick, is that the drone performs a direct mapping of sensor input (from an Intel RealSense 435 stereo depth camera) to collision-free trajectories. Conventional obstacle avoidance involves first collecting sensor data; making a map based on that sensor data; and finally making a plan based on that map. This approach works perfectly fine as long as you're not concerned with getting all of that done quickly, but for a drone with limited onboard resources moving at high speed, it just takes too long. UZH's approach is instead to go straight from sensor input to trajectory output, which is much faster and allows the speed of the drone to increase substantially.

The convolutional network that performs this sensor-to-trajectory mapping was trained entirely in simulation, which is cheaper and easier but (I would have to guess) less fun than letting actual drones hammer themselves against obstacles over and over until they figure things out. A simulated "expert" drone pilot that has access to a 3D point cloud, perfect state estimation, and computation that's not constrained by real-time requirements trains its own end-to-end policy, which is of course not achievable in real life. But then, the simulated system that will be operating under real-life constraints just learns in simulation to match the expert as closely as possible, which is how you get that expert-level performance in a way that can be taken out of simulation and transferred to a real drone without any adaptation or fine-tuning.

The other big part of this is making that sim-to-real transition, which can be problematic because simulation doesn't always do a great job of simulating everything that happens in the world that can screw with a robot. But this method turns out to be very robust against motion blur, sensor noise, and other perception artifacts. The drone has successfully navigated through real world environments including snowy terrains, derailed trains, ruins, thick vegetation, and collapsed buildings.

>***"While humans require years to train, the AI, leveraging high-performance simulators, can reach comparable navigation abilities much faster, basically overnight." -Antonio Loquercio, UZH***

This is not to say that the performance here is flawless—the system still has trouble with very low illumination conditions (because the cameras simply can't see), as well as similar vision challenges like dust, fog, glare, and transparent or reflective surfaces. The training also didn't include dynamic obstacles, although the researchers tell us that moving things shouldn't be a problem even now as long as their speed relative to the drone is negligible. Many of these problems could potentially be mitigated by using [event cameras](https://spectrum.ieee.org/event-camera-helps-drone-dodge-thrown-objects) rather than traditional cameras, since faster sensors, especially ones tuned to detect motion, would be ideal for high speed drones.

![](https://spectrum.ieee.org/media-library/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpbWFnZSI6Imh0dHBzOi8vYXNzZXRzLnJibC5tcy8yNzYyMDc1NC9vcmlnaW4ucG5nIiwiZXhwaXJlc19hdCI6MTYzMzkwNTc4OX0.ziAUFFcbW2WPbFNbwiYkErKgXobBI6QlrCfLUpKU2Ps/image.png?width=837&quality=80)

The researchers tell us that their system does not (yet) surpass the performance of expert humans in these challenging environments:

> Analyzing their performance indicates that humans have a very rich and detailed understanding of their surroundings and are capable of planning and executing plans that span far in the future (our approach plans only one second into the future). Both are capabilities that today's autonomous systems still lack. We see our work as a stepping stone towards faster autonomous flight that is enabled by directly predicting collision-free trajectories from high-dimensional (noisy) sensory input.

This is one of the things that is likely coming next, though—giving the drone the ability to learn and improve from real-world experience. Coupled with more capable sensors and always increasing computer power, pushing that flight envelope past 40 kph in complex environments seems like it's not just possible, but inevitable.

Source: [IEEE Spectrum](https://spectrum.ieee.org/racing-drone)
