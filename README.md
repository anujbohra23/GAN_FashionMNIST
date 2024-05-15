A basic GAN example for generation Fashion images.
GAN - Generative Adversarial Network
It consists of Generators which generate fake images which look like real images and Discriminator which try to differentiate between real and fake images.

1. Data Processing
   Data is loaded and processed in these steps :
   a. Map - to map images for scaling \
    b. Cache - caching for improving trianing speed\
    c. Shuffle - shufflingto avoid learning patterns in a specific order\
    d. Batch - groups into batches of 128\
    e. Prefetch - fetches next 128 images.\
2. Generator Bulding
