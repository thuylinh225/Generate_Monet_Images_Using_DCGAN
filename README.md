# Generate_Monet_Images_Using_DCGAN

## 1.1 Problem

A generative adversarial network (GAN) is a generative model that defines an adversarial net framework and is composed of two CNN models, namely a generator and a discriminator, with the goal of generating new realistic images when given a set of training images. These two models act as adversaries of each other: the generator learns to generate new fake images that look like real images (starting with random noise) while the discriminator learns to determine whether a sample image is a real or a fake image. The two models are trained together in a zero-sum game, adversarially, and overtime, the generator gets better at generating images that are super close to real images and discriminator gets better at differentiating them. The process reaches equilibrium when the discriminator can no longer distinguish real images from fakes.  

![image](https://user-images.githubusercontent.com/63614659/220342049-46593e0a-c03f-48ba-ac77-07aa123252a1.png)

In this project, we will build and train a Deep Convolutional Generative Adversarial Network (DCGAN) with Keras to generate images of Monet-style.    

DCGAN is a type of GAN that uses convolutional neural networks (CNNs) as the generator and discriminator. CNNs are specifically designed for image recognition tasks and are well-suited for generating images using GANs. DCGAN includes several architectural changes compared to a regular GAN. It uses transposed convolutional layers for the generator instead of fully connected layers, and replaces pooling layers with strided convolutions. It also uses batch normalization to stabilize the training process and prevents the generator from collapsing.  

![image](https://user-images.githubusercontent.com/63614659/220342224-ddcaabb8-72e3-496c-83ef-f375dc152422.png)

As we can see, the Discriminator model is just a Convolutional classification model. In contrast, the Generator model is more complex as it learns to convert latent inputs into an actual image with the help of Transposed and regular Convolutions. In summary, while both GAN and DCGAN are used for generating new data, DCGAN specifically uses convolutional neural networks as the generator and discriminator, and includes several architectural changes to improve the stability and quality of generated data.  

There are 4 major steps in the training:     
1. Build the generator.       
2. Build the discriminator.      
3. Define Loss Functions & Optimizers.    
4. Define the training loop & Visualize Images.   

## 1.2 Data

In this project, I use a dataset from Kaggle, was downloaded from the link:     
https://www.kaggle.com/competitions/gan-getting-started/data 
  
The dataset contains four directories: monet_tfrec, photo_tfrec, monet_jpg, and photo_jpg. The monet_tfrec and monet_jpg directories contain the same painting images, and the photo_tfrec and photo_jpg   directories contain the same photos.    

The monet directories contain Monet paintings. We will use these images to train our model.   

The photo directories contain photos. We will add Monet-style to these images and submit our generated jpeg images as a zip file.  

Files   
monet_jpg - 300 Monet paintings sized 256x256 in JPEG format     
monet_tfrec - 300 Monet paintings sized 256x256 in TFRecord format     
photo_jpg - 7028 photos sized 256x256 in JPEG format     
photo_tfrec - 7028 photos sized 256x256 in TFRecord format    


Reference Sources:       
https://www.kaggle.com/code/amyjang/monet-cyclegan-tutorial/notebook      
https://www.tensorflow.org/tutorials/generative/dcgan
