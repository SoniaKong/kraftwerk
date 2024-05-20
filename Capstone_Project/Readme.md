## Project Name: Customer Purchase Propensity

1) Task: Using Multiple Classification methods to idenfity high propensity customers
2) Goal: The goal of this project is to identify more effective ways for people who are likely to subsribe to our product and compare their performances to identify the best model.
3) Techniques Expected to Use: Data cleaning, preprocessing, column transformations, feature selections, classifier selections, shap analysis, performation evaluation and comparion with following 4 methods:
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
 6) Used feature_permutation selected top features for SVM model.
    <img width="1131" alt="Screenshot 2024-05-19 at 8 00 56 PM" src="https://github.com/SoniaKong/kraftwerk/assets/26859063/8b78d777-f94f-4503-a566-c0e08d2c9b3d">
    The values at the top of the table are the most important features in our model, while those at the 
    bottom matter least. The first number in each row indicates how much model performance decreased with random shuffling, using the same performance metric as the 
    model (in this case, accuracy score). The number after the ± measures how performance varied from one-reshuffling to the next, i.e., degree of randomness across 
    multiple shuffles. Negative values for permutation importance indicate that the predictions on the shuffled (or noisy) data are more accurate than the real data. 
    This means that the feature does not contribute much to predictions (importance close to 0), but random chance caused the predictions on shuffled data to be more 
    accurate. This is more common with small datasets. In our example, the top 3 features are PageValues, Administrative, Informational while the 2 least significant 
    are month, VisitorType.
 7) Used GridSearchCV look for best parameters for SVM model.
 8) Model Compariosn:
    <img width="725" alt="Screenshot 2024-05-19 at 7 55 38 PM" src="https://github.com/SoniaKong/kraftwerk/assets/26859063/cf50381e-c0cb-4c88-a25f-7c8ff4ac7f26">
 9) Used Shap analysis to explain the linear indicator for Logistic Regression model:
     <img width="726" alt="Screenshot 2024-05-19 at 8 04 35 PM" src="https://github.com/SoniaKong/kraftwerk/assets/26859063/71f4878c-af79-4bf7-b517-865248f0c9bd">

## Summary of Findings:

 1) SVM model is performing better than KNN, Decision Tree or Logistic Regression with best F1 score.
 2) From the shap analysis, we can see some positive indicators, such as the more the pagevalues, the longer the product related duration, the more the likely customer convert, which makes sense since stronger engagement shows the intention. 
 3) Also from shap analytis, we can see some negative indicatiors, such as the more exit or bounce rate, the less likely to convert, which apprarently shows less interest.

## Next Step and Recommendations:
 1) If we can figure out way to improve the page to be more attrative, customers could spend more time on the pages then ultimately improve the conversion rate. 
 2) Also if we can use this model to only target high propensity customers with customerized email messages, the conversion rate could be improved accordingly as well. 
