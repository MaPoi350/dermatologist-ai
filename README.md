### Dermatoligist AI Project by ISIC
The objective is to create an algorithm for an app that classifies images of different types of skin anomalies and diagnoses Melanoma, the deadliest type of skin cancer. The algorithm shall distinguish between malignant skin tumor from two types of benign lesion (Nevus and Seborherric Keratoses). Google Colab was used as platform to run all codes and notebooks.

## Data
All images of Melanoma, Nevus and Seborherric Keratoses were provided within the  <a href="https://challenge.kitware.com/#challenge/583f126bcad3a51cc66c8d9a">2017 ISIC Challenge on Skin Lesion Analysis Towards Melanoma Detection</a>.
The provided data by ISIC and Udacity was already seperated in <a href="https://s3-us-west-1.amazonaws.com/udacity-dlnfd/datasets/skin-cancer/train.zip">Training Data</a>,<a href="https://s3-us-west-1.amazonaws.com/udacity-dlnfd/datasets/skin-cancer/valid.zip">Validation Data</a>  and <a href="https://s3-us-west-1.amazonaws.com/udacity-dlnfd/datasets/skin-cancer/test.zip>Test Data</a>.

## Methods and Variables of the classifier
  - A pretrained VGG16 model with an adapted 2 layer classifier and a 0,15 dropout function was used
  - Criterion: NLLLOSS
  - Optimizer: Adam
  - 5 Epochs were used
  - A learning rate of 0.0001 was used for the training
  
## Results
The scores of the 3 categories are:
  
Category 1 Score: 0.730
  
Category 2 Score: 0.825
  
Category 3 Score: 0.778
  
In Task 1 (Category 1) the ROC curve describes the ability of the model to distinguish between malignant melanoma and the benign skin lesions (nevus, seborrheic keratosis). In Task 2 (Category 2)  the ROC curves measures the ability of the model to distinguish between melanocytic and keratinocytic skin lesions. Category describes the average of Category 1 and 2.
  
The ROC curve describes the accuracy of the trained model:
  
![alt text](https://github.com/MaPoi350/dermatologist-ai/blob/main/assets/ROC_Curvature.png) 
  
The Confusion Matrix describes the probablities of False/True Positives and False/True Negatives:
  
![alt text](https://github.com/MaPoi350/dermatologist-ai/blob/main/assets/Confusion_Matrix.png)
  
## Conclusion:

An average result of 0,778 is better than expected with only 5 Epochs. Nevertheless, the weak part of this result is the high false negative result of 0,68 (as documented in the confusion matrix). This results in the fact that people with a malignant melanom are classified as healthy, with the consequence, that they wouldn't go to the doctor and in the worst case die.

A better classifier should minimize the false negative results, even if the false positive results increase. A healthy patient, which is diagnosed with melanoma, goes to the doctor and will be then diagnosed as healthy. This results only in wasted time and is preferred than the false negative result.

One way to reduce the false negative probability is a better classifier, with another network, a higher epoch rate or another criterion/optimizer. Another way is a decrease of the estimated result threshold, when a  melanom is classified (e.g. a decrease from min 0,5 to min 0,4 or min 0,3).
  
Another reason is the data quality. Many training images are polluted by markers or other parts not related to Skin_Cancer, which should be removed. And the Nevus images in the training folder are 3,5 times higher than the melanoma images. This explains, why we have a high benign rate in the confusion matrix. The training data should be better balanced.  

Last but not least, additional data could be taken into account like age or sex.

The influence of different variables to improve the classifier shall be further investigated within this project.


 
