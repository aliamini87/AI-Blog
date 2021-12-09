---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-10-13
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 6
tags:
title:
visibility: public



---




# Models that recognize inputs that differ substantially from most of their training data

![LONGTAIL-1](https://cdn2.hubspot.net/hub/5871640/hubfs/LONGTAIL-1.gif?upscale=true&width=1200&upscale=true&name=LONGTAIL-1.gif)

Models trained using supervised learning struggle to classify inputs that differ substantially from most of their training data. A new method helps them recognize such outliers.  
**What’s new:** Abhijit Guha Roy, Jie Ren, and colleagues at Google developed [Hierarchical Outlier Detection](https://arxiv.org/abs/2104.03829v1?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--WW4Woe1bkMvRM_F_OEmOjFOvxcpKFzO2MXwTE6b_2hSSnVuN42JtfNI3FyDSuSIkTUrRu) (HOD), a loss function that helps models learn to classify out-of-distribution inputs — even if they don’t conform to a class label in the training set.  
**Key insight:** Previous work has proposed two general approaches to handling out-of-distribution inputs. One is to include a catch-all outlier class in the training set. Given the diversity of examples in this class, however, it’s difficult to learn to recognize outliers consistently. The other is to label separate outlier classes in the training set. This enables a trained model to recognize certain kinds of outliers but leaves it unable to identify outlier classes that aren't represented in the training set. HOD attempts to cover the gamut by encouraging a model to classify images both as outliers in general and as specific classes of outlier.  
**How it works:** The authors started with a [ResNet](https://arxiv.org/abs/1512.03385?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--WW4Woe1bkMvRM_F_OEmOjFOvxcpKFzO2MXwTE6b_2hSSnVuN42JtfNI3FyDSuSIkTUrRu) pretrained on [JFT](https://arxiv.org/abs/1503.02531?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--WW4Woe1bkMvRM_F_OEmOjFOvxcpKFzO2MXwTE6b_2hSSnVuN42JtfNI3FyDSuSIkTUrRu) (Google's proprietary collection of 300 million images). They fine-tuned it on [images](https://arxiv.org/abs/1909.05382?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--WW4Woe1bkMvRM_F_OEmOjFOvxcpKFzO2MXwTE6b_2hSSnVuN42JtfNI3FyDSuSIkTUrRu) of roughly 10,000 cases of skin disease, each labeled according to 225 different conditions. Of these, 26 conditions were represented by at least 100 cases; these were assigned an additional “inlier” label. The remaining 199 were assigned an additional “outlier” label. The training, validation, and test sets included a a variety of inlier classes, but the outlier classes were divided among them; that is, the datasets had no outlier classes in common.

-   The ResNet generated a representation of each image in a case. It averaged the representations and passed them through a fully connected layer, forming a single representation of the case.
-   A softmax layer used this representation to identify the condition. Then the model assigned an inlier or outlier label depending on whether the sum of the probabilities of predicting an outlier class exceeded a threshold set by the user.
-   The HOD loss function contains two terms. One encourages the algorithm to identify the correct condition. The other encourages it to assign an accurate inlier or outlier label.

**Results:** Training the model on both outlier status and specific outlier classes helped it learn to recognize outliers in general — although the task still proved difficult. The authors’ approach achieved .794 AUC, while the same architecture trained on only a general outlier label (plus labels for all inlier classes) achieved .756 AUC. When classifying inliers, the model trained on all labels achieved 74 percent accuracy, while the one given only a general outlier label achieved 72.8 percent accuracy.  
**Why it matters:** Real-world applications can be rife with out-of-distribution data. This approach helps models detect both examples that are similar to those in the training dataset but not labeled (for example, new skin conditions) and examples that are substantially different (for example, pictures of iguanas).  
**We're thinking:** Giving models the ability to recognize edge cases could build greater trust in their output.

---
Source: [deeplearning.ai](https://read.deeplearning.ai/the-batch/issue-112/)
