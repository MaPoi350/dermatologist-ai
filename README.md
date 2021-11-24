### Dermatoligist AI Project by Udacity
The objective is to create an algorithm for an app that classifies images of different types of skin anomalies and diagnoses Melanoma, the deadliest type of skin cancer. The algorithm shall distinguish between malignant skin tumor from two types of benign lesion (Nevus and Seborherric Keratoses). Google Colab was used as platform to run all codes and notebooks.

## Data
All images of Melanoma, Nevus and Seborherric Keratoses were provided within the  <a href="https://challenge.kitware.com/#challenge/583f126bcad3a51cc66c8d9a">2017 ISIC Challenge on Skin Lesion Analysis Towards Melanoma Detection</a>.
The provided data by Udacity was already seperated in <a href="https://s3-us-west-1.amazonaws.com/udacity-dlnfd/datasets/skin-cancer/train.zip">Training Data</a>,<a href="https://s3-us-west-1.amazonaws.com/udacity-dlnfd/datasets/skin-cancer/valid.zip">Validation Data</a>  and <a href="https://s3-us-west-1.amazonaws.com/udacity-dlnfd/datasets/skin-cancer/test.zip>Test Data</a>.

## Methods
  - A pretrained VGG16 model with an adapted 2 layer classifier and a 0,15 dropout function was used
  - Criterion: NLLLOSS
  - Optimizer: Adam
  - 5 Epochs were used
  
## Results
![alt text](https://github.com/MaPoi350/dermatologist-ai/blob/main/assets/ROC_Curvature.png) 
![alt text](https://github.com/MaPoi350/dermatologist-ai/blob/main/assets/Confusion_Matrix.png)

 
