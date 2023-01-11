# Glaucoma retinal analysis

![eye-test](https://user-images.githubusercontent.com/81832365/211692403-e8f9ce9b-5b55-485f-8c6d-938da231ef97.jpg)

## Intro

In this work, I use a dataset of retinal fundus pictures to identify whether glaucoma, a condition that can result in vision loss, is present in the patient's eye. The dataset used is available [here](https://www.kaggle.com/datasets/jordidelatorreuoc/practica-dl-uoc-2022).

## Strategy

I have used a two-phased approach to analyze the data: in the first phase, I have tested different neural networks to see which one works best, and in the second phase I have used a cross-validation to try to minimize false negatives. In this context, it is crucial to get that number as low as it is possible, since any patient with glaucoma can see their lives seriously impacted if the condition is left unchecked. 

## Neural networks used

In the first phase of the project, 3 different configurations of the EfficientNetB0 model, along with an implementation of VGG16 and a ResNet50 one. These are all Convolutional Neural Networks (CNNs), as it makes sense to use this technollogy in image recognition problems.

The second phase of it consists of a cross-validation of one of the EfficientNetB0 models, as it has yielded the best metrics. 

## Results

Model 3 has given the best f1-score, as it can be seen in the picture.

![scores](https://user-images.githubusercontent.com/81832365/211693143-f1b85810-4aea-4a6c-801c-610aa13ff67e.png)

It also shows a solid performance regarding all other scores, more consistently than the others.

![conf_mat](https://user-images.githubusercontent.com/81832365/211693731-70638f8e-2603-4638-8ae1-a70d8dc83e59.png)

Looking at the confusion matrix, we can see how there can some concerns related to the f1-score. 9 patients are diagnosed healthy and have glaucomas, which would be inacceptable in a real-life situation. Therefore, in any hypothetical future phase it would be desirable to lower this number. Let's keep in mind that the f1 metric stresses the importance of false negatives, and the lower it is, the better it performs with them. However, this is a good starting point, since the model gives less false negatives than the others.

The cross validation section [----]

## Conclusions

There is always a tradeoff between accuracy and reducing false negatives, and perhaps if the number of FNs were lower, the overall performance would be impacted. Therefore, this contradiction must be navigated and it is necessary to tread very finely in order to get the optimal model. 


## Bibliography
[1] https://datascience.stackexchange.com/questions/48246/how-to-compute-f1-in-tensorflow
