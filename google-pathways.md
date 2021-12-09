---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-10-31
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 17
tags:
title:
visibility: public
---

# Introducing Pathways: A next-generation AI architecture

Too often, machine learning systems overspecialize at individual tasks, when they could excel at many. That’s why we’re building Pathways—a new AI architecture that will handle many tasks at once, learn new tasks quickly and reflect a better understanding of the world.

Jeff Dean

Google Senior Fellow and SVP, Google Research

![Article's hero media](https://storage.googleapis.com/gweb-uniblog-publish-prod/original_images/pathways_3.gif)


When I reflect on the past two decades of computer science research, few things inspire me more than the remarkable progress we’ve seen in the field of artificial intelligence.

In 2001, some colleagues sitting just a few feet away from me at Google realized they could use an obscure technique called machine learning to help correct misspelled Search queries. (I remember I was amazed to see it work on everything from “ayambic pitnamiter” to “unnblevaiabel”). Today, AI augments many of the things that we do, whether that’s helping you [capture a nice selfie](https://ai.googleblog.com/2021/06/take-all-your-pictures-to-cleaners-with.html), or providing [more useful search results](https://blog.google/products/search/how-ai-making-information-more-useful/), or warning hundreds of millions of people [when and where flooding will occur](https://ai.googleblog.com/2020/09/the-technology-behind-our-recent.html). Twenty years of advances in research have helped elevate AI from a promising idea to an indispensable aid in billions of people’s daily lives. And for all that progress, I’m still excited about its as-yet-untapped potential – AI is poised to help humanity confront some of the toughest challenges we’ve ever faced, from persistent problems like illness and inequality to emerging threats like climate change.

But matching the depth and complexity of those urgent challenges will require new, more capable AI systems – systems that can combine AI’s proven approaches with nascent research directions to be able to solve problems we are unable to solve today. To that end, teams across Google Research are working on elements of a next-generation AI architecture we think will help realize such systems.

### We call this new AI architecture Pathways.

Pathways is a new way of thinking about AI that addresses many of the weaknesses of existing systems and synthesizes their strengths. To show you what I mean, let’s walk through some of AI’s current shortcomings and how Pathways can improve upon them.

**Today's AI models are typically trained to do only one thing. Pathways will enable us to train a single model to do thousands or millions of things.**

Today’s AI systems are often trained from scratch for each new problem – the mathematical model’s parameters are initiated literally with random numbers. Imagine if, every time you learned a new skill (jumping rope, for example), you forgot everything you’d learned – how to balance, how to leap, how to coordinate the movement of your hands – and started learning each new skill from nothing.

That’s more or less how we train most machine learning models today. Rather than extending existing models to learn new tasks, we train each new model from nothing to do one thing and one thing only (or we sometimes specialize a general model to a specific task). The result is that we end up developing thousands of models for thousands of individual tasks. Not only does learning each new task take longer this way, but it also requires much more data to learn each new task, since we’re trying to learn everything about the world and the specifics of that task from nothing (completely unlike how people approach new tasks).

Instead, we’d like to train one model that can not only handle many separate tasks, but also draw upon and combine its existing skills to learn new tasks faster and more effectively. That way what a model learns by training on one task – say, learning how aerial images can predict the elevation of a landscape – could help it learn another task -- say, predicting how flood waters will flow through that terrain.

We want a model to have different capabilities that can be called upon as needed, and stitched together to perform new, more complex tasks – a bit closer to the way the mammalian brain generalizes across tasks.

**Today's models mostly focus on one sense. Pathways will enable multiple senses.**

People rely on multiple senses to perceive the world. That’s very different from how contemporary AI systems digest information. Most of today’s models process just one modality of information at a time. They can take in text, or images or speech — but typically not all three at once.

Pathways could enable multimodal models that encompass vision, auditory, and language understanding simultaneously. So whether the model is processing the word “leopard,” the sound of someone saying “leopard,” or a video of a leopard running, the same response is activated internally: the concept of a leopard. The result is a model that’s more insightful and less prone to mistakes and biases.

And of course an AI model needn’t be restricted to these familiar senses; Pathways could handle more abstract forms of data, helping find useful patterns that have eluded human scientists in complex systems such as climate dynamics.

**Today's models are dense and inefficient. Pathways will make them sparse and efficient.**

A third problem is that most of today’s models are “dense,” which means the whole neural network activates to accomplish a task, regardless of whether it’s very simple or really complicated.

This, too, is very unlike the way people approach problems. We have many different parts of our brain that are specialized for different tasks, yet we only call upon the relevant pieces for a given situation. There are close to a hundred billion neurons in your brain, but you rely on a small fraction of them to interpret this sentence.

AI can work the same way. We can build a single model that is “sparsely” activated, which means only small pathways through the network are called into action as needed. In fact, the model dynamically learns which parts of the network are good at which tasks -- it learns how to route tasks through the most relevant parts of the model. A big benefit to this kind of architecture is that it not only has a larger capacity to learn a variety of tasks, but it’s also faster and much more energy efficient, because we don’t activate the entire network for every task.

For example, GShard and Switch Transformer are two of the largest machine learning models we’ve ever created, but because both use sparse activation, they [consume less than 1/10th the energy](https://blog.google/technology/ai/minimizing-carbon-footprint/) that you’d expect of similarly sized dense models — while being as accurate as dense models.

So to recap: today’s machine learning models tend to overspecialize at individual tasks when they could excel at many. They rely on one form of input when they could synthesize several. And too often they resort to brute force when deftness and specialization of expertise would do.

That’s why we’re building Pathways. Pathways will enable a single AI system to generalize across thousands or millions of tasks, to understand different types of data, and to do so with remarkable efficiency – advancing us from the era of single-purpose models that merely recognize patterns to one in which more general-purpose intelligent systems reflect a deeper understanding of our world and can adapt to new needs.

That last point is crucial. We’re familiar with many of today’s biggest global challenges, and working on technologies to [help address them](https://blog.google/outreach-initiatives/sustainability/sustainability-2021/). But we’re also sure there are major future challenges we haven’t yet anticipated, and many will demand urgent solutions. So, with great care, and always in line with our AI Principles, we’re crafting the kind of next-generation AI system that can quickly adapt to new needs and solve new problems all around the world as they arise, helping humanity make the most of the future ahead of us.

---
Source : [Google blog](https://blog.google/technology/ai/introducing-pathways-next-generation-ai-architecture/)
