# GA-Capstone-Project

## Image Classifier for Tropical Flower Presentation

In this project, I took inspiration from all the plant identification phone apps on the market (in particular Pl@ntNet) and tried to build a classifier of my own, particualrly tailored toward tropical flora.

In my personal experience with these plant identifcation apps, I found them to be  quite inaccurate when used on plants in Singapore. While it is understandable, considering how many species of plants not just locally but worldwide, I was

Although Pl@ntNet has a robust dataset, I was looking exclusively for popular local plants. To this end, I made use of NParks publication "1001 Garden Plants in Singapore" to identify the top 253 most popular plant species in Singapore. From there, I employed the Selenium Webdriver to automate the image scraping process from Google Images, pulling 100 images for each species.

Although this technically should have supplied me with 25300 images over 253 classes, many of the images turned out to be inappropriate for feeding into my CNN. As a result, a lot of the images had to be manually removed, with some classes shrinking to less than 50% of their original size.
Ultimately, I elected to use 2579 images over 50 of the more popular plant species.

I initially trained a basic CNN on the dataset to set benchmark top-1 and top-5 accuracies of 0.31 and 0.56 respectively. Following that I trained four pre-trained models (VGG-19, InceptionV3, MobileNetV2, EfficientNetB3) before settling on using MobileNetV2 as my final model to tune due to it having relatively good top-1 and top-5 accuracies (0.61 and 0.84), but more so due to the size and low computational requirements.

Using data augmentation, I managed to achieve a final MobileNetV2 model with top-1 and top-5 accuracies of 66.5% and 87.7%. There was also another MobileNetV2 model that showed promise using data augmentation, fully trainable layers, and regularisation. Model did not seem to be properly fit yet, so with more epochs, it could have out performed our data augmentation model.
