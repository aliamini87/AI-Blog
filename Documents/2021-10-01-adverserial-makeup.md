## Adverserial Makeup


Drop off your adversarial [hats](https://arxiv.org/abs/1908.08705?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz-8QsJWqT2o_J1ShIjCrSsYkFvMAnCBhaA2EXAdYbnlE13tMsuEANbyDdvf7vHFb3GJaHUSl), [eyeglasses](https://users.ece.cmu.edu/~lbauer/papers/2016/ccs2016-face-recognition.pdf?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz-8QsJWqT2o_J1ShIjCrSsYkFvMAnCBhaA2EXAdYbnlE13tMsuEANbyDdvf7vHFb3GJaHUSl), and [tee shirts](https://arxiv.org/abs/1910.11099?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz-8QsJWqT2o_J1ShIjCrSsYkFvMAnCBhaA2EXAdYbnlE13tMsuEANbyDdvf7vHFb3GJaHUSl) to the second-hand store. The latest fashion statement is adversarial makeup.  
**What’s new:** Researchers at Ben-Gurion University and NEC developed a [system](https://arxiv.org/abs/2109.06467?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz-8QsJWqT2o_J1ShIjCrSsYkFvMAnCBhaA2EXAdYbnlE13tMsuEANbyDdvf7vHFb3GJaHUSl) for applying natural-looking makeup that makes people unrecognizable to face recognition models. 

![](https://dl-staging-website.ghost.io/content/images/2021/09/2.gif)

**How it works:** Working with 20 volunteers, the researchers used [FaceNet](https://arxiv.org/abs/1503.03832?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz-8QsJWqT2o_J1ShIjCrSsYkFvMAnCBhaA2EXAdYbnlE13tMsuEANbyDdvf7vHFb3GJaHUSl), which learns a mapping from face images to a compact Euclidean space, to produce heat maps that showed which face regions were most important for identification.

-   They used the consumer-grade virtual makeover app [YouCam Makeup](https://www.youtube.com/channel/UCExTYT6XYEt_bT6qs7m-X0A?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz-8QsJWqT2o_J1ShIjCrSsYkFvMAnCBhaA2EXAdYbnlE13tMsuEANbyDdvf7vHFb3GJaHUSl) to adapt the heatmaps into digital makeup patterns overlaid on each volunteer’s image.
-   They fed iterations of these digitally done-up face shots to FaceNet until the subject was unrecognizable.
-   Then a makeup artist physically applied the patterns to actual faces in neutral tones.
-   The volunteers walked down a hallway, first without and then with makeup, while being filmed by a pair of cameras that streamed their output to the [ArcFace](https://arxiv.org/abs/1801.07698?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz-8QsJWqT2o_J1ShIjCrSsYkFvMAnCBhaA2EXAdYbnlE13tMsuEANbyDdvf7vHFb3GJaHUSl) face recognizer.

**Results:** ArcFace recognized participants wearing adversarial makeup in 1.2 percent of frames. It recognized those wearing no makeup in 47.6 percent of video frames, and those wearing random makeup patterns in 33.7 percent of frames.  
**Why it matters:** This new technique requires only ordinary, unobtrusive makeup, doing away with accessories that might raise security officers’ suspicions. It offers perhaps the easiest way yet for ordinary people to thwart face recognition — at least until the algorithms catch on.

source : [depplearning.ai](https://read.deeplearning.ai/the-batch/issue-111/)
