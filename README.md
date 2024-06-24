# credit-risk-classification

## Overview of the Analysis

* Purpose of the analysis

The purpose of this analysis is to build a predictive model and leverage machine learning techniques that can classify loans as either "healthy" (low risk) or "high-risk." This type of analysis is commonly used in the financial industry to assist lenders in making informed decisions about loan approvals and risk management. In terms of real world use by financial institutions similar models are used for risk assessment, risk management to mitigate losses and by accurately classifying loan applications, lenders can streamline the approval process, ensuring that only applicants with a high probability of repayment are approved.  Other areas it can help are with cost reduction by identifying high-risk loans, lenders can take preemptive actions such as offering different terms or additional scrutiny, reducing the likelihood of defaults.  

* Explain what financial information the data was on, and what you needed to predict.

The financial information supplied contained information on loan size, interest rate,	borrower income, debt to income, number of accounts,	derogatory marks,	total debt,	and loan status.  Derogatory marks refer to negative records on an individual's credit report such as late or missed payments that may impact creditworthiness and the likelihood of loan approval.  Loan status was split into 0 and 1.  The loans with a status of 0 was referred to as a healthy loan, and those with a status of 1 was referred to as a high risk loan.

* Provide basic information about the variables you were trying to predict.

Using the information that was given, we would use this to build a logistic regression model to identify the creditworthiness of borrowers.  The model was created to see whether those loans that were identified as e.g. healthy actually are healthy, and those who were high risk actually are high risk.    

* Describe the stages of the machine learning process you went through as part of this analysis.
  
To achieve this, the data was examined where the labels set (y) from the “loan_status” column and the features (X) DataFrame from the remaining columns were created.  The data was then split into training and testing sets.  The test size was set at 30% of the data supplied.  After this was done a Logistic Regression Model was created using the training data (X_train and y_train).  The predictions on the testing data labels was saved by using the testing feature data (X_test) and the fitted model and then the outcomes assessed.  The model's performance was judged by creating a confusion matrix and a classfication matrix, and an evaluation made.  A Logistic Regression Model was used - it was a task requirement - but there are other methods that could also be applied - but these were beyond the scop of this assignment. 

## Results

From the Confusion Matrix:

*  True Negatives: 22,399 - The model correctly predicted 22,399 healthy loans.

*  False Positives: 116 - The model incorrectly predicted 116 high-risk loans as healthy loans.

*  False Negatives: 70 - The model incorrectly predicted 70 healthy loans as high-risk loans.

*  True Positives: 676 - The model correctly predicted 676 high-risk loans

From the Classification Report:

Precision: The ratio of correctly predicted positive observations to the total predicted positives.

*  Precision for class 0 (healthy loans): 1.00
*  Precision for class 1 (high-risk loans): 0.85

Recall (Sensitivity): The ratio of correctly predicted positive observations to all observations in the actual class.

*  Recall for class 0 (healthy loans): 0.99
*  Recall for class 1 (high-risk loans): 0.91

F1 Score: The weighted average of Precision and Recall.

*  F1 score for class 0 (healthy loans): 1.00
*  F1 score for class 1 (high-risk loans): 0.88

Support: The number of actual occurrences of the class in the specified dataset.

*  Support for class 0 (healthy loans): 22,515
*  Support for class 1 (high-risk loans): 746

Overall Accuracy: The ratio of correctly predicted observations to the total observations.

*  Accuracy: 0.99

Summary and Overall Performance:

The model has a high overall accuracy of 99%, suggesting it is very effective at predicting loan status.

For Healthy Loans (Class 0) the model performs exceptionally well with a precision and recall close to 100%, meaning it almost perfectly identifies healthy loans.

For High-Risk Loans (Class 1) the precision for high-risk loans show 85% of the loans predicted as high-risk are actually high-risk, and recall shows 91% of actual high-risk loans are correctly identified.  The F1 score for high-risk loans is 88%, showing a decent balance between precision and recall.  I would recommend using this model - definitely for Healthy loans - but further refinement may be needed for those High Risk loans.  

It does need to noted that the vast bulk of the data is for healthy loans - over 96% of the data provided is for healthy loans.  Therefore any firm decisions regarding higher risk loans need to balanced with this in mind.  Yes it did correctly predict in the majority of cases correctly for high risk loans, if there is a move to increase on a large scale the amount of high risk loans then because this model (relative to healthy loans) does not work as well for high risk loans, I would suggest examining this aspect further to ensure correct identification. 

This is especially true considering the current economic climate as well as a moral context.  If we are correctly identifying high risk loans correctly we reduce risk to lenders.  On a much bigger scale, the sub prime mortgage crisis was caused by high risk mortgages defaulting at a much higher rate than expected.  The effects of this was that some banks needed to be bailed out by national governments which clearly had wide ranging implications.  By identifying high risk loans correctly, support can be put in place to prevent this happening (i.e. defaults on a large scale).  This can be of benefit to the borrower - and to the lender.  

The macro average and weighted average metrics show that the model performs well across both classes, but there's a slight drop in performance for the high-risk class compared to the healthy class. 
