# Image Transformer Speed-Up Speed Up!

![NESTED](https://cdn2.hubspot.net/hub/5871640/hubfs/NESTED.gif?upscale=true&width=1200&upscale=true&name=NESTED.gif)

The transformer architecture is notoriously inefficient when processing long sequences — a problem in processing images, which are essentially long sequences of pixels. One way around this is to break up input images and process the pieces separately. New work improves upon this already-streamlined approach.  
**What’s new:** Zizhao Zhang and colleagues at Google and Rutgers University simplified an earlier proposal for using transformers to process images. They call their architecture [NesT](https://arxiv.org/abs/2105.12723?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--nlQXRW4-7X-ix91nIeK09eSC7HZEucHhs-tTrQrkj708vf7H2NG5TVZmAM8cfkhn20y50).  
**Key Insight:**  A transformer that processes parts of an image and then joins them can work more efficiently than one that looks at the entire image at once. However, to relate the parts to the whole, it must learn how the pixels in different regions relate to one another. A recent model called [Swin](https://arxiv.org/pdf/2103.14030.pdf?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--nlQXRW4-7X-ix91nIeK09eSC7HZEucHhs-tTrQrkj708vf7H2NG5TVZmAM8cfkhn20y50) does this by shifting region boundaries in between processing regions and merging them together — a step that nonetheless consumes compute cycles. Using convolutions to process both within and across regions can enable a model to learn such relationships without shifting region boundaries, saving that computation.  
**How it works:** The authors trained NesT to classify images in [ImageNet](https://www.image-net.org/?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--nlQXRW4-7X-ix91nIeK09eSC7HZEucHhs-tTrQrkj708vf7H2NG5TVZmAM8cfkhn20y50).

-   The authors divided input images into regions and partitioned each region into a grid. A transformer generated a representation of each grid square.
-   The model downsampled every block of four adjacent squares using a convolutional layer, combining the representations of each square into a representation of the block.
-   Then the model combined adjacent blocks and regenerated the representation until only one representation, representing the entire image, remained.

**Results:** A 38 million-parameter NesT achieved 83.3 accuracy on ImageNet. This performance matched that of an 88-million parameter Swin-B — a 57 percent saving in the compute budget.  
**Why it matters:** Transformers typically bog down when processing images. NesT could help vision applications take fuller advantage of the architecture’s strengths.  
**We’re thinking:** Computational efficiency for the Swin!

---
source : [deeplearning.ai](https://read.deeplearning.ai/the-batch/issue-113/)
