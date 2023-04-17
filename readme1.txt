Title: Summary of Practical Application 1 explaining the analysis of the coupons and how acceptance rates change based on different variables


Description: We perform analysis of the coupon acceptance rate based on the different variables described below.

The attributes of this data set include:

User attributes
Gender: male, female
Age: below 21, 21 to 25, 26 to 30, etc.
Marital Status: single, married partner, unmarried partner, or widowed
Number of children: 0, 1, or more than 1
Education: high school, bachelors degree, associates degree, or graduate degree
Occupation: architecture & engineering, business & financial, etc.
Annual income: less than $12500, $12500 - $24999, $25000 - $37499, etc.
Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
Number of times that he/she buys takeaway food: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
Number of times that he/she goes to a coffee house: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
Number of times that he/she eats at a restaurant with average expense less than $20 per person: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8

Contextual attributes
Driving destination: home, work, or no urgent destination
Location of user, coupon and destination: we provide a map to show the geographical location of the user, destination, and the venue, and we mark the distance between    each two places with time of driving. The user can see whether the venue is in the same direction as the destination.
Weather: sunny, rainy, or snowy
Temperature: 30F, 55F, or 80F
Time: 10AM, 2PM, or 6PM
Passenger: alone, partner, kid(s), or friend(s)

Coupon attributes
time before it expires: 2 hours or one day


The variable names are

Data columns (total 26 columns):
 #   Column                Non-Null Count  Dtype 
---  ------                --------------  ----- 
 0   destination           12684 non-null  object
 1   passanger             12684 non-null  object
 2   weather               12684 non-null  object
 3   temperature           12684 non-null  int64 
 4   time                  12684 non-null  object
 5   coupon                12684 non-null  object
 6   expiration            12684 non-null  object
 7   gender                12684 non-null  object
 8   age                   12684 non-null  object
 9   maritalStatus         12684 non-null  object
 10  has_children          12684 non-null  int64 
 11  education             12684 non-null  object
 12  occupation            12684 non-null  object
 13  income                12684 non-null  object
 14  car                   108 non-null    object
 15  Bar                   12577 non-null  object
 16  CoffeeHouse           12467 non-null  object
 17  CarryAway             12533 non-null  object
 18  RestaurantLessThan20  12554 non-null  object
 19  Restaurant20To50      12495 non-null  object
 20  toCoupon_GEQ5min      12684 non-null  int64 
 21  toCoupon_GEQ15min     12684 non-null  int64 
 22  toCoupon_GEQ25min     12684 non-null  int64 
 23  direction_same        12684 non-null  int64 
 24  direction_opp         12684 non-null  int64 
 25  Y                     12684 non-null  int64 


We eliminated column labeled 'car' as it is missing most values and also the column 'toCoupon_GEQ5min' since all the values for te entire dataset are equal to 1 and thus it is a useless attributes. So we use 23 columns in our final analysis and after correctly naming the passenger column the 23 columns are.

#   Column                Non-Null Count  Dtype 
---  ------                --------------  ----- 
 0   destination           12684 non-null  object
 1   passenger             12684 non-null  object
 2   weather               12684 non-null  object
 3   temperature           12684 non-null  int64 
 4   time                  12684 non-null  object
 5   coupon                12684 non-null  object
 6   expiration            12684 non-null  object
 7   gender                12684 non-null  object
 8   age                   12684 non-null  object
 9   maritalStatus         12684 non-null  object
 10  has_children          12684 non-null  int64 
 11  education             12684 non-null  object
 12  occupation            12684 non-null  object
 13  income                12684 non-null  object
 14  Bar                   12577 non-null  object
 15  CoffeeHouse           12467 non-null  object
 16  CarryAway             12533 non-null  object
 17  RestaurantLessThan20  12554 non-null  object
 18  Restaurant20To50      12495 non-null  object
 19  toCoupon_GEQ15min     12684 non-null  int64 
 20  toCoupon_GEQ25min     12684 non-null  int64 
 21  direction_same        12684 non-null  int64 
 22  direction_opp         12684 non-null  int64 
 23  Y                     12684 non-null  int64 


The column 'Y' indicates acceptance with 1= Accept and O= Reject

Organization of the repository:
The public github URL is https://github.com/RJGeorge007/PracticalApplication1
The data file is called coupons.csv.
There is an image folder storing the various plots
There is the Jupyter notebook "Assignment 5" that detail out the analysis

We use pandas, seaborn, matplotlib and numpy technologies to analyze individual and joint effects on acceptance rate.


What are our findings?

1. 57% of the total observations accepted the coupon
2. 59% of the bar coupons were accepted
3. Drivers who went to bars less than three times accepted coupons 63% of the time
4. Folks who went to bars more than three times accepted coupons 76% of the time.
5. Folks who went to bars less than three times accepted coupons 63% of the time.
6. So there is a higher acceptance rate for bar visits greater than 3.
7. 70% of the coupons were accepted by those over 25 and visiting bars more than once a month
8. 60% of the coupons were accepted by those under 25 and visiting bars less than once a month
9. So older multiple visit patrons had a higher acceptance rate
10. There was a 71% acceptance rate for drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry
11. The acceptance rate for for drivers who go to bars more than once a month, had passengers that were not a kid, and were not widowed is also 71%
12. The acceptance rate for those who go to bars more than once a month and are under the age of 30 is 72%
13. The acceptance rate for those who go to cheap restaurants more than 4 times a month and income is less than 50K is 54%
14. Older drivers over 25 visiting bars more than three times a month had the largest acceptance rate.
15. We see that if you are driving to work you have the lowest acceptance rate of 65%, then 76% with no particular destination in place and 71% if you combine these two groups
16. We know that almost 80% of the folks on their way home accepted a carryout coupon. 
17. All drivers with children at home accepted carry out coupons 74% of the time
18. Looks like the acceptance rate for carryout without children is 73% and there is no material difference between having children at home or not.
19. Driver acceptance was 75% of carryout coupons if driving in the opposite direction which is higher than 70% acceptance in the same direction and this is counterintuitive.
This specific data may be incorrect or drivers don't mind turning around if the deal is good.
20. Overall lower incomes have higher acceptance across all the areas until you make USD 62,500 For the next three income brands acceptance rate is about the same.The only outlier is if the income is USD 100,000 or more
21. Males tend to accept coupons more than females
22. When the day is sunny,more coupons are accepted than rejected and more coupons are rejected than accepted on rainy and snowy days
23. We see that 57% of Single and Married Partner categories accepted the coupons
24. Persons under the age of 30 accept coupons 60% of the time
25. When folks were not in a rush to get to work or home, they accepted more coupons
26. Coupons will longer validity are accepted more
27. Cheap restaurants and Carry out has the highest acceptance rate.
28. Coffee House and Cheap Restaurants total acceptance is about the same with carry out next.
29. As expected, bars and expensive restaurants have lower number of coupons offered and rejection rates are higher


Recommendations:
Keep offering coupons for Coffee House between the hours of 6 AM and 3PM
Increase offering of Cheap Restaurants between 10 am and 10PM
Increase offering of Carry out coupons between 10am and 10PM
Bar and Expensive restaurant coupons should be offered between 6pm and 10PM irrespective of 2h expiry or 1 day expiry
For Takeout coupons do not target a specific demographic
For Expensive restaurant, target a higher income bracket
For Coffee House, target a younger demographic
For cheap restaurant target those with kids and lower income groups
