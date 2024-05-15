A basic GAN example for generation Fashion images.
GAN - Generative Adversarial Network
It consists of Generators which generate fake images which look like real images and Discriminator which try to differentiate between real and fake images.

1. Data Processing
   Data is loaded and processed in these steps :\
   a. Map - to map images for scaling \
    b. Cache - caching for improving trianing speed\
    c. Shuffle - shufflingto avoid learning patterns in a specific order\
    d. Batch - groups into batches of 128\
    e. Prefetch - fetches next 128 images.

2. Generator Bulding
   It uses sequential model for training\
   a. Dense Layer with ReLU and Reshape to convert 128 random inputs to 7*7*128 shape\
   b. Upsampling blocks to double the size of output layer and then Conv Layer to get parameters\
   c. Downsampling blocks with Conv and ReLU\

3. Discriminator Building
