# Addressing-Class-Imbalance-in-Stroke-Prediction-using-Machine-Learning
Author - Anurag Tendulkar <br>
email - anurag.mtendulkar@gmail.com

### Details of the project are in the methods and results pdf. Below is just a short summary of the project.

## Goal
The project aims to build a predictive model that identifies patients at risk of having a stroke from given features. To reduce the number of strokes in the population we want to assign health coaches to individuals having higher risk of having strokes. Thus the model should correctly identify individuals at risk and make less misclassifications at the same time

## Dataset Description
The dataset is highly imbalanced where the ratio of minority class (population having strokes) to majority class (population not having strokes) is 1: 54.
The dataset includes categorical features and columns with missing values, which need to be cleaned and pre-processed. Additionally, there are features with binary data, as well as numeric data that requires standardization. <br>
Shape of dataset - (43,400, 15) <br>
The training data had to be resampled to address the class imbalance. Oversampling using smote and undersampling using tomek links was used.


## Models and Results
Accuracy is not the best metric when it comes to imbalanced data because a naive classifier (which predicts all samples as majority class) can have a high accuracy but 0 precision and recall.<br>
Precision and Recall are both important for us as we must assign a reasonable number of health coaches while correctly identifying patients at risk.
Confusion matrix helps us understand our needs the best as seen below.

## Logistic Regression
Confusion Matrix
<br><br>![image](https://user-images.githubusercontent.com/74342035/233461818-9ece1a74-74f4-4970-b88f-920fbea4852b.png)
<br>Metrics<br>![image](https://user-images.githubusercontent.com/74342035/233462207-952bcf23-7d0b-4f15-bd42-927f56e9cd33.png)
<br><br>

## Random Forest
Confusion Matrix
<br><br>![image](https://user-images.githubusercontent.com/74342035/233463093-0961758b-2d90-4d50-b925-f13a0367384b.png)
<br>Metrics<br>![image](https://user-images.githubusercontent.com/74342035/233462920-e61c5134-37ef-4423-9e34-3fefb5843920.png)
<br><br>

## Isolation Forest
Confusion Matrix
<br><br>![image](https://user-images.githubusercontent.com/74342035/233463232-e70f4afe-0673-4570-a7ca-d18e10b27edd.png)
<br>Metrics<br>![image](https://user-images.githubusercontent.com/74342035/233463291-adc10a15-75e7-4080-952a-aa35d71de6b7.png)
<br><br>

## Challenges Faced and Future Work
### Precision Recall Trade-off
This was the problem I faced while testing out different models. Each algorithm trades one for the other (Eg : SMOTE increases recall at the cost of precision). I would like to understand more about this topic to handle imbalanced datasets better.
### New Algorithms
I would like to explore and research other algorithms which build upon a different hypothesis. This may improve the poor performance of the current classifiers. E.g., One Class classification is used for identifying outliers, but it can be modified to handle imbalanced datasets. It does not require resampling unlike most of the supervised algorithms.
