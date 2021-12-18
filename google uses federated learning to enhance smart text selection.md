---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-12-18
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 22
tags:
title:
visibility: public

---

# google uses federated learning to enhance smart text selection
In this [article](https://ai.googleblog.com/2021/11/predicting-text-selections-with.html) by google blog, they discuss how they use federated learning to enhance smart text selection feature in Android. This is important because federated learning is a way to respect privacy of users. Instead of transfering data to the servers for training, training of the network will be done inside the device and only updated weights of the network transferred to the server. They also developed the tools that are needed for this. 
In the following, their article is provided.

Smart Text Selection, [launched in 2017 as part of Android O](https://www.youtube.com/watch?v=Y2VF8tmLFHw&t=4832s), is one of Android’s most frequently used features, helping users select, copy, and use text easily and quickly by predicting the desired word or set of words around a user’s tap, and automatically expanding the selection appropriately. Through this feature, selections are automatically expanded, and for selections with defined classification types, e.g., addresses and phone numbers, users are offered an app with which to open the selection, saving users even more time.

[![](https://blogger.googleusercontent.com/img/a/AVvXsEijkmRDALy_mwfLyCe3ZdDg2L5P_VKF9AtcX2uodJ1w8Jjb8F_ibZ3Dp8GK3SNmxFySJHItD64Vcc20UkbCOJiSmMljeTLyLvdNwXw8TUdH4gnL7qMOvHP606EYICm9j6IYoSbdNo5EvzuClY8MMjwYl9YOug5Pk_pynWtQEnYWPVsZYDhpS7tg1R2rnQ=s320)](https://blogger.googleusercontent.com/img/a/AVvXsEijkmRDALy_mwfLyCe3ZdDg2L5P_VKF9AtcX2uodJ1w8Jjb8F_ibZ3Dp8GK3SNmxFySJHItD64Vcc20UkbCOJiSmMljeTLyLvdNwXw8TUdH4gnL7qMOvHP606EYICm9j6IYoSbdNo5EvzuClY8MMjwYl9YOug5Pk_pynWtQEnYWPVsZYDhpS7tg1R2rnQ=s480)

Today we describe how we have improved the performance of Smart Text Selection by using [federated learning](https://ai.googleblog.com/2017/04/federated-learning-collaborative.html) to train the neural network model on user interactions responsibly while preserving user privacy. This work, which is part of Android’s new [Private Compute Core](https://security.googleblog.com/2021/09/introducing-androids-private-compute.html) secure environment, enabled us to improve the model’s selection accuracy by up to 20% on some types of entities.

## Server-Side Proxy Data for Entity Selections  
Smart Text Selection, which is the same technology behind [Smart Linkify](https://ai.googleblog.com/2018/08/the-machine-learning-behind-android.html), does not predict arbitrary selections, but focuses on well-defined entities, such as addresses or phone numbers, and tries to predict the selection bounds for those categories. In the absence of multi-word entities, the model is trained to only select a single word in order to minimize the frequency of making multi-word selections in error.

The Smart Text Selection feature was originally trained using proxy data sourced from web pages to which [schema.org](http://schema.org/) annotations had been applied. These entities were then embedded in a selection of random text, and the model was trained to select just the entity, without spilling over into the random text surrounding it.

While this approach of training on schema.org-annotations worked, it had several limitations. The data was quite different from text that we expect users see on-device. For example, websites with schema.org annotations typically have entities with more proper formatting than what users might type on their phones. In addition, the text samples in which the entities were embedded for training were random and did not reflect realistic context on-device.

## On-Device Feedback Signal for Federated Learning 
With this new launch, the model no longer uses proxy data for span prediction, but is instead trained on-device on real interactions using federated learning. This is a training approach for machine learning models in which a central server coordinates model training that is split among many devices, while the raw data used stays on the local device. A standard federated learning training process works as follows: The server starts by initializing the model. Then, an iterative process begins in which (a) devices get sampled, (b) selected devices improve the model using their local data, and (c) then send back only the improved model, not the data used for training. The server then averages the updates it received to create the model that is sent out in the next iteration.

<iframe allowfullscreen="" height="360" src="https://www.youtube.com/embed/gbRJPa9d-VU" width="640" youtube-src-id="gbRJPa9d-VU"></iframe>

For Smart Text Selection, each time a user taps to select text and corrects the model’s suggestion, Android gets precise feedback for what selection span the model should have predicted. In order to preserve user privacy, the selections are temporarily kept on the device, without being visible server-side, and are then used to improve the model by applying federated learning techniques. This technique has the advantage of training the model on the same kind of data that it sees during inference.

## Federated Learning & Privacy 
One of the advantages of the federated learning approach is that it enables user privacy, because raw data is not exposed to a server. Instead, the server only receives updated model weights. Still, to protect against various threats, we explored ways to protect the on-device data, securely aggregate gradients, and reduce the risk of model memorization.

The on-device code for training Federated Smart Text Selection models is part of Android’s Private Compute Core secure environment, which makes it particularly well situated to securely handle user data. This is because the training environment in Private Compute Core is isolated from the network and data egress is only allowed when federated and other privacy-preserving techniques are applied. In addition to network isolation, data in Private Compute Core is protected by policies that restrict how it can be used, thus protecting from malicious code that may have found its way onto the device.

To aggregate model updates produced by the on-device training code, we use [Secure Aggregation](https://research.google/pubs/pub45808/), a cryptographic protocol that allows servers to compute the mean update for federated learning model training without reading the updates provided by individual devices. In addition to being individually protected by Secure Aggregation, the updates are also protected by transport encryption, creating two layers of defense against attackers on the network.

Finally, we looked into model memorization. In principle, it is possible for characteristics of the training data to be encoded in the updates sent to the server, survive the aggregation process, and end up being memorized by the global model. This could make it possible for an attacker to attempt to reconstruct the training data from the model. We used methods from [Secret Sharer](https://arxiv.org/abs/1802.08232), an analysis technique that quantifies to what degree a model unintentionally memorizes its training data, to empirically verify that the model was not memorizing sensitive information. Further, we employed data masking techniques to prevent certain kinds of sensitive data from ever being seen by the model

In combination, these techniques help ensure that Federated Smart Text Selection is trained in a way that preserves user privacy.

## Achieving Superior Model Quality
Initial attempts to train the model using federated learning were unsuccessful. The loss did not converge and predictions were essentially random. Debugging the training process was difficult, because the training data was on-device and not centrally collected, and so, it could not be examined or verified. In fact, in such a case, it’s not even possible to determine if the data looks as expected, which is often the first step in debugging machine learning pipelines.

To overcome this challenge, we carefully designed high-level metrics that gave us an understanding of how the model behaved during training. Such metrics included the number of training examples, selection accuracy, and [recall and precision](https://en.wikipedia.org/wiki/Precision_and_recall) metrics for each entity type. These metrics are collected during federated training via [federated analytics](https://ai.googleblog.com/2020/05/federated-analytics-collaborative-data.html), a similar process as the collection of the model weights. Through these metrics and many analyses, we were able to better understand which aspects of the system worked well and where bugs could exist.

After fixing these bugs and making additional improvements, such as implementing on-device filters for data, using better [federated optimization methods](https://arxiv.org/abs/2003.00295) and applying more [robust gradient aggregators](https://www.tensorflow.org/federated/api_docs/python/tff/learning/robust_aggregator), the model trained nicely.

## Results
Using this new federated approach, we were able to significantly improve Smart Text Selection models, with the degree depending on the language being used. Typical improvements ranged between 5% and 7% for multi-word selection accuracy, with no drop in single-word performance. The accuracy of correctly selecting addresses (the most complex type of entity supported) increased by between 8% and 20%, again, depending on the language being used. These improvements lead to millions of additional selections being automatically expanded for users every day.

## Internationalization
An additional advantage of this federated learning approach for Smart Text Selection is its ability to scale to additional languages. Server-side training required manual tweaking of the proxy data for each language in order to make it more similar to on-device data. While this only works to some degree, it takes a tremendous amount of effort for each additional language.

The federated learning pipeline, however, trains on user interactions, without the need for such manual adjustments. Once the model achieved good results for English, we applied the same pipeline to Japanese and saw even greater improvements, without needing to tune the system specifically for Japanese selections.

We hope that this new federated approach lets us scale Smart Text Selection to many more languages. Ideally this will also work without manual tuning of the system, making it possible to support even low-resource languages.

## Conclusion
We developed a federated way of learning to predict text selections based on user interactions, resulting in much improved Smart Text Selection models deployed to Android users. This approach required the use of federated learning, since it works without collecting user data on the server. Additionally, we used many state-of-the-art privacy approaches, such as Android's new Private Compute Core, Secure Aggregation and the Secret Sharer method. The results show that privacy does not have to be a limiting factor when training models. Instead, we managed to obtain a significantly better model, while ensuring that users' data stays private.

## Acknowledgements
_Many people contributed to this work. We would like to thank Lukas Zilka, Asela Gunawardana, Silvano Bonacina, Seth Welna, Tony Mak, Chang Li, Abodunrinwa Toki, Sergey Volnov, Matt Sharifi, Abhanshu Sharma, Eugenio Marchiori, Jacek Jurewicz, Nicholas Carlini, Jordan McClead, Sophia Kovaleva, Evelyn Kao, Tom Hume, Alex Ingerman, Brendan McMahan, Fei Zheng, Zachary Charles, Sean Augenstein, Zachary Garrett, Stefan Dierauf, David Petrou, Vishwath Mohan, Hunter King, Emily Glanz, Hubert Eichner, Krzysztof Ostrowski, Jakub Konecny, Shanshan Wu, Janel Thamkul, Elizabeth Kemp, and everyone else involved in the project._

---
Source: [google blog](https://ai.googleblog.com/2021/11/predicting-text-selections-with.html)