# Machine Learning Analysis on Cancer Dataset to Predict Tumor Malignancy

----

## Goal

Given a dataset on cancer diagnoses, use 2 machine learning algorithms to classify the tumor types as malignant or benign, and compare the performance of the two models. Also compare prediction accuracies for models trained directly on the data's attributes or trained on the first two principal components. 

---- 

## Attribute Selection 

Identify useful pairs of attributes for predicting the target variable (malignancy) using seaborn's pairplot. 

<img width="603" alt="Screenshot 2023-12-31 at 3 38 05 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/9b2603a0-6d64-4ba5-bd61-90bd585bd57f">

The atrributes I will use to train the algorithms are 'mean concave points' and 'worst perimeter'.

----

## Split data into training and testing sets 

<img width="558" alt="Screenshot 2023-12-31 at 3 39 19 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/8b1271d5-72f7-4b07-a968-02843ee9250e">

----

## Machine learning on two attributes of choice

### Algorithm #1: Nearest Neighbors

<img width="528" alt="Screenshot 2023-12-31 at 3 40 31 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/1a785310-4864-4ac9-8577-5eb4fedfd1f2">

<img width="437" alt="Screenshot 2023-12-31 at 3 40 58 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/2f42df54-4e8b-402e-8e0c-6ce8ef979162">

The KNN algorithm trained on the two attributes of interest has a 92% accuracy. We can tell from the plot that the classification is mostly accurate, with some incorrect predictions along the boundary between clusters.

### Algorithm #2: Naive Bayes

<img width="594" alt="Screenshot 2023-12-31 at 3 42 10 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/7a150240-1519-4cf5-b28b-27b27fffa213">

<img width="437" alt="Screenshot 2023-12-31 at 3 42 25 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/4be65c3f-3888-4278-8da2-0541e5c340a6">

The Naive Bayes classification trained on the two attributes of interest has a 93% accuracy. This model performed slightly better on points along the boundary.

----

## Principal Component Analysis (PCA)

<img width="643" alt="Screenshot 2023-12-31 at 3 43 18 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/e7ed899c-6c89-4154-9e3e-5ef91d9ac26c">

<img width="608" alt="Screenshot 2023-12-31 at 3 43 45 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/1a8bcc9d-5afe-4064-b738-c86f56bbf409">

### Algorithm #1: Nearest Neighbors on PCA Data 

<img width="608" alt="Screenshot 2023-12-31 at 3 44 42 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/0d7a747f-4d8d-4f75-b98c-7d233027e5a8">

<img width="434" alt="Screenshot 2023-12-31 at 3 44 54 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/502a0f49-21ef-45a6-bbfb-28361978dadc">

The Nearest Neighbors algorithm trained on the PCA data has a 93% accuracy, which is 1 percent higher than the accuracy of the KNN model trained on just the two correlated attributes. This indicates that higher-accuracy models can be made by performing PCA on the whole dataset.

### Algorithm #2: Naive Bayes on PCA Data 

<img width="588" alt="Screenshot 2023-12-31 at 3 45 58 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/35c91b30-9d93-40e9-8e21-5e514f4c7b90">

<img width="436" alt="Screenshot 2023-12-31 at 3 46 15 PM" src="https://github.com/catherinealeal/TumorMalignancy/assets/100166102/cf5229c0-edf8-45cf-9e65-bbbf43403420">

The Naive Bayes algorithm trained on the PCA data produced the highest accuracy model at 94%. Overall, the Naive Bayes models performed better than the KNN models, and training on the PCA data further increases their accuracies.

-----

## Conclusion: I would recommend the use of the Naive Bayes algorithm trained on PCA data as the automated screening algorithm for cancer detection.

- KNN trained on two attributes: 92% accuracy
- Naive Bayes trained on two attributes: 93% accuracy
- KNN trained on PCA data: 93% accuracy
- Naive Bayes trained on PCA data: 94% accuracy
