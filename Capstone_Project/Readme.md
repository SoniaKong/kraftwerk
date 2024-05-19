## Project Name: Customer Purchase Propensity

Task: Using Multiple Classification methods to idenfity high propensity customers
Goal: The goal of this project is to identify more effective ways for people who are likely to subsribe to our product and compare their performances to identify the best model.
Techniques Expected to Use: Data cleaning, preprocessing, column transformations, feature selections, classifier selections, performation evaluation and comparion with following 4 methods:
KNN - LOGISTICRegression - DecisionTree - SVM
Data: Online Shoppers Purchasing Intention Dataset Link: https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset Of the 12,330 sessions in the dataset, 84.5% (10,422) were negative class samples that did not end with shopping, and the rest (1908) were positive class samples ending with shopping.

## Data Cleaning:

 1) Dropped Car column, since it contains 99% of missing values.
 2) Then Dropped Rows with missing values.
 2) Removed "()" from passanger column, i.e. Kid(s) to Kids
 3) Changed type of Y column from Int64 to String for better plotting¶
 4) After cleaning, the final dataset has 12079 entries, 25 columns

## Code and Visualization:

 1) Used Pandas value_counts spot-check the distribution of specific column
 2) Used Seaborn countplot and pie chart to visualize the difference of acceptance rate for different segmentation to identify the common characteristics of potential likely-hood group.

## Summary of Findings:

 1) Findings for Bar Coupons:
 - Overall coupon acceptance rate is lower than non-acceptance rate (41% vs 59%)
 - However, for those who went to Bar more than once a month, the acceptance rate is significantly higher (69% vs 31%), and with further analysis for those who went to bar more than 4 times a month, we found the more request they went, the higher the acceptance rate we can see.
 - Passenger with no Kids is another factor for a higher acceptance rate, which is reasonable because most of bars has age limitation
 - Drivers with age under 30 are more likely to accept coupon, i guess that is reasonable too because bars are more attractive to young people.
 - In summary, drivers who went to bar more than once a month, no kids passenger, age under 30 are more likely to accept the bar coupons.

 2) Findings for Restaurant(<20) coupons:
 - Overall coupon acceptance rate is higher than non-acceptance rate (71% vs 29%), which is not like the bar coupons, and we can see a potential business opportunity already.
 - After breakdown, we can see drivers who went to cheap restaurant more than once and age under 25 have even higher acceptance rate (76%)
 - If we only look at longer-term coupon (except the 2h immediate coupon), we found the acceptance rate is super high (84% vs 16%)
 - In summary, overall drivers are already easy to accept cheap restaurant coupons and those who went to cheap restaurant once a month, age under 25 are even more likely to accept coupon, especially the longer-term coupon.

## Next Step and Recommendations:
- Distribute Cheap restaurant coupons for general targeting. For 2h expiration immediate coupons (maybe a deeper discount than 1d/2d expiration coupons), distribute them only during the non-mealtime to increase the traffic.
- Distribute Bar coupons for precise targeting (who went to bar at least once a month, age under 30 and no kids onboard).
- If possible, do a break-even analysis to see if the discount loss could be compensated by the increase of traffic.
