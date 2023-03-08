# Amazon_Vine_Analysis

## Overview of the Analysis: 
The client, SellBy, is considering participating in Amazon's Vine reviews program, a service that allows retailers to pay a small fee to gather reviews from Amazon members. The purpose of this analysis is to use Amazon Web Services RDS, PySpark, and pgAdmin to complete an ETL process on a dataset for the selected product of books. When examining the data throughout this process, we are assessing whether the reviews gathered through the Vine program are more favorable than regular reviews, and providing these findings back to the client to inform their decision about whether to participate.

## Results: 
(Prepping the data)

* How many Vine reviews and non-Vine reviews were there?
In this dataset, there were 5012 reviews submitted through the paid Vine program and 109297 reviews not associated with Vine.

<img width="424" alt="image" src="https://user-images.githubusercontent.com/114873837/223878547-d05808eb-cbe9-41c0-ad8d-7f01874d5205.png">

* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
Of the reviews associated with the Vine program, 2031 were five stars. For reviews not submitted through the Vine program, 49967 were five stars.

<img width="446" alt="image" src="https://user-images.githubusercontent.com/114873837/223878893-9fe86311-f910-4bfe-b3a8-46cb985f19f8.png">

* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
Using the above counts for five-star reviews and total number of reviews, the percentage of Vine and non-Vine reviews that earned five stars were 45.7% and 40.5%, respectively.

<img width="574" alt="image" src="https://user-images.githubusercontent.com/114873837/223879140-0fa65fdc-eac8-49cf-9581-550829284d69.png">

## Summary: 
In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.
