# plant-pathology

This project was done as a part of Kaggle contest Plant Pathology 2020 - FGV C7.

## Overview

Crop diseases are a major threat to food security, but their rapid identification remains difficult in many parts of the world due to the lack of the necessary infrastructure. Misdiagnosis of the many diseases impacting agricultural crops can lead to misuse of chemicals leading to the emergence of resistant pathogen strains, increased input costs, and more outbreaks with significant economic loss and environmental impacts. Current disease diagnosis based on human scouting is time-consuming and expensive, and although computer-vision based models have the promise to increase efficiency, the great variance in symptoms due to age of infected tissues, genetic variations, and light conditions within trees decreases the accuracy of detection.

![Overview](https://github.com/rohitpatwa/plant-pathology/blob/main/media/leaves.png)

## Dataset

We used the dataset given in the Plant Pathology 2020 - FGVC7 contest on Kaggle. It is an image classification problem where each image can be classified into one of 4 categories (healthy, multiple_diseases, rust, scab). The training data has 1821 labeled images of plant leaves. Each image is an RGB image of size 2048*1365 containing one or more leaves.

By plotting the images and their rgb distribution, we came to know that the green parts of the image have low blue values, but by contrast, the brown parts have high blue values. This suggests that green (healthy) parts of the imagees have low blue values, whereas unhealthy parts are more likely to have high blue values. This might suggest that the blue channel may have a correlation with the occureence of diseases in plants.

![Overview](https://github.com/rohitpatwa/plant-pathology/blob/main/media/rgb_distribution.png)

## Model Training

We trained 2 linear models (Logistic regression and SVM) and 2 non-linear models (EfficientNet-B5 and ResNet18) on this dataset and compared their performances.

#### EfficientNet

EfficientNet is another popular (more recent) CNN-based ImageNet model which achieved the SOTA on several image-based tasks in 2019. EfficientNet performs model scaling in an innovative way to achieve excellent accuracy with significantly fewer parameters. It achieves the same if not greater accuracy than the previous model with a much shallower architecture.

There are three scaling dimensions of a CNN: depth, width, and resolution. **Depth** simply means how deep the network is which is equivalent to the number of layers in it. **Width** simply means how wide the network is. One measure of width, for example, is the number of channels in a Conv layer. **Resolution** is simply the image resolution that is being passed to a CNN. The figure below will give you a clear idea of what scaling means across different dimensions.

![Overview](https://github.com/rohitpatwa/plant-pathology/blob/main/media/efficientnet.png)

## Results

As expected, EfficientNet-B5 gave the highest precision, recall and F1 score for all classes.

![Overview](https://github.com/rohitpatwa/plant-pathology/blob/main/media/performance_comparision.png)

![Overview](https://github.com/rohitpatwa/plant-pathology/blob/main/media/accuracy_plot.png)

## Authors

* **Rohit Patwa** [\[LinkedIn\]](https://www.linkedin.com/in/rohitpatwa/)
* **Kunjan Khatri** [\[LinkedIn\]](https://www.linkedin.com/in/kunjan-khatri/)

## References

* **Plant Disease Classification Using Image Segmentation and SVM Techniques**  
[https://www.ripublication.com/ijcir17/ijcirv13n7_23.pdf](https://www.ripublication.com/ijcir17/ijcirv13n7_23.pdf)

* **EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks**  
[https://medium.com/@nainaakash012/efficientnet-rethinking-model-scaling-for-convolutional-neural-networks-92941c5bfb95](https://medium.com/@nainaakash012/efficientnet-rethinking-model-scaling-for-convolutional-neural-networks-92941c5bfb95)