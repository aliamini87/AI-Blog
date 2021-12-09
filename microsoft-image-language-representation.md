---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-11-04
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 18
tags:
title:
visibility: public
---

# Turing Bletchley: A Universal Image Language Representation model by Microsoft

![](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/1400x788_Bletchly_no_logo_dot_graphic-1-1024x576.jpg)

Today, the [Microsoft Turing team](https://turing.microsoft.com/) is thrilled to introduce Turing Bletchley, a 2.5-billion parameter Universal Image Language Representation model (T-UILR) that can perform image-language tasks in 94 languages. T-Bletchley has an image encoder and a universal language encoder that vectorize input image and text respectively so that semantically similar images and texts align with each other. This model shows uniquely powerful capabilities and a groundbreaking advancement in image language understanding.

T-Bletchley outperforms state-of-the-art models, like [Google’s ALIGN](https://arxiv.org/abs/2102.05918), on English image-language data sets (ImageNet, CIFAR, and COCO), and outperforms [MULE,](https://arxiv.org/abs/1909.03493) [SMALR,](https://arxiv.org/abs/2004.04312) and [M3P](https://arxiv.org/abs/2006.02635) on universal image language data sets (Multi30k and COCO). To see T-Bletchley in action navigate to the [demo](https://go.microsoft.com/fwlink/?linkid=2178904).

## Significance of multi-modal and universal

![Three sets of four images. The first set shows different views of the Eiffel Tower at night retrieved using a Korean-language query. The second set shows different images of people playing soccer in the rain, retrieved using a query in Spanish. The third set shows different views of cats interacting with computers using a Finnish-language query that translates to English as “cat programming”. ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/Bletchley-Fig1-1024x682.jpg)

Image showing “a beautiful sunset on the beach”

Language and vision are inherently linked. When we hear the statement “a beautiful sunset on the beach” we imagine an image similar to the one above. Models that focus only on language fail to capture this link. To these models, sentences are no more than a grammatically correct sequence of words.

Furthermore, vision is a global modality. The same sight of the beach sunset can be narrated in any language (_“una hermosa puesta de sol en la playa”_, _“un beau coucher de soleil sur la plage”_, _“Matahari terbenam yang indah di pantai”_, etc.), and it would not change the corresponding visual representation. Traditional multi-modal models tie vision to a particular language (most commonly English) and therefore fail to capture this universal property of vision.

With T-Bletchley, we address both these shortcomings. We take a multi-modal approach that advances a computer’s ability to understand language as well as understand images natively, just from pixels. Additionally, we consider language modality with a universal-first approach when developing the model. The result is a one-of-a-kind universal multi-modal model that understands images and text across 94 different languages, resulting in some impressive capabilities. For example, by utilizing a common image-language vector space, without using any metadata or extra information like surrounding text, T-Bletchley can retrieve images that match a text description provided in any language. It can also find images that answer text-based questions in any language, or images that are semantically like another image.

## T-Bletchley in action

To test the capabilities of T-Bletchley, we built an image retrieval system consisting of 30 million randomly sampled images from the web that were unseen by the model during training. [The images – without any captions, alt-text or other forms of text metadata – were encoded by the image encoder and stored in an index](https://go.microsoft.com/fwlink/?linkid=2178904).

We built two types of retrieval systems – text-to-image and image-to-image. We vectorized the input queries (for text-to-image with the text encoder and for image-to-image with the image encoder). We use the encoded vector as key and query the index to find its nearest neighbors in the vector space using the approximate nearest neighbor (ANN) algorithm HNSW. The nearest neighbors are then displayed as the image retrieval results.

Today’s image retrieval systems depend heavily on text metadata that is available for images, e.g., image captions, alt-text, surrounding text, image URL, etc. T-Bletchley is unique in that the system can do image retrieval from just the encoded image vectors and does not use any text metadata. This is a big step in true image understanding as compared to today’s systems. Moreover, the demo was built directly with the pre-trained model and not finetuned with any image retrieval task.

In addition, today’s image retrieval systems also use object tagging algorithms applied to images which augment the text metadata (i.e., add tags like car, house, beach, etc. generated from the image). Since the object tagging systems are trained by human-labeled data, the number of classes (tags) is extremely limited. T-Bletchley is trained with unsupervised data, and as a result, it understands a very large number of objects, actions, and many other concepts (dancing, programming, racing, etc.) of the real world.

Below are some examples that showcase the capabilities of T-Bletchley in an image retrieval system.

## Universal text-to-image retrieval

Below are examples of images retrieved using text-based queries in multiple languages:

![Three sets of four images. The first set shows different views of the Eiffel Tower at night retrieved using a Korean-language query. The second set shows different images of people playing soccer in the rain, retrieved using a query in Spanish. The third set shows different views of cats interacting with computers using a Finnish-language query that translates to English as “cat programming”. ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/BletchlyFig3-1024x539.png)

The third example shows that T-Bletchley “understands” the act of programming and has carved out a vector subspace dedicated solely for images of cats programming. True image understanding can be used to improve current retrieval systems to place a greater weight on the image itself.

## Code-switched retrieval

![Two sets of four images. The first set shows small airplanes landing or at rest on unpaved runways, retrieved by a query mixing English and Khmer language. The second set shows groups of people posing for a photo at the Great Wall of China, retrieved using a query mixing English and Chinese.  ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/BletchleyFig3.1-1024x339.png)

T-Bletchley can even retrieve images from non-English language queries written with English script!

![Two sets of four images. The first set shows groups of children playing cricket, retrieved using a query mixing English and English-script Hindi. The second set shows three photos and one artist’s rendering of a train next to bodies of water, retrieved using a query mixing English and English-script Japanese. ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/Bletchleyfig4-1024x346.png)

T-Bletchley can understand sentences containing multiple languages and scripts:

![A set of four images shows a dog playing with a ball, retrieved using a query mixing English and three other languages.](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/BletchleyFig5-1024x167.png)

## Image-to-image retrieval

To evaluate image retrieval, we encode the given image using the image encoder and retrieve the closest image vectors and corresponding images from the index. Because T-Bletchley was trained to pick the best caption for an image, it tends to prefer semantically similar images instead of visually similar ones.

![An image of a map of Seattle and an arrow pointing to four different images of a map of Seattle ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/BletchleyFig6-1024x224.png)

The images retrieved by T-Bletchley are not necessarily similar in appearance to the query image. However, the images, all of the same geography, are ‘semantically similar.’ T-Bletchley does not return the following images from the retrieval set that look like the input image.

![Four maps of different cities ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/BletchleyFig7-1024x212.png)

## Understanding text within images

T-Bletchley is also able to understand text within images without the use of OCR technologies. In the following examples, images are directly passed to the image encoder and stored as 1024 dimensional vectors, and only the cosine similarity between these vectors is used to retrieve similar images.

![Three sets of images. The first set shows a slide comparing microeconomics and macroeconomics. An arrow points to a series of four similar slides comparing microeconomics and macroeconomics. The second set shows a slide entitled: “HOW DOES COVID-19 SPREAD?”. An arrow points to a series of four similar slides explaining how COVID-19 is spread. The third set shows some French text with its English translation: différence entre les données primaires etsecondaires  (difference between primary and secondary data in french). An arrow points to four separate images with English text referring to “primary data” and “secondary data”. ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/BlechleyFig8-1024x508.png)

In the first example, T-Bletchley understands that the text in the image is about the differences between microeconomics and macroeconomics and retrieves similar slides. In the second example, T-Bletchley retrieves images related to COVID-19 even though T-Bletchley’s training data pre-dates COVID-19.

This capability is universal—it can be used in multiple languages. The examples below show retrieval in French and Arabic.

![An image of a text book cover titled: “La Revolution francaise”, with an arrow pointing to a set of four similar images of textbooks depicting the French Revolution and other French history. 
An image of a vintage advertisment for Coca-Cola with an arrow pointing to a set of four similar images, two in Arabic and two in English. ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/BletchleyFig9-1024x414.png)

## T-Bletchley: model development

### Dataset

T-Bletchley was trained using billions of image-caption pairs drawn from the web.

Examples of the dataset are depicted below.

![A set of three captions with a related image. The first query: “Photo of Joy Yee's Noodle Kitchen - Evanston, IL, United States. Huge selection of food”, points to a restaurant menu. The second caption: “2016 Ford Shelby GT350R – Photo Gallery  - RoadandTrack.com”, points to a photo of a white sports car. The third query: “фото кувшинов с водой”, which translates to “photo of jugs of water” in Russian, points to a photo of five clear drinking glasses being filled with water. ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/BletchleyFig10.png)

A large, diverse training dataset resulted in a robust model that can handle a wide variety of images. To achieve universality, we trained the model on a parallel corpus of 500 million translation pairs. These pairs were created by extracting sentences from document-aligned webpages from common crawl corpus. Adding the Translated Text Contrasted Task allowed us to create a language-agnostic vector representation of captions, which helped make the model much more universal.

## Model architecture & training

T-Bletchley consists of transformer-based image and text encoders which are both analogous to the [BERT-large](https://arxiv.org/abs/1810.04805) architecture.

![A set of two images. The image on the left is an illustration of the image text contrastive task. Images containing a paper boat, flowers and a bird are shown to be encoded by the image encoder. Corresponding captions in different languages are shown to be encoded by the text encoder. Contrastive loss is then applied over the resulting vectors. The image on the right is an illustration of the translation text contrastive task. Sentences and their translations in different languages are encoded by the text encoder and the contrastive loss is applied over the resulting vectors. ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/1200x627_Bletchly_Slide5_graphics_edited_Light-2.jpg)

Images and captions were independently encoded, and the model was then trained by applying a contrastive loss on the generated image and text vectors. Similarly, to create a language-agnostic representation, each sentence from a translation pair was independently encoded and a contrastive loss was applied over the resulting batch of vectors.

![An illustration of how the image text contrastive and translation text contrastive tasks work together to help align the space of images, English text and non-English text. On the left side of the illustration, the three domains—Image Domain, English Domain, and Non-English Domain--are segregated. An arrow labeled “Image-Captions training data” points to another depiction of the three domains where the image domain and the English domain intersect but the non-English domain is still separate and shown in gray to show that it’s not significantly affected. A two headed arrow with the label “Image-Text contrastive loss” is drawn between the image and English domains.  
Towards the bottom of the image, an arrow labeled “Parallel corpus training data” points to another depiction of the three domains where the English domain and the non-English domain intersect but the image domain is separate and shown in gray to indicate that it is not significantly affected. A two-headed arrow with the label “Translated Text Contrastive loss” is drawn between the English and non-English domains. 
Finally, a third arrow with the label “Resulting Effect” is drawn to the right of the image which points to a depiction of all three domains intersecting. ](https://www.microsoft.com/en-us/research/uploads/prod/2021/11/1200x627_Bletchly_Slide1_graphics_edited_Light-1-1024x535.jpg)

In this way, despite the image caption pairs being predominantly in English, we managed to align captions in different languages with corresponding images.

We leveraged the kernels in the [DeepSpeed](https://github.com/microsoft/DeepSpeed) library (compatible with PyTorch) for our transformer’s implementation and the [ZeRO optimizer](https://www.microsoft.com/en-us/research/publication/zero-memory-optimization-towards-training-a-trillion-parameter-models/) for training the model.

## In-depth model evaluation

T-Bletchley advances the state of the art across multiple public benchmarks.

### English

For this evaluation, we followed the prompt engineering and ensembling followed in Google’s [ALIGN](https://arxiv.org/abs/2102.05918) paper. T-Bletchley outperforms Google’s ALIGN model on English image-language benchmarks and sets a new state of the art standard in zero shot image classification, an area pioneered by [OpenAI’s CLIP model](https://openai.com/blog/clip/).



| Model       | ImageNet | CIFAR-100 | CIFAR-10 | COCO R@1 image->text | COCO R@1 text->image |
| ----------- |:--------:|:---------:|:--------:|:--------------------:|:--------------------:|
| [ALIGN](https://arxiv.org/abs/2102.05918)       |   76.4   |     -     |    -     |         58.6         |         45.6         |
| T-Bletchley |   79.0   |   83.5    |   97.7   |         59.1         |         43.3         | 


When fine-tuned for retrieval, T-Bletchley outperforms ALIGN, the previous state of the art, by more than two points on the COCO test set.

<table>
    <thead>
        <tr>
            <th rowspan=2>Model</th>
            <th colspan=2>Flickr 30k Recall @1</th>
            <th colspan=2>COCO Recall @1</th>
        </tr>
        <tr>
            <th>image -> text</th>
            <th>text->image</th>
            <th>image -> text</th>
            <th>text->image</th>
        </tr>
    </thead>
    <tbody>
        <tr>    
            <td> <a href="https://arxiv.org/abs/2004.06165">OSCAR</a> </td>
            <td>-</td>
            <td>-</td>
            <td>73.5</td>
            <td>57.5</td>
        </tr>
        <tr>
            <td> <a href="https://arxiv.org/abs/2102.05918">ALIGN</a> </td>
            <td>95.3</td>
            <td>84.9</td>
            <td>77</td>
            <td>59.5</td>
        </tr>
        <tr>
            <td>T-Bletchley</td>
            <td>97.1</td>
            <td>87.4</td>
            <td>80.2</td>
            <td>62.3</td>
        </tr>
    </tbody>
</table>



T-Bletchley achieves state-of-the-art results in English-specific tasks compared to English-only models. T-Bletchley’s English performance is not hindered by universal language support!

### Universal

T-Bletchley’s universal retrieval capabilities were evaluated on the Multi30k, COCO-CN and COCO-JP datasets and compared to multilingual models. Even before fine-tuning, T-Bletchley significantly outperforms previous models.

<table>
    <thead>
        <tr>
            <th rowspan=2>Setting</th>
            <th rowspan=2>Model</th>
            <th colspan=3>Multi30k</th>
            <th colspan=2>COCO</th>
        </tr>
        <tr>
            <th>French</th>
            <th>text->German</th>
            <th>image ->Czech</th>
            <th>text->Chinese</th>
            <th>text->Japanese</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=2>Zero Shot</td>
            <td><a href="https://arxiv.org/abs/2006.02635">M3P</a></td>
            <td>27.1</td>
            <td>36.8</td>
            <td>20.4</td>
            <td>32.3</td>
            <td>33.3</td>
        </tr>
        <tr>
            <td>T-Bletchley</td>
            <td>85</td>
            <td>83.2</td>
            <td>81.2</td>
            <td>81.5</td>
            <td>64.8</td>
        </tr>
    </tbody>
</table>

When T-Bletchley is fine-tuned, the model sets new state-of-the-art results in multiple languages, shown in the table below.

<table>
    <thead>
        <tr>
            <th rowspan=2>Setting</th>
            <th rowspan=2>Model</th>
            <th colspan=3>Multi30k</th>
            <th colspan=2>COCO</th>
        </tr>
        <tr>
            <th>French</th>
            <th>text->German</th>
            <th>image ->Czech</th>
            <th>text->Chinese</th>
            <th>text->Japanese</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=4>Zero Shot</td>
            <td><a href="https://arxiv.org/abs/1909.03493">MULE</a></td>
            <td>62.3</td>
            <td>64.1</td>
            <td>57.7</td>
            <td>75.6</td>
            <td>75.9</td>
        </tr>
        <tr>
            <td><a href="https://arxiv.org/abs/2004.04312">SMALR</a></td>
            <td>65.9</td>
            <td>69.8</td>
            <td>64.8</td>
            <td>76.7</td>
            <td>77.5</td>
        </tr>
        <tr>
            <td><a href="https://arxiv.org/abs/2006.02635">M3P</a></td>
            <td>73.9</td>
            <td>82.7</td>
            <td>72.2</td>
            <td>86.2</td>
            <td>87.9</td>
        </tr>
        <tr>
            <td>T-Bletchley</td>
            <td>94.6</td>
            <td>94.3</td>
            <td>93.6</td>
            <td>89.0</td>
            <td>86.3</td>
        </tr>
    </tbody>
</table>


### Future applications

The goal of T-Bletchley is to create a model that understands text and images as seamlessly as humans do. The first version of T-Bletchley represents a significant breakthrough in this mission. We expect the T-Bletchley model to improve image question and answering, image search, and image-to-image search experiences in Bing, Microsoft Office and Azure.

**Note on Responsible AI:** Like other publicly available models, the Microsoft Turing models are trained with billions of pages of publicly available text and images, and hence may have picked up biases around gender, race and more from these public documents. Mitigating negative effects from these biases is a difficult, industry-wide issue and Microsoft is committed to the advancement and use of AI grounded in principles that put people first and benefit society. We are putting these [Microsoft AI principles](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1%3aprimaryr6) into practice throughout the company and have taken extensive precautionary measures to prevent these implicit biases from getting exhibited when using the models in our products. We strongly encourage developers to do the same by putting appropriate guardrails and mitigations in place before taking these models to production.

---
Source : [Microsoft.com](https://www.microsoft.com/en-us/research/blog/turing-bletchley-a-universal-image-language-representation-model-by-microsoft/)
