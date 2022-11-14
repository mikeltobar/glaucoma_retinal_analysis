# Glaucoma retinal analysis

A deep learning approach to glaucoma detection.

## Intro

In this work, I use a dataset of retinal fundus pictures to identify whether glaucoma, a condition that can result in vision loss, is present in the patient's eye. The dataset used is available [here](https://www.kaggle.com/datasets/jordidelatorreuoc/practica-dl-uoc-2022).

## Strategy

I have used a two-phased approach to analyze the data: in the first one, I have tested different neural networks to see which one works best, and in the second one I have used a cross-validation to try to minimize false negatives. In this context, it is crucial to get that number as low as it is possible, since any patient with glaucoma can see their lives seriously impacted if the condition is left unchecked. 

## Neural networks used

In the first phase of the project, 3 different configurations of the EfficientNet B0 model, along with an implementation of VGG16 and a ResNet50 one. These are all Convolutional Neural Networks (CNNs), as it makes sense to use this technollogy in image recognition problems.

The second phase of it consists of a cross-validation of one of the EfficientNet B0 models, as it has yielded the best metrics. 

## Results

The performance of the models, especially when measured with the f1-score, is quite good. However, there are some concerns related to the f1-score, and in a hypothetical future phase it would be desirable to lower it.

## Conclusions

There is always a tradeoff between accuracy and reducing false negatives, and perhaps if the number of FNs were lower, the overall performance would be impacted. Therefore, this contradiction must be navigated and it is necessary to tread very finely in order to get the optimal model. 
