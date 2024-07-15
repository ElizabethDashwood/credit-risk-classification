# credit-risk-classification

## Module 20 Homework Credit Risk Challenge
### Description:
This is the Module 20 Homework credit-risk-challenge for using scikit-learn (Reference: https://scikit-learn.org/stable/) for Python using the logistic regression function along with a confusion matrix and classification report, with pandas in Jupyter Lab. 

### Getting started:
This challenge has 1 project called: Credit Risk using a starter code csv file called lending_data.csv

### Installations required:
This project has been run in a Windows 11 GitBash environment, using Python 3.10.13 together with Jupyter Lab as the editor

### Executing Homework Challenge Requirements:
Please see credit_risk_classification.ipynb for the script which performs all code requirements of the project, and includes a paragraph of analysis of results at the end of the file.   More detailed analysis follows below in the Credit Risk Analysis Report.

## Overview of the Analysis - Credit Risk Analysis Report:

### Purpose:
The purpose of the analysis in the credit risk project was to determine how accurate the Logistic Regression model was for identifying healthy loans and high-risk loans.  As is the nature of the Logistic Regression model, there are binary outcomes (that is, two possible outcomes) for the data being tested.  So in this project, the outcome for each data record was that it represented either a healthy loan (indicted by 0) or a high-risk loan (indicated by 1). 

### Financial Loan input data for predictions
The input data in the lending_data.csv file had a loan_status column to indicate if the loan was healthy (indicated by 0), or high-risk (indicated by 1).  Logisitc Regression is a form of supervised learning, and as is the case with supervised learning models, we know the answer to the question we are analysing (that is we know the loan_status as either a 0 or 1), and we are determining how well the Logistic Regression model predicts the correct outcome, to enable accurate classification of the data into the healthy and high-risk loans.

### Data preparation and machine learning steps used in the analysis
To create an X and y variable, the loan_status was separated from the lending_data.csv file, with this single column of loan status data being used as the y variable, which represents the 'target' or 'labels' for the two possible outcomes (healthy loans and high-risk loans.)  The remaining columns of data in the lending_data.csv file form the X variable 'features' of the loans and include items such as the loan size, interest rate, borrower income, debt to income ratio, and total debt.  

The scikit-learn train_test_split function, then uses the X and y variables to split the data into a train dataset that will teach the Logistic Regression model, and a test dataset that will test the Logistic Regression model after it is trained, with the aim of seeing how accurately the model predicts the status of the loans. 

The scikit-learn Logistic Regression function is then called and uses the training data for the X and y axis along with other functions such as the default solver 'lbfgs' and a maximum of 200 interations to control the model's performance and the .fit function to process the data in the Logistic Regression model.  

The resulting trained Logistic Regression model, is then used to process the test data for the X and y access to predict which records and healthy loans and which records are high risk loans.  The resulting predictions are compared to the actual loan status to see how accurate the predictions are.

If this project, is would appear theat the model was very accurate for the healthy loans and also reasonably accurate for the high-risk loans, as further explained in the Results section below.

To further test the accuracy of the model, the predictions and actual loan status data were analysed with the Confusion Matrix and the Classification Report functions from scikit learn. 


## Results Analysis using precision and recall scores and accuracy measures

### Machine Learning Logisitc Regression Model:
 
* Using the classification report, we see that this logistic regression model did a very good job at predicting the healthy loans, with the model achieving 100% precision and 100% recall for healthly loans.
* While the model does have 99% accuracy overall and a weighted average accuracy of 99%, these very high percentages, are potentially skewed by the input data have many more healthy loan records, than high-risk loan records.
* The macro average accuracy of 94%, and the precision and recall percentages of 87% and 89% respectively for high-risk loans, are indicative of the logistic regression model being slightly less accurate for predicting high-risk loans. So to improve the model further, attention would need to be paid to identifying features that help determine high-risk loans.

## Summary

In summary, the Logistic Regression model did an excellent job at predicting the healthly loans as demonstrated by the accurancy, precision and recall scores noted above. The confusion matrix rows and columns both add to the total of 19384 records in the model, which is another indicator that the model is accurate.  The classification report further indicated that the model does a good job predicting high-risk loan between 88% and 94% of the time.
This model can be recommended to predict the outcome for loans.  However, further analysis of high-risk home loans is needed, potentially with a more advanced machine learning model, considering more features that indicate tendency for a loan to become high-risk. 

The performance of the model is important, particularly in correctly identifying loan status = 1 for the loans that are high-risk, so that measures can be taken to further analyse characteristics of why the loans are high risk, and to avoid approval of such loans in the further. It would also be useful to further train the model to try to eliminate false positve and false negative predictions.  This would help to ensure that loans are correctly identified as healthy or high-risk, so that appropriate actions can be taken by loan approvers. 
