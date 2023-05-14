# Use main.ipynb file in the Starte_Code folder for the solution

# Loan Risk Classification using Machine Learning

## Overview

The purpose of this analysis is to compare the performance of two machine learning models, Logistic Regression and RandomOverSampler, in classifying loan risk. In particular, we will compare the balanced accuracy, precision, and recall scores of the two models. Originally the data contained various features like loan size, interest rate, borrower income, etc. These features are typically used to predict whether the loan is going to deafault or not. which was provided in column 'loan_status' with 0 - no default, 1 - default. Based on this information, it is possible to build up a machine learning model that can predict whether the customer will default or not.

### Variables used to predict:
- model_lr - Logistic Regression - used the original data to make predictions
- model_ros  - Random Over Sampler - generated synthetic data to improve the recall


### Machine Learning Stages:
1. Split the data into training(~75%) and testing (~25%)
2. Train the model with the training data
3. Predict the outcomes of the model by using the testing data
4. Check the accuracy score
5. Repeat the process fordifferent models and pick the model that suits the application in question

### Models Used:

Logistic Regression and RandomOverSampler are two different machine learning models that can be used for classification tasks.

Logistic Regression is a statistical model that is commonly used for binary classification problems where the response variable is categorical and has two levels. It works by estimating the probability of an event occurring based on the values of the independent variables. It creates a decision boundary that separates the two classes and assigns a probability to each observation based on which side of the boundary it falls. The output of the model is a binary prediction that assigns each observation to one of the two classes.

RandomOverSampler is a resampling technique that is commonly used to address imbalanced datasets. In classification tasks, an imbalanced dataset refers to a dataset where one class has significantly fewer observations than the other. This can cause problems for machine learning models because they may be biased towards the majority class and perform poorly on the minority class. RandomOverSampler addresses this problem by oversampling the minority class, which involves creating synthetic observations for the minority class by randomly duplicating existing observations. This helps to balance the dataset and improve the performance of the machine learning model.

## Results

### RandomOverSampler

- Balanced accuracy score: 0.99
- Precision and recall scores:

    | Class | Precision | Recall | F1-Score |
    | --- | --- | --- | --- |
    | Healthy Loan | 1.00 | 0.99 | 1.00 |
    | High Risk Loan | 0.84 | 0.99 | 0.91 |
    
### Logistic Regression

- Balanced accuracy score: 0.95
- Precision and recall scores:

    | Class | Precision | Recall | F1-Score |
    | --- | --- | --- | --- |
    | Healthy Loan | 1.00 | 0.99 | 1.00 |
    | High Risk Loan | 0.85 | 0.91 | 0.88 |
    
## Summary

Both models achieved high accuracy in classifying loan risk, with RandomOverSampler performing slightly better than logistic regression in terms of balanced accuracy and precision for the High Risk Loan class. RandomOverSampler performed better in recall for the High Risk Loan class, indicating that it was better at identifying actual High Risk Loans.

If correctly identifying all High Risk Loans is a higher priority, RandomOverSampler may be the better choice as it has a higher recall score for this class. The choice ultimately depends on the specific goals and priorities of the project. In this particular case RandomOverSampling is a better model to use, since we are trying to lower the amount of false negatives, since defaulted loans are high cost for the banks.

