## Overview of the Analysis

### Purpose of the Analysis
The aim of this analysis is to construct and test machine learning models for the purpose of evaluating the creditworthiness of borrowers. The goal of this project is to utilize past lending data obtained from a peer-to-peer lending services organization to attempt to construct prediction models that have the ability for identifying loans that possess a significant likelihood of default.

### Financial Data
The dataset utilized in this analysis comprises historical data on lending activities, encompassing details pertaining to borrowers and the outcomes of loans. Our primary focus is on the "loan_status" column, which denotes the health of a loan. A value of 0 signifies a loan that is in healthy loan, while a value of 1 suggests a loan that carries a significant risk of default or high risk loan.

### Variables of Interest
In our analysis, we are primarily interested in predicting the credit risk of loans. The key variables in the dataset includes:
- **Features (x)**: Various attributes from the dataset, such as borrower information, loan details, and financial indicators.
- **Labels (y)**: The "loan_status" column, where 0 represents healthy loans, and 1 represents high-risk loans.

### Machine Learning Process
Our analysis involved the following stages:
1. Data Preprocessing: Reading and preparing the data, including splitting it into training and testing sets.
2. Model Building: Training logistic regression models using the training data.
3. Model Evaluation: Assessing model performance through metrics like accuracy, precision, and recall.
4. Reporting: Summarizing and communicating the results of our analysis for categorizing the loans as high risks or low risk.

### Methods Used
Logistic regression was applied on the dataset, This is a commonly used classification algorithm, to model the credit risk. In addition, resampling techniques was used to address potential class imbalance issues in the dataset.

## Results

### Machine Learning Model 1: Logistic Regression with Original Data
**Accuracy**: Model 1 achieved a high accuracy score of approximately 95.2%, indicating that it performs well in classifying both healthy (0) and high-risk (1) loans.

**Precision and Recall**: The logistic regression model predicts a healthy loan (0) with 1.00 precision and 1.00 recall. The precision for high-risk loans (1) is 0.85, which indicates that when the model predicts a loan as high-risk, its prediction is correct 85% of the time. The recall for high-risk loans is 0.91, which implies that the model correctly identifies 91% of all high-risk loans in the dataset.

**Confusion Matrix**: The confusion matrix reveals that the model correctly predicted most of the healthy loans (true negatives: 18663) but had some false negatives (56). It also identified many true positives (563) for high-risk loans but had some false positives (102).

### Machine Learning Model 2: Logistic Regression with Resampled Training Data
**Accuracy**: Model 2, trained with oversampled data, achieved a significantly higher accuracy score of approximately 99.4%. This suggests that the oversampling technique improved the model's overall performance.

**Precision and Recall**: The logistic regression model predicts a healthy loan (0) with 1.00 precision and 1.00 recall.The precision for high-risk loans (1) came sligthly down at 0.84 from 0.85, indicating a consistent ability to correctly classify 84% times correctly high-risk loans. However, the recall for high-risk loans increased to 0.99, indicating that the model now correctly identifies 99% time correctly all high-risk loans in the dataset. This is a significant improvement from Model 1.

**Confusion Matrix**: The confusion matrix for Model 2 shows that it correctly predicted almost all healthy loans (true negatives: 18649) and correctly identified all high-risk loans (true positives: 615). There were only a few false negatives (4) and false positives (116).

## Summary

Model Comparison: Model 2, which was trained with resampled data using the RandomOverSampler, outperforms Model 1 in terms of accuracy, recall, and overall predictive capability. It demonstrates the ability to correctly identify all high-risk loans while maintaining good precision for high-risk loans.

Problem Dependency: The selection of an appropriate model may be dependent upon the particular issue being addressed. If the primary objective is to effectively identify high-risk loans (1's), Model 2 appears as the obvious preference due to its higher recall rate. Nevertheless, in situations when achieving a balance between precision and recall is of utmost importance, it may be imperative to undertake additional adjustment and re-testing.

Recommendation: Given the significant enhancement in prediction, Model 2, trained with oversampled data, is recommended for assessing credit risk much better as compared to Model 1. It offers a higher level of confidence in identifying high-risk loans, which is a crucial task for a lending services company to mimimize their risk of lending.

Justification: The justification for recommending Model 2 is based on its superior performance in terms of recall, which ensures that all high-risk loans are correctly identified. The significance of this matter becomes even more significant in the context of risk evaluation within the lending sector, as the failure to identify a loan with a substantial risk profile might result in financial loss.

Overall, The results show that data resampling strategies can greatly improve machine learning models' prediction skills in situations involving imbalanced datasets, such as credit risk assessment.

