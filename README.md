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
   c. Downsampling blocks with Conv and ReLU

3. Discriminator Building
   It has similar steps like generator without upsampling but with dropout to get regularisation and making it difficult for discriminator to learn

4. Discriminator Training
   Using Adam as the Optimiser and BinaryCrossentropy as the loss \
   a. Getting real images and generating some fake images with generator\
   b. Creates GradientTape to track gradients for backpropogation\
   c. It feeds real and fake images to discriminator and creates labels for real ones as 1 and fake ones as 0\
   d. Adds noise for robustness\
   e. Calculates Total Loss

5. Generator Training
   Similar steps to traiing the discriminator but the differentiator is that it creates labels for the generated images as all ones, tricking the discriminator into believing they're real (predicted_labels).

6. Saving the model and images
   a. Saves the model in .h5 file\
   b. Saves the generated images in images folder

High GPU power is required to generate the images.
