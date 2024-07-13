# GAN
Generative Adversarial Networks (GANs) are a type of machine learning framework composed of two neural networks: a generator and a discriminator. The generator creates synthetic data, while the discriminator evaluates its authenticity. This adversarial process helps the generator improve its data generation capabilities over time. GANs are highly effective in producing high-quality, realistic outputs, making them useful in various applications, including image generation, data augmentation, and style transfer. They are particularly valuable in situations where collecting real-world data is difficult or costly, as they can generate diverse datasets for training other models. By simulating real data, GANs enable advancements in fields such as computer vision, natural language processing, and creative industries, providing innovative solutions to complex problems.

## Project Overview
The CelebFaces Attributes (CelebA) Dataset consists of images and 40 facial attribute labels. This code implements a Conditional Wasserstein GAN (cWGAN) to generate synthetic facial images based on these attributes.

##### Feature Array
features = ['5_o_Clock_Shadow', 'Arched_Eyebrows', 'Attractive', 'Bags_Under_Eyes',
            'Bald', 'Bangs', 'Big_Lips', 'Big_Nose', 'Black_Hair', 'Blond_Hair',
            'Blurry', 'Brown_Hair', 'Bushy_Eyebrows', 'Chubby', 'Double_Chin',
            'Eyeglasses', 'Goatee', 'Gray_Hair', 'Heavy_Makeup', 'High_Cheekbones',
            'Male', 'Mouth_Slightly_Open', 'Mustache', 'Narrow_Eyes', 'No_Beard',
            'Oval_Face', 'Pale_Skin', 'Pointy_Nose', 'Receding_Hairline',
            'Rosy_Cheeks', 'Sideburns', 'Smiling', 'Straight_Hair', 'Wavy_Hair',
            'Wearing_Earrings', 'Wearing_Hat', 'Wearing_Lipstick',
            'Wearing_Necklace', 'Wearing_Necktie', 'Young']

### Code Details
#### 1. Critic Model:

Defines the architecture for the critic (discriminator) model.
Takes an input image and a label as inputs.
Utilizes Conv2D, LeakyReLU activation, and Dropout layers for processing.
Outputs a single value indicating real or fake image.
Displays the critic model summary.
### 2. Generator Model:

Defines the architecture for the generator model.
Takes noise vector (latent space) and a label as inputs.
Uses Conv2DTranspose, BatchNormalization, and LeakyReLU layers to generate images.
Outputs synthetic images matching input dimensions.
Displays the generator model summary.
### 3. ConditionalWGAN Class:

Custom model combining critic and generator.
Methods for compiling, gradient penalty calculation, and train_step method for training.
Critic trained for multiple steps (critic_steps).
Generator trained to deceive critic.
Tracks critic and generator losses during training.
### 4. Training Setup:

Instance of ConditionalWGAN with critic, generator, latent dimension, critic steps, and gradient penalty.
cWGAN compiled with Adam optimizers for critic and generator.

## Conclusion
This cWGAN project leverages TensorFlow and Keras to create synthetic facial images from the CelebA dataset based on given facial attribute labels. The critic distinguishes real from synthetic images, while the generator learns to produce realistic facial images conditioned on specified attributes.


