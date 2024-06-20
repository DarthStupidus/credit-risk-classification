# credit-risk-classification

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms).

The purpose of this analysis is to build a predictive model and leverage machine learning techniques that can classify loans as either "healthy" (low risk) or "high-risk." This type of analysis is commonly used in the financial industry to assist lenders in making informed decisions about loan approvals and risk management. In terms of real world use by financial institutions similar models are used for risk assessment, risk management to mitigate losses and by accurately classifying loan applications, lenders can streamline the approval process, ensuring that only applicants with a high probability of repayment are approved.  Other areas it can help are with cost reduction by identifying high-risk loans, lenders can take preemptive actions such as offering different terms or additional scrutiny, reducing the likelihood of defaults.  

The financial information supplied contained information on loan size, interest rate,	borrower income, debt to income, number of accounts,	derogatory marks,	total debt,	and loan status.  Derogatory marks refer to negative records on an individual's credit report such as late or missed payments that may impact creditworthiness and the likelihood of loan approval.  Loan status was split into 0 and 1.  The loans with a status of 0 was referred to as a healthy loan, and those with a status of 1 was referred to as a high risk loan.

Using the information that was given, we would use this to build a logistic regression model to identify the creditworthiness of borrowers.  

To achieve this, the data was examined where the labels set (y) from the “loan_status” column and the features (X) DataFrame from the remaining columns were created.  The data was then split into training and testing sets.  After this was done a Logistic Regression Model was created using the training data (X_train and y_train).  The predictions on the testing data labels was saved by using the testing feature data (X_test) and the fitted model and then the outcomes assessed.  The model's performance was judged by creating a confusion matrix and a classfication matrix, and an evaluation made.

## Results

**Question:** How well does the logistic regression model predict both the `0` (healthy loan) and `1` (high-risk loan) labels?

**Answer:** 

From the Confusion Matrix:

True Negatives: 22,399 - The model correctly predicted 22,399 healthy loans.

False Positives: 116 - The model incorrectly predicted 116 high-risk loans as healthy loans.

False Negatives: 70 - The model incorrectly predicted 70 healthy loans as high-risk loans.

True Positives: 676 - The model correctly predicted 676 high-risk loans

From the Classification Report:

Precision: The ratio of correctly predicted positive observations to the total predicted positives.

Precision for class 0 (healthy loans): 1.00
Precision for class 1 (high-risk loans): 0.85

Recall (Sensitivity): The ratio of correctly predicted positive observations to all observations in the actual class.

Recall for class 0 (healthy loans): 0.99
Recall for class 1 (high-risk loans): 0.91

F1 Score: The weighted average of Precision and Recall.

F1 score for class 0 (healthy loans): 1.00
F1 score for class 1 (high-risk loans): 0.88

Support: The number of actual occurrences of the class in the specified dataset.

Support for class 0 (healthy loans): 22,515
Support for class 1 (high-risk loans): 746

Overall Accuracy: The ratio of correctly predicted observations to the total observations.

Accuracy: 0.99

For Healthy Loans (Class 0) the model performs exceptionally well with a precision and recall close to 100%, meaning it almost perfectly identifies healthy loans.

For High-Risk Loans (Class 1) the precision for high-risk loans show 85% of the loans predicted as high-risk are actually high-risk, and recall shows 91% of actual high-risk loans are correctly identified.  The F1 score for high-risk loans is 88%, showing a decent balance between precision and recall.

Summary and Overall Performance:

The model has a high overall accuracy of 99%, suggesting it is very effective at predicting loan status.

The macro average and weighted average metrics show that the model performs well across both classes, but there's a slight drop in performance for the high-risk class compared to the healthy class. 
