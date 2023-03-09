# Amazon_Vine_Analysis

## Overview of the Analysis: 
In this exercise, the client, SellBy, is considering participating in Amazon's Vine reviews program, a service that allows retailers to pay a small fee to gather reviews from Amazon members. Following an ETL process, this analysis uses PySpark to extract and transform a dataset of book sales and reviews from Amazon, load the transformed data into pgAdmin connected to an AWS RDS, and complete additional transformation and summary analysis. The analysis performs a comparison between reviews gathered through the Vine program and those gathered separately from the program in order to draw conclusions about potential positivity bias - We are assessing whether the reviews gathered through the Vine program are more favorable than regular reviews, and providing these findings back to the client to inform their decision about whether to participate.

## Resources:
* pgAdmin
* PySpark
* Google colab
* Amazon's library of review datasets on AWS S3: https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt

## Results: 
After the book reviews dataset was extracted from Amazon's S3 library into PySpark, it was transformed into separate data frames displaying information about customers, products, reviews, and vine status. The resulting tables were load into pgAdmin and the AWS RDS server.

<img width="890" alt="image" src="https://user-images.githubusercontent.com/114873837/224174015-f97ba326-a45f-4bde-a20e-23fe1f3f1d2f.png">

After the book reviews dataset was extracted from Amazon's S3 library into PySpark, it was transformed to produce a variety of data frames to load into pgAdmin and the AWS RDS server. 

After the data was loaded into pgAdmin and the AWS RDS server, the data was then prepared for analysis through a series of filtering steps designed to isolate the most impactful data. The complete dataset of book reviews was reduced to reviews voted as "helpful" by other Amazon visitors (more specifically, reviews receiving over 20 votes and 50% "helpful" votes). Then, the dataset was divided by the "Vine" column to create two separate datasets for vine and non-vine reviews that can be compared, allowing us to address the questions below:

* How many Vine reviews and non-Vine reviews were there?
In this dataset, there were 5012 reviews submitted through the paid Vine program and 109297 reviews not associated with Vine.

<img width="424" alt="image" src="https://user-images.githubusercontent.com/114873837/223878547-d05808eb-cbe9-41c0-ad8d-7f01874d5205.png">

* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
Of the reviews associated with the Vine program, 2031 were five stars. For reviews not submitted through the Vine program, 49967 were five stars.

<img width="446" alt="image" src="https://user-images.githubusercontent.com/114873837/223878893-9fe86311-f910-4bfe-b3a8-46cb985f19f8.png">

* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
Using the above counts for five-star reviews and total number of reviews, the percentage of Vine and non-Vine reviews that earned five stars were 40.5% and 45.7%, respectively.

<img width="574" alt="image" src="https://user-images.githubusercontent.com/114873837/223879140-0fa65fdc-eac8-49cf-9581-550829284d69.png">

## Summary: 

While one may assume that reviews submitted for products through the Vine program would skew higher than their counterparts (i.e. the Amazon members receiving the free product to review will rate the product more favorably), the analysis of this dataset did not support this theory. Based on these observations, the proportion of Vine reviews that rated the products as five stars was only 40.5% in comparison to the non-Vine 45.7%. Since books are a type of art form where preference can be very subjective and unique to the individual, it is possible that books that are provided for free to the reviewers don't always match their preferences for genre or author - whereas, if a consumer has sought out the book to purchase it, they are more likely to be interested in enjoying the content. 

## Recommendations:
Given the observations above, it could be helpful to assess the descriptive statistics and distribution of star count between the two datasets. While vine reviewers may not have granted as many five-star reviews, did they provide more four-star reviews that, when combined with the five-star review count, would result in an overall "favorable" rating that would outweigh that of the non-vine reviewers? Knowing the proportion of one-star or two-star reviews for each group would also help us determine if a certain group found the books more polarizing, rating them at the more extreme ends of the scale.  
