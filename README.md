# AR2IL
Code repository of the AR2IL lab

## Content
1. [2D Neural Style Transfer](#neuralstyle)
2. [Tree-GAN](#treegan)

<a name="neuralstyle"></a>
## Neural Style Transfer
Neural style transfer is an optimization technique used to take two images—a content image and a style reference image (such as an artwork by a famous painter)—and blend them together so the output image looks like the content image, but “painted” in the style of the style reference image. 

This technique is outlined in <a href="https://arxiv.org/abs/1508.06576" class="external">A Neural Algorithm of Artistic Style</a> (Gatys et al.).

This is implemented by optimizing the output image to match the content statistics of the content image and the style statistics of the style reference image. 

In this notebook, deep learning is used to create a new image version of the primary image (content image) while using the style of the secondary image (style image).
