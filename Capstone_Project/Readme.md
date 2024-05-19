Project Name: Will a Customer Accept the Coupon?¶
Data Cleaning:
Dropped Car column, since it contains 99% of missing values.
Then Dropped Rows with missing values.
Removed "()" from passanger column, i.e. Kid(s) to Kids
Changed type of Y column from Int64 to String for better plotting¶
After cleaning, the final dataset has 12079 entries, 25 columns
Code and Visualization:
Used Pandas value_counts spot-check the distribution of specific column
Used Seaborn countplot and pie chart to visualize the difference of acceptance rate for different segmentation to identify the common characteristics of potential likely-hood group.
Summary of Findings:
Findings for Bar Coupons:
Overall coupon acceptance rate is lower than non-acceptance rate (41% vs 59%)
However, for those who went to Bar more than once a month, the acceptance rate is significantly higher (69% vs 31%), and with further analysis for those who went to bar more than 4 times a month, we found the more request they went, the higher the acceptance rate we can see.
Passenger with no Kids is another factor for a higher acceptance rate, which is reasonable because most of bars has age limitation
Drivers with age under 30 are more likely to accept coupon, i guess that is reasonable too because bars are more attractive to young people.
In summary, drivers who went to bar more than once a month, no kids passenger, age under 30 are more likely to accept the bar coupons.
Findings for Restaurant(<20) coupons:
Overall coupon acceptance rate is higher than non-acceptance rate (71% vs 29%), which is not like the bar coupons, and we can see a potential business opportunity already.
After breakdown, we can see drivers who went to cheap restaurant more than once and age under 25 have even higher acceptance rate (76%)
If we only look at longer-term coupon (except the 2h immediate coupon), we found the acceptance rate is super high (84% vs 16%)
In summary, overall drivers are already easy to accept cheap restaurant coupons and those who went to cheap restaurant once a month, age under 25 are even more likely to accept coupon, especially the longer-term coupon.
Next Step and Recommendations:
Distribute Cheap restaurant coupons for general targeting. For 2h expiration immediate coupons (maybe a deeper discount than 1d/2d expiration coupons), distribute them only during the non-mealtime to increase the traffic.
Distribute Bar coupons for precise targeting (who went to bar at least once a month, age under 30 and no kids onboard).
If possible, do a break-even analysis to see if the discount loss could be compensated by the increase of traffic.
