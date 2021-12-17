---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-12-17
description:
icon:
image: 
label: null
layout: default
order: 21
tags:
title:
visibility: public

---

# Physics Aware Motion Capture Animation Using Vision by NVIDIA


![AI captures the movement using motion capture to animate the individual into a digital avatar, and provide a physics simulation to accurately imitate the real-life movement.](../static/avatar-nvidia-1.gif)



Researchers from NVIDIA, the University of Toronto, and the Vector Institute have proposed a new motion capture method foregoing the use of expensive motion-capture hardware. It uses only video input to improve past motion-capture animation models. They also improve their motion estimation, by considering physics constraints. 

YouTuber and graphics researcher Dr. Károly Zsolnai-Fehér breaks down the research on this innovative technology in his YouTube series: _Two Minute Papers_. This video highlights how the researchers can capture individuals using AI solely through video input to translate it into pose of the person and digital avatar. They can give the avatar a physics simulation to negate the conventional challenges of foot sliding and temporal inconsistencies or flickering. Check out the video below:

<iframe width="683" height="384" src="https://www.youtube.com/embed/MrKlPvWvQ2Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

_A video presenting the paper “Physics-based Human Motion Estimation and Synthesis from Videos in 2 minutes.”_

“In this paper, we introduced a new framework for training motion synthesis models from raw video pose estimations without making use of motion capture data,” Kevin Xie explains in the paper.

![](../static/nvidia_motion_capture_1.jpg)

“Our framework refines noisy pose estimates by enforcing physics constraints through contact invariant optimization, including computation of contact forces. We then train a time-series generative model on the refined poses, synthesizing both future motion and contact forces. Our results demonstrated significant performance boosts in both, pose estimation via our physics-based refinement, and motion synthesis results from video. We hope that our work will lead to more scalable human motion synthesis by leveraging large online video resources.”

![A graphic showing a person turned into an avatar that is trying to walk in a snow storm.](../static/avatar-nvidia-2.png)


This framework brings people one step closer to working and playing inside virtual worlds. It will help developers animate human motion far more affordably, with a much greater diversity of motions. From video games to the virtual world, this framework will undoubtedly impact how we visualize human motion synthesis.

Check out the [framework](https://nv-tlabs.github.io/physics-pose-estimation-project-page/) or read the paper [Physics-based Human Motion Estimation and Synthesis from Videos](https://arxiv.org/abs/2109.09913), by [Kevin Xie](https://arxiv.org/search/cs?query=Xie%2C+Kevin&searchtype=author&abstracts=show&order=-announced_date_first&size=50), [](https://arxiv.org/search/cs?searchtype=author&query=Wang%2C+T)[Tingwu Wang](https://arxiv.org/search/cs?query=Wang%2C+Tingwu&searchtype=author&abstracts=show&order=-announced_date_first&size=50), [](https://arxiv.org/search/cs?searchtype=author&query=Guo%2C+Y)[Umar Iqbal](https://arxiv.org/search/cs?query=Iqbal%2C+Umar&searchtype=author&abstracts=show&order=-announced_date_first&size=50), [Yunrong Guo](https://arxiv.org/search/cs?query=Guo%2C+Yunrong&searchtype=author&abstracts=show&order=-announced_date_first&size=50), [Sanja Fidler](https://arxiv.org/search/cs?query=Fidler%2C+Sanja&searchtype=author&abstracts=show&order=-announced_date_first&size=50), and [Florian Shkurti](https://arxiv.org/search/cs?query=Shkurti%2C+Florian&searchtype=author&abstracts=show&order=-announced_date_first&size=50).

Learn more about the [NVIDIA Toronto AI lab](https://nv-tlabs.github.io/).

---
source: [NVIDIA developer blog](https://developer.nvidia.com/blog/nvidia-ai-generating-motion-capture-animation-without-hardware-or-motion-data/)