---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-10-16
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 10
tags:
title:
visibility: public



---




# Teaching AI to perceive the world through your eyes

AI that understands the world from a first-person point of view could unlock a new era of immersive experiences, as devices like augmented reality (AR) glasses and virtual reality (VR) headsets become as useful in everyday life as smartphones. Imagine your AR device displaying exactly how to hold the sticks during a drum lesson, guiding you through a recipe, helping you find your lost keys, or recalling memories as holograms that come to life in front of you.

To build these new technologies, we need to teach AI to understand and interact with the world like we do, from a first-person perspective — commonly referred to in the research community as egocentric perception. Today’s computer vision (CV) systems, however, typically learn from millions of photos and videos that are captured in third-person perspective, where the camera is just a spectator to the action. “Next-generation AI systems will need to learn from an entirely different kind of data — videos that show the world from the center of the action, rather than the sidelines,” says [Kristen Grauman, lead research scientist at Facebook.](https://ai.facebook.com/people/kristen-grauman/)

Facebook AI is announcing [Ego4D](https://ai.facebook.com/research/publications/ego4d-unscripted-first-person-video-from-around-the-world-and-a-benchmark-suite-for-egocentric-perception), an ambitious long-term project aimed at solving research challenges in egocentric perception. We brought together a consortium of 13 universities and labs across nine countries, who collected more than 2,200 hours of first-person video in the wild, featuring over 700 participants going about their daily lives. This dramatically increases the scale of egocentric data publicly available to the research community by an order of magnitude, more than 20x greater than any other data set in terms of hours of footage. Facebook funded the project through academic gifts to each of the participating universities.

![](https://scontent-hkg4-2.xx.fbcdn.net/v/t39.2365-6/244650956_262731809117347_4121150845039607684_n.jpg?_nc_cat=104&ccb=1-5&_nc_sid=ad8a9d&_nc_ohc=EOJhI6LYcSgAX-mboeD&_nc_ht=scontent-hkg4-2.xx&oh=777cdfc09f3dad6ac2944cec570337dc&oe=61700265)

In collaboration with the consortium and Facebook Reality Labs Research (FRL Research), Facebook AI also developed five benchmark challenges centered on first-person visual experience that will spur advancements toward real-world applications for future AI assistants. Ego4D’s five benchmarks are:

-   Episodic memory: What happened when? (e.g., “Where did I leave my keys?”)
    
-   Forecasting: What am I likely to do next? (e.g., “Wait, you’ve already added salt to this recipe.”)
    
-   Hand and object manipulation: What am I doing? (e.g., “Teach me how to play the drums.”)
    
-   Audio-visual diarization: Who said what when? (e.g., “What was the main topic during class?”)
    
-   Social interaction: Who is interacting with whom? (e.g., “Help me better hear the person talking to me at this noisy restaurant.”)
    

These benchmarks will catalyze research on the building blocks necessary to develop smarter AI assistants that can understand and interact not just in the real world but also in the metaverse, where physical reality, AR, and VR all come together in a single space.

The data sets will be publicly available in [November of this year for researchers](https://l.facebook.com/l.php?u=http%3A%2F%2Fego4d-data.org%2F&h=AT3FoZ3Df70N8utZSqzXSyK_kpF1CEoQmklVoMz4tKIVJ0HLU_KdE9dSNTWHkh4lBbtFhAnFPj6Lwdk9euKTSthfT25wGOEl9CUBUtbhUVxJx032w8fO4AakWQZvH2oHDYLYLeesxv6MKQmhjBqmdw) who sign Ego4D’s data use agreement. Each university team was responsible for complying with their own institutional research policy. The process involved developing a study protocol compliant with standards from institutional research ethics committees and/or review boards, including a process to obtain informed consent and/or video release from participants.

As a supplement to this work, researchers from FRL used Vuzix Blade® Smart Glasses to collect an additional 400 hours of first-person video data in staged environments in our research labs with written consent from the individuals who were captured on video. This data will be released as well.

Through our commitment to open science and research, we hope the AI field will be able to more rapidly spur progress in egocentric perception.

## Why egocentric perception is hard

Let’s say you’re about to ride a roller coaster for the first time. In addition to the adrenaline rush and maybe some (hopefully joyous) screaming, the ride looks completely different from the rider’s perspective than it did on the ground.

While it’s easy for people to relate to both first- and third-person perspectives, AI today doesn't share that level of understanding. Strap a CV system onto a roller-coaster ride and it likely won’t have any idea what it’s looking at, even if it’s trained on hundreds of thousands of images or videos of roller coasters shown from the sidelines on the ground.

“For AI systems to interact with the world the way we do, the AI field needs to evolve to an entirely new paradigm of first-person perception,” Grauman says. “That means teaching AI to understand daily life activities through human eyes in the context of real-time motion, interaction, and multisensory observations.”

![](https://scontent-hkg4-2.xx.fbcdn.net/v/t39.2365-6/244418518_1031530464301216_3359625472102924233_n.png?_nc_cat=109&ccb=1-5&_nc_sid=ad8a9d&_nc_ohc=7BtUFtvEKy8AX8BHkPk&_nc_ht=scontent-hkg4-2.xx&oh=7539eef187c457d3408240bc9620bb7c&oe=616FAB49)

The Ego4D project focuses on providing researchers with the tools and benchmarks necessary to catalyze research and push the frontier of egocentric perception.

## Unpacking the real-world data set

Benchmarks and data sets have historically proved to be crucial catalysts for innovation for the AI industry. After all, today’s CV systems, which can identify virtually any object in an image, were built on top of data sets and benchmarks — e.g., MNIST, COCO, and ImageNet — that provided researchers with a test bed for research on real-world images.

But egocentric perception is a whole new arena. We can’t build tomorrow’s innovations using yesterday’s tools. The unprecedented scale and diversity of Ego4D is crucial for ushering in the next generation of intelligent AI systems.


To build this first-of-its-kind data set, teams at each of our partner universities distributed off-the-shelf head-mounted cameras and other wearable sensors to research participants so that they could capture first-person, unscripted video of their daily lives. They focused on having participants capture video from day-to-day scenarios, such as grocery shopping, cooking, and talking while playing games and engaging in other group activities with family and friends. The video collection captures what the camera wearer chooses to gaze at in a specific environment, what the camera wearer is doing with their hands and objects in front of them, and how the camera wearer interacts with other people from the egocentric perspective. So far, the collection features camera wearers performing hundreds of activities and interactions with hundreds of different objects.


The participants featured in the Ego4D data set live in the U.K., Italy, India, Japan, Saudi Arabia, Singapore, Colombia, Rwanda, and the United States, varying across ages, professions, and genders, which were self-identified. Compared with existing data sets, the Ego4D data set provides a greater diversity of scenes, people, and activities, which increases the applicability of models trained for people across backgrounds, ethnicities, occupations, and ages.

We believe global representation is crucial for egocentric research because the egocentric visual experience will differ significantly across cultural and geographic contexts. If, in the future, someone is wearing AR glasses while cooking and asks an AI assistant to guide them through a curry recipe, for example, the AI system under the hood should ideally be able to recognize that cooking curry often looks different from region to region.

## Building intelligent egocentric perception

“Equally important as data collection is defining the right research benchmarks or tasks,” Grauman says. “A major milestone for this project has been to distill what it means to have intelligent egocentric perception, where we recall the past, anticipate the future, and interact with people and objects.” Ego4D’s five challenging new benchmarks provide a common objective for researchers to build fundamental research for real-world perception of visual and social contexts.

Building these benchmarks required rigorous annotation of our egocentric data set. For this massive annotation effort, Facebook AI leveraged trained third-party annotators for labeling the data needed to train and evaluate algorithms on our five benchmark tasks. This entailed using [Facebook’s Human-AI loop (Halo) annotation platform](https://ai.facebook.com/blog/how-facebook-annotates-multimodal-training-data-for-ml/), for which we wrote specific guidelines for this type of annotation task and fine-tuned the tool itself. We collected a wide variety of label types, such as dense textual narrations describing the camera wearer’s activity, spatial and temporal annotations on objects and actions, and multimodal speech transcription. In total, thousands of hours of video were transcribed and millions of annotations were collected, with sampling criteria spanning the video data from all our partners in the consortium to ensure diversity in the resulting data set. As a result, researchers can readily use the Ego4D data set for building and testing their models on our benchmarks as soon as it’s released, later this year.

Here’s a breakdown of the benchmarks, which are fundamental building blocks that could form the basis for more useful AI assistants, robots, and other future innovations:

1.  **Episodic memory: What happened when?** AI could answer freeform questions and extend your personal memory by retrieving key moments in past egocentric videos. To do this, the model must localize the response to a query within past video frames — and, when relevant, further provide 3D spatial directions in the environment. So, if you’re preparing your parents to stay with your children, you could ask your AI assistant or home robot questions, such as “Where did I leave my kid’s favorite teddy bear?”
    
2.  **Forecasting: What will I do next?** AI could understand how the camera wearer’s actions might affect the future state of the world, in terms of where the person is likely to move, what objects they are likely to touch, or what activity they are likely to engage in next. Forecasting actions requires not only recognizing what has happened but also looking ahead to anticipate next moves. This will allow future AI systems that deliver helpful guidance in the moment. For example, just as you’re about to grasp a salt shaker, your AI assistant could send a notification to your device saying, “Wait, you’ve already added salt.”
    
3.  **Hand-object interaction: What am I doing and how?**Learning how hands interact with objects is crucial for coaching and instructing on daily tasks. AI must detect first-person human-object interactions, recognize grasps, and detect object state changes. This thrust is also motivated by robot learning, where a robot could gain experience vicariously through people’s experience observed in video. So, when you’re cooking a recipe, your AI assistant could instruct you on which ingredients you need and what you need to do first, understand what you’ve already done, and guide you through each pinch and dash.
    
4.  **Audio-visual diarization: Who said what when?** Humans use sound to understand the world and identify who said what and when. AI of the future could too. If you’re in an important class but are half-distracted because your child’s babysitter is texting you questions at the same time, you could later ask: “What were the main topics during the discussion in class today after the professor handed back our exam?”
    
5.  **Social interaction: How are we interacting?** Beyond recognizing sight and sound cues, understanding social interactions is core to any intelligent AI assistant. A socially intelligent AI would understand who is speaking to whom and who is paying attention to whom. So, the next time you’re at a dinner party, an AI assistant could help you better focus on what the person talking to you across the noisy table is saying.
    

## What’s next for Ego4D and beyond

We're just starting to scratch the surface on egocentric perception. Through the Ego4D project, Facebook AI, FRL, and the university consortium have forged an entirely new path for academics and industry experts to build smarter, more interactive and flexible computer vision systems. And we see a not-so-distant future in which the research we’re doing today could have a positive impact on the way we live, work, and play.

As AI gains a deeper understanding of how people go about life as they normally would, it can begin to contextualize and personalize experiences in ways that haven’t been possible before.

“Ego4D makes it possible for AI to gain knowledge rooted in the physical and social world, gleaned through the first-person perspective of the people who live in it,” Grauman says. “Not only will AI start to understand the world around it better, it could one day be personalized at an individual level — it could know your favorite coffee mug or guide your itinerary for your next family trip. And we're actively working on assistant-inspired research prototypes that could do just that.” ”

With AI-driven capabilities supported by Ego4D’s benchmarks and trained on the data set, it’s possible for assistants to provide value in unique and meaningful ways. Through augmented memory, an AI assistant could help you recall critical pieces of information from a recent conversation with your colleague or locate where your daughter last left her bicycle helmet, and provide supplemental skills in real time to guide you through building your new IKEA furniture or following a new recipe for your dinner party. We believe the value derived from this body of work and continued advancements in the space will propel us toward this future reality.

Later this year, the university consortium will release the data for purposes permitted in the licensing agreement.

Early next year, researchers should look out for the Ego4D research challenge that invites AI experts around the world to teach machines to understand the first-person perspective of our daily life activity.

If you’re attending the 2021 International Conference on Computer Vision, sign up for our [full-day Workshop on Egocentric Perception, Interaction and Computing](https://l.facebook.com/l.php?u=https%3A%2F%2Feyewear-computing.org%2FEPIC_ICCV21%2F&h=AT1GvZ3cfm1Ruw2bajSWb2733nUehmbYcK6Sps92ScOsa3jUIdedk1NxbQLdvIfZi1VL_dthlrza-eKicBtoFHUFXRt0SP_2aaR39jB0qBghQbmLuiz7PB8mlPoNq_yCh02Cp-xl1z8mE__5GCAWCg) on October 17, where you can learn more, ask questions, and share feedback about Ego4D.

_The academic consortium for the Ego4D initiative includes the following lead researchers (also known as principal investigators): CV Jawahar (IIIT Hyderabad), David Crandall (Indiana University), Dima Damen (University of Bristol), Giovanni Maria Farinella (University of Catania), Haizhou Li (National University of Singapore), Kristen Grauman (Facebook AI), Bernard Ghanem (KAUST), Jitendra Malik (Facebook AI), Kris Kitani (CMU and CMU Africa), Aude Oliva (MIT), Hyun Soo Park (University of Minnesota), Jim Rehg (Georgia Tech), Yoichi Sato (University of Tokyo), Jianbo Shi (University of Pennsylvania), Antonio Torralba (MIT), Mike Zheng Shou (National University of Singapore), and Pablo Arbelaez (U. of Los Andes). [Click here](https://l.facebook.com/l.php?u=http%3A%2F%2Fego4d-data.org%2F&h=AT3vrfOiA7OBhQJ3UqsdyMQOPl3BHihRPzfs0KatHBnDSxhvQxWTRtSipkZSjMquwbh0RfUhaTpcEuQxeljfHbxdXezab_5E8tf7SbrqFZ53VFMQFuGNtH27Vhpo-jeVIvvpMhcfYDE-9zZE4jayZg) to learn more about the Ego4D consortium and project._

[Read the full paper](https://ai.facebook.com/research/publications/ego4d-unscripted-first-person-video-from-around-the-world-and-a-benchmark-suite-for-egocentric-perception)

---
Source = [ai.facebook.com](https://ai.facebook.com/blog/teaching-ai-to-perceive-the-world-through-your-eyes?s=09)


