## Project Name: Customer Purchase Propensity

1) Task: Using Multiple Classification methods to idenfity high propensity customers
2) Goal: The goal of this project is to identify more effective ways for people who are likely to subsribe to our product and compare their performances to identify the best model.
3) Techniques Expected to Use: Data cleaning, preprocessing, column transformations, feature selections, classifier selections, performation evaluation and comparion with following 4 methods:
KNN - LOGISTICRegression - DecisionTree - SVM
4) Data: Online Shoppers Purchasing Intention Dataset Link: https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset Of the 12,330 sessions in the dataset, 84.5% (10,422) were negative class samples that did not end with shopping, and the rest (1908) were positive class samples ending with shopping.

## Data Cleaning:

 1) Dropped Na rows with missing values.
 2) Standscaled all numerical columns.
 3) Onehotencoded 3 categorical columns: 'VisitorType','Weekend','Month'
 4) Take 'Revenue' as the target column and changed Yes/No to 1/0 with mapping function
 5) After cleaning, the final dataset has 12330 rows × 29 columns and then split it into 80:20 for holdout validation

## Modeling and Evaluation:

 1) Used KNN/LOGISTICRegression/DecisionTree/SVM train the model
 2) Evaluate the metrics: Trian_score, Test_score, Preciosn, Recall, F1_score, Fitting time
 3) Plotted confustion matrix based on test data
 4) Plotted ROC based on test data
 5) Plotted Precison/Recall vs Threshold on test data
 6) Model Compariosn:
    
    
 8) Used Shap analysis to explain the linear indicator for Logistic Regression model

## Summary of Findings:

 1) SVM model is performing better than KNN, Decision Tree or Logistic Regression with best F1 score.
 2) From the shap analysis, we can see some positive indicators, such as the more the pagevalues, the longer the product related duration, the more the likely customer convert, which makes sense since stronger engagement shows the intention. 
 3) Also from shap analytis, we can see some negative indicatiors, such as the more exit or bounce rate, the less likely to convert, which apprarently shows less interest.

## Next Step and Recommendations:
 1) If we can figure out way to improve the page to be more attrative, customers could spend more time on the pages then ultimately improve the conversion rate. 
 2) Also if we can use this model to only target high propensity customers with customerized email messages, the conversion rate could be improved accordingly as well. 
