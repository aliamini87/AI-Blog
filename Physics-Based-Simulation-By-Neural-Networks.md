---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-11-13
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 19
tags:
title:
visibility: public
---

# Physics Based Simulation By Neural Networks
![](https://developer-blogs.nvidia.com/wp-content/uploads/2021/11/Modulus-Stack-NVIDIA.jpg)
## Introduction
It was while reading [this](https://developer.nvidia.com/blog/accelerating-product-development-with-physics-informed-neural-networks-and-simnet) article that I felt that I still did not understand how these neural network-based simulators work and how deep learning would improve the numerical physics-based simulations. In the same article a [link](https://docs.nvidia.com/deeplearning/simnet/user-guide/SimNet_v21.06_User_Guide.pdf) was given to the [NVIDIA SimNet](https://developer.nvidia.com/modulus) guide. However, in the week that I wrote this article, its name was changed to NVIDIA modulus. Reading a few pages of this guide, I can say that I just understood what they mean by using neural networks in physics based simulations.

## The main points about these networks
- The use of neural networks in these problems is as a solver and is not intended to replace experimental formulas such as the Navier-Stokes equations or the mass conservation equations. If they were to do so, they would have to give these networks a lot of real-world experimental testing and training. But this is not the approach at all. These are only supposed to be more efficient solvers than current solvers for the same equations.
- The error function for teaching these networks is the comparison of the network output with the output of the differential equations of the physics. In other words, because there are physical equations (ordinary or partial differential equations), the training error is the error between estimation of the neural network and the differential equations output. As a result, ideally, the network should give output at the same point as the governing physical equations. So if the physics equations have simplifications, the network answer will also have these simplifications.
- The advantage of these methods over conventional numerical solvers lies in several points. First, in normal solvers, the problem must be resolved again by changing the configuration of the problem (for example, the length of a tube in a fluid dynamics example). But in neural network-based solvers, different configurations can also be given as input to the network and are solved all together. This can greatly speed up the process. Second, training neural networks can be done much faster and more efficiently because of their development on GPUs. As a result, the speed of solving problems will increase. Third, neural network solvers are not as dependent on mesh size for accuracy as other methods. Actually the third note is not clear for me and I only see this in [this](https://developer.nvidia.com/blog/accelerating-product-development-with-physics-informed-neural-networks-and-simnet) article.
- In this type of use of neural networks, there is also the issue of overfitting and etc. This means that if the network becomes too deep, it is possible that the answers will be very accurate in the points tested, but in other places the problem will be far from the correct answer.

## A Simple Example
The following is a simple example of using these networks to see how it is used in practice. The examples are from that SimNet user guide.
Consider the problem of the following differential equations.

<a href="https://www.codecogs.com/eqnedit.php?latex=\begin{cases}&space;\frac{\partial^2&space;u}{\partial&space;x^2}(x)&space;=&space;f(x)\\&space;u(0)=u(1)=0&space;\end{cases}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\begin{cases}&space;\frac{\partial^2&space;u}{\partial&space;x^2}(x)&space;=&space;f(x)\\&space;u(0)=u(1)=0&space;\end{cases}" title="\begin{cases} \frac{\partial^2 u}{\partial x^2}(x) = f(x)\\ u(0)=u(1)=0 \end{cases}" /></a>

The error formula considered here is a combination of the error of the differential equations themselves and the boundary condition error.

<a href="https://www.codecogs.com/eqnedit.php?latex=L_{total}&space;=&space;L_{residual}&plus;L_{BC}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?L_{total}&space;=&space;L_{residual}&plus;L_{BC}" title="L_{total} = L_{residual}+L_{BC}" /></a>

Which

<a href="https://www.codecogs.com/eqnedit.php?latex=L_{residual}&space;=&space;\frac{1}{N}\:&space;\sum_{i=0}^N&space;\left(\frac{\partial^2u_{net}}{\partial&space;x^2}\left(x_i)-f(x_i\right)\right)^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?L_{residual}&space;=&space;\frac{1}{N}\:&space;\sum_{i=0}^N&space;\left(\frac{\partial^2u_{net}}{\partial&space;x^2}\left(x_i)-f(x_i\right)\right)^2" title="L_{residual} = \frac{1}{N}\: \sum_{i=0}^N \left(\frac{\partial^2u_{net}}{\partial x^2}\left(x_i)-f(x_i\right)\right)^2" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=L_{BC}&space;=&space;u_{net}(0)^2&plus;u_{net}(1)^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?L_{BC}&space;=&space;u_{net}(0)^2&plus;u_{net}(1)^2" title="L_{BC} = u_{net}(0)^2+u_{net}(1)^2" /></a>

Note that <a href="https://www.codecogs.com/eqnedit.php?latex=x_i" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_i" title="x_i" /></a> in the above equations are arbitrary points in the range of 0 and 1. As I said before, this is not aد external training issue, and given the explicit equations, any point in the domain can be selected for training. 
This equation has an explicit answer for <a href="https://www.codecogs.com/eqnedit.php?latex=f&space;(x)&space;=1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?f&space;(x)&space;=1" title="f (x) =1" /></a>. So, the network is trained for this function and in the following figure, a comparison of the explicit answer and the network answer can be seen.

<img src="https://aliamini87.github.io/images/Pasted image 20211105124019.png" style="display: block; margin: auto;" />


## Another example with adding study of a paramater change to the problem
We can add study of a parameter change and use this solver. Consider the problem as follows: this time the length of the pipe is also considered as a parameter in the design.

<a href="https://www.codecogs.com/eqnedit.php?latex=\begin{cases}&space;\frac{\partial^2&space;u}{\partial&space;x^2}(x)&space;=&space;f(x)\\&space;u(0)=u(l)=0&space;\end{cases}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\begin{cases}&space;\frac{\partial^2&space;u}{\partial&space;x^2}(x)&space;=&space;f(x)\\&space;u(0)=u(l)=0&space;\end{cases}" title="\begin{cases} \frac{\partial^2 u}{\partial x^2}(x) = f(x)\\ u(0)=u(l)=0 \end{cases}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=1<l<2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?1<l<2" title="1<l<2" /></a>

In this case, it can be assumed that the function that the neural network must estimate is <a href="https://www.codecogs.com/eqnedit.php?latex=u&space;(x,&space;l)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?u&space;(x,&space;l)" title="u (x, l)" /></a>. 
The error function is also as follows.

<a href="https://www.codecogs.com/eqnedit.php?latex=L_{residual}&space;=&space;\int_{1}^2\int_0^l\left(\frac{\partial^2u_{net}}{\partial&space;x^2}\left(x,l)-f(x\right)\right)^2dxdl&space;\approx&space;\left(\int_{1}^2\int_0^ldxdl\right)\frac{1}{N}\:&space;\sum_{i=0}^N&space;\left(\frac{\partial^2u_{net}}{\partial&space;x^2}\left(x_i,l_i)-f(x_i\right)\right)^2&space;\\" target="_blank"><img src="https://latex.codecogs.com/gif.latex?L_{residual}&space;=&space;\int_{1}^2\int_0^l\left(\frac{\partial^2u_{net}}{\partial&space;x^2}\left(x,l)-f(x\right)\right)^2dxdl&space;\approx&space;\left(\int_{1}^2\int_0^ldxdl\right)\frac{1}{N}\:&space;\sum_{i=0}^N&space;\left(\frac{\partial^2u_{net}}{\partial&space;x^2}\left(x_i,l_i)-f(x_i\right)\right)^2&space;\\" title="L_{residual} = \int_{1}^2\int_0^l\left(\frac{\partial^2u_{net}}{\partial x^2}\left(x,l)-f(x\right)\right)^2dxdl \approx \left(\int_{1}^2\int_0^ldxdl\right)\frac{1}{N}\: \sum_{i=0}^N \left(\frac{\partial^2u_{net}}{\partial x^2}\left(x_i,l_i)-f(x_i\right)\right)^2 \\" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=L_{BC}&space;=&space;\int_1^2\left(u_{net}(0,l)^2&space;&plus;&space;u_{net}(l,l)^2\right)dl&space;\approx&space;\left(\int_1^2dl\right)\frac{1}{N}\sum_{i=0}^N&space;\left(u_{net}(0,l_i)^2&space;&plus;&space;u_{net}(l_i,l_i)^2\right)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?L_{BC}&space;=&space;\int_1^2\left(u_{net}(0,l)^2&space;&plus;&space;u_{net}(l,l)^2\right)dl&space;\approx&space;\left(\int_1^2dl\right)\frac{1}{N}\sum_{i=0}^N&space;\left(u_{net}(0,l_i)^2&space;&plus;&space;u_{net}(l_i,l_i)^2\right)" title="L_{BC} = \int_1^2\left(u_{net}(0,l)^2 + u_{net}(l,l)^2\right)dl \approx \left(\int_1^2dl\right)\frac{1}{N}\sum_{i=0}^N \left(u_{net}(0,l_i)^2 + u_{net}(l_i,l_i)^2\right)" /></a>

The results after training the network.

<img src="https://aliamini87.github.io/images/Pasted image 20211105131715.png" style="display: block; margin: auto;" />


## Other Notes
Implementation of these solvers has more complicated notes that you can find in the SimNet user guide.
For example, somewhere in this guide, it is mentioned that they have come to the conclusion that in solving fluid problems, in addition to the Navier-Stokes equations, they must also consider the continuity equations, and the more they add continuity equations in different places , the higher the accuracy is.

