# deep-learning-challenge
Module 21 Report

Overview of the Analysis
This analysis reviews the accuracy in predicting the likelihood of defaulting on a loan given a specific set of data:

Loan size
Interest rate
Borrower income
Debt to income
Number of accounts
Derogatory marks
Total debt
To do this I used machine learning. First with the actual set of data consisting of 77,536 rows (75036 healthy loan status, 2500 with high-risk loan status. This will be referenced as "Machine Learning Model 1".

A second set of data was compiled using RandomOverSampler to create an equal number of rows for both categories (56277 healthy loan status, 56277 high-risk loan status). This will be referenced as "Machine Learning Model 2".

All other variables were kept consistent between the two models:

Standard 75%/25% train_test set
Logistic regression model
Results
Following are the findings from the two models:

Machine Learning Model 1:

Accuracy: 0.9924164259182832
Confusion Matrix:
Healthy Loans - 18679, 80
High-risk Loans - 67, 558
Classification Report: precision recall f1-score support
Healthy Loan 1.00 1.00 1.00 18759 High-Risk Loan 0.87 0.89 0.88 625

accuracy                           0.99     19384
macro avg 0.94 0.94 0.94 19384 weighted avg 0.99 0.99 0.99 19384

Machine Learning Model 2:

Accuracy: 0.9952022286421791
Confusion Matrix:
Healthy Loans - 18668, 91
High-risk Loans - 2, 623
Classification Report: precision recall f1-score support
Healthy Loan 1.00 1.00 1.00 18759 High-Risk Loan 0.87 1.00 0.93 625

accuracy                           1.00     19384
macro avg 0.94 1.00 0.96 19384 weighted avg 1.00 1.00 1.00 19384

Precision: Did not change between the two models for Healthy or High-risk

Recall: Improved considerably from .89 for high-risk loans in Model 1 to 1.00 in Model 2

f1-score: Improved from .88 for high-risk loans in Model 1 to .93 in Model 2 (an increase in this would be expected as f1-score is the average of precision and recall)

Macro avg: This is the average for each, precision, recall, and f1-score, across both classes and shows the improvement as mentioned above

This is intended to provide a balanced score between classes
Weighted avg: This is the weighted average across classes taking the number of samples in each into account.

In this case, it more closely matches Healthy loans due to the much larger class size
Summary
While the two models don't appear to vary much, as the Healthy loan predication rate for both is 100%, there are some significant improvements to High-risk loan predications in Model 2. This improvement can be attributed to the oversampling adding volume to the training and thereby improving the prediction of High-risk loans. For this reason, I would recommend using as much data as possible when training machine learning to improve accuracy as much as possible.