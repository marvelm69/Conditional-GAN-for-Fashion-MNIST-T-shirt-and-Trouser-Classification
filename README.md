![image](https://github.com/user-attachments/assets/947d14f1-1d33-49d2-b9ea-8d5d1b1cb29c)# Conditional GAN for Fashion MNIST: T-shirt and Trouser Classification

## Overview

This project utilizes a **Conditional Generative Adversarial Network (cGAN)** to generate realistic images of **T-shirts/tops (class 0)** and **Trousers (class 1)** from the **Fashion MNIST** dataset. The key components are a **Generator** that generates images from random noise and a **Discriminator** that distinguishes between real and generated images. The model is trained to enhance the Generator's ability to create images that are indistinguishable from real ones.

## Goals

The main goals of this project include:

- **Image Generation**: Generate realistic images of T-shirts and trousers using a Conditional GAN.
- **Adversarial Training**: Implement a competitive process between the Generator and Discriminator to improve the quality of generated images over time.
- **Model Evaluation**: Measure the quality of generated images using the **Fréchet Inception Distance (FID)**, a standard metric for generative models.

## Theoretical Approach

### 1. **Components of cGAN**:
   - **Generator (G)**: Takes random noise as input and generates an image that mimics the real images from the dataset.
   - **Discriminator (D)**: Evaluates both real images from the dataset and generated images from the Generator, distinguishing between the two.

### 2. **Process Flow**:
   - **Noise Input**: The Generator starts by taking random noise vectors and outputs synthetic images.
   - **Discriminator Input**: The Discriminator takes both real and fake images, and classifies them as either real or fake.
   - **Adversarial Learning**: The two models are trained in opposition, where the Generator tries to fool the Discriminator, and the Discriminator tries to accurately classify images as real or fake.

### 3. **Training Process**:
   - **Generator Training**: The Generator's objective is to maximize the Discriminator's classification error for generated images.
   - **Discriminator Training**: The Discriminator learns to differentiate between real and generated images, with the goal of minimizing classification errors.
   - The training alternates between these two objectives, iteratively improving the Generator's image quality and the Discriminator's classification skills.

## Results Summary

The model was trained for **50 epochs** on the Fashion MNIST dataset. The Generator and Discriminator losses were recorded at each step, with the Generator gradually improving its image creation ability.

- **Discriminator Loss**: Initially, the Discriminator performed well, distinguishing real from fake images. As the Generator improved, the Discriminator's task became more challenging, but it continued to refine its classification ability.
- **Generator Loss**: Over time, the Generator's loss decreased as it became better at fooling the Discriminator, creating more realistic images.
![image](https://github.com/user-attachments/assets/2819167e-faeb-4c7b-afb2-3c5f7932c83a)

### **Fréchet Inception Distance (FID)**

The model's performance was evaluated using the **Fréchet Inception Distance (FID)**, a metric that measures the similarity between real and generated images. A lower FID score indicates better performance. The manually calculated FID score was **4.98e+44**, while the FID score using an inception model adjusted for grayscale images yielded **2.25e+110**.

## Conclusion

The project successfully demonstrates the effectiveness of **Conditional GANs** in generating realistic images of T-shirts and trousers from the Fashion MNIST dataset. The results suggest that the Generator improved steadily during training, although some challenges remain in creating consistently indistinguishable images.

Future work could focus on:
- Enhancing the model architecture to further reduce the FID score.
- Training for more epochs to allow the Generator to refine its outputs.
- Exploring alternative GAN architectures or loss functions to improve performance.


