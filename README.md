# Novel-StyleGAN-Inversion-Papers
Share some intersting paper about StyleGAN, especially StyleGAN Inversion.

**The ultimate goal** is to revise my paper [Collaborative Learning for Faster StyleGAN Embedding](https://arxiv.org/pdf/2007.01758.pdf), and then release the code.

* Why I need to revise my paper?
  I think I should hack into the details of GAN Inversion, such as the influence of interpolating (due to the different size of input and output images), the design of the encoder... What's more, I found there is no standard split to evaluate the inversion effect.

-----
## The pioneer in StyleGAN Inversion.
1. [Image2StyleGAN: How to Embed Images Into the StyleGAN Latent Space?](https://arxiv.org/pdf/1904.03189.pdf)
2. StyleGAN Encoder. [[code1](https://github.com/Puzer/stylegan-encoder)] [[code2](https://github.com/pbaylies/stylegan-encoder)]
3. [Image2StyleGAN++: How to Edit the Embedded Images?](https://arxiv.org/pdf/1911.11544.pdf)

Image2StyleGAN is the first paper in StyleGAN inversion. In this work, they conducted some interesting experiments which is meaningful to the future works. StyleGAN Encoder is another pioneer work, which takes the results of a nerual network as initial point of the next optimization produre. StyleGAN Encoder has two representative repos, in which `code1` is ealier and `code2` has better inversion effect. Image2StyleGAN++ was expanded to optimize both latent vector and the noise maps.

### TODO
- [x] Reproduce [Image2StyleGAN](https://github.com/syguan96/Image2StyleGAN)  
- [ ] Reproduce Image2StyleGAN++. 
  - I won't reimplement Image2StyleGAN++ right now.

-----
## A comprehensive survey
1. [GAN Inversion: A Survey](https://arxiv.org/pdf/2101.05278.pdf). [github](https://github.com/weihaox/awesome-gan-inversion)
  This paper comprehensively reviewed current papers of StyleGAN inversion.
  
## How to design the encoder? These papers give their solutions.
1. [Designing an Encoder for StyleGAN Image Manipulation](https://arxiv.org/pdf/2102.02766.pdf).
2. [Encoding in style: a stylegan encoder for image-to-image translation](https://arxiv.org/pdf/2008.00951.pdf).
3. [ReStyle: A Residual-Based StyleGAN Encoder via Iterative Refinement](https://arxiv.org/pdf/2104.02699.pdf).
    - ReStyle slacks the one-step forward pass to multi-step learning. This idea makes sense, which somewhat shares same spirt with [my paper]((https://arxiv.org/pdf/2007.01758.pdf)). My question is whether the Fig.6 can indicates general phenomenon.

## How to constraint the gan inversion?
1. [Exploiting Deep Generative Prior for Versatile Image Restoration and Manipulation.](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123470256.pdf)[[github](https://github.com/XingangPan/deep-generative-prior)]
    - The discriminator-based constraint and progressively training policy are interesting.
2. [LOHO: Latent Optimization of Hairstyles via Orthogonalization](https://arxiv.org/pdf/2103.03891.pdf)
    - how to design constraints on hair? this paper gives an answer.
  
## Application
1. [In&Out : Diverse Image Outpainting via GAN Inversion](https://arxiv.org/pdf/2104.00675.pdf)
    - Outpainting is an interesting application by patch-based inversion.
    - The prior loss part again point out how to ensure the inversed latent code staying in the gan domain.
2. [Exploiting Spatial Dimensions of Latent in GAN for Real-time Image Editing.](https://arxiv.org/pdf/2104.14754.pdf) [[github](https://github.com/naver-ai/StyleMapGAN)]
    - First training an encoder to inverse images. Then combine the guidence image and the source image in the feature-level to realize local editting effect.
3. [InfinityGAN: Towards Infinite-Resolution Image Synthesis](https://arxiv.org/pdf/2104.03963.pdf)
    - novel work. **deserve to be read once more.**


### 3D application
1. [DO 2D GANS KNOW 3D SHAPE? UNSUPERVISED 3D SHAPE RECONSTRUCTION FROM 2D IMAGE GANS.](https://arxiv.org/pdf/2011.00844.pdf). [[github](https://github.com/XingangPan/GAN2Shape)]
    - A fancy pipline in which takes gan inversion to reduce the artifacts of hand-crafted images, so that enabling training decompositional network.
    - They use discriminator's feature and l2 regularization term to constraint gan inversion step. Particularly, the form of l2 regularization is noticable.
    - They also realized that gan inversion cannot preserve all semantics of the original instance.

## Tools
1. Learning Continuous Image Representation With Local Implicit Image Function. Nice work.


