# AmazonVine_Analysis

Programs and languages used: `PySpark`, `pgAdmin`, `Google Colabratory`, `Postgres`

Reference Files: Amazon_Reviews_ETL.ipynb, Amazon_Vine_Analysis.ipynb

## Overview
The purpose of this analysis was to review Amazon reviews written by members of the Paid Amazon Vine Program, a service which allows manufacturers to receive reviews of their products and determine if there is any biases between Vine members and non-member reviews.

In order to identify if there are any biases towards favorable reviews, the percentage of 5 star ratings compared to total ratings needed to be collected. 

The Amazon dataset for "Video Games" was used for this analysis.

[dataset link](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz)

## Results:

### Deliverable 1: refer to file => Amazon_Reviews_ETL.ipynb
* Create an RDS instance database using AWS and pfAdmin - ***successful***
* Extract the dataset and create a new DataFrame using `Colabratory Notebook` and `pySpark`
* Transform dataframe - create the "customer_id" table and count the "customer_ids"
* Drop Duplicates on the "products_table"
* Create the "review_id_table" and convert "review_date" column to a date
* Create vine_table
* Write all newely created tables to pgAdmin and run query to check data upload- ***succussful***

<img width="597" alt="Screen Shot 2023-02-20 at 11 38 06 AM" src="https://user-images.githubusercontent.com/115188500/220170185-929db85c-cbd6-4f4f-a658-20701a7862f4.png">

### Deliverable 2: Analysis of Vine Reviews Refer to file => Amazon_Vine_Analysis.ipynb
* Count of "Total Votes" equal or greater than 20
* Percent of "Helpful Votes" to "Total Votes" equal or greater than 50%

![Vine_percent50](https://user-images.githubusercontent.com/115188500/220171019-353cf204-9be0-40e6-9391-df42e7c8f72a.png)

Question 1: How many Vine reviews and non-Vine reviews were there?

* Vine members made up only 0.17% (102) of the total reviews (61,173).

![Vine_total](https://user-images.githubusercontent.com/115188500/220172146-61b78891-4323-42a6-8a62-3cd3c7bc4685.png)
![Vine_paid](https://user-images.githubusercontent.com/115188500/220172587-e6475888-ec0e-4455-90e7-f78bab306e2f.png)
![Vine_nonpaid](https://user-images.githubusercontent.com/115188500/220172689-bdc16ee6-6b5d-46b5-93c7-24527a1909ce.png)

Question 2: How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
* Vine members gave 48 out of 102 reviews of a 5 -Star rating.
* Non - Vine members gave 19,922 out of 61,173 reviews of a 5 - Star rating

Question 3: What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
* 47% of the reviews for Vine memebers were rated 5 stars
* 32% of the reviews for non-Vine memebers were rated 5 stars

## Summary

Based on the findings of the analysis, Vine members may show a little positivity bias with the video game products considering nearly half of the ratings were 5 Star while Non-Vine members showed around 15% less 5 Star ratings. With this information we can assume that non-Vine customers are more critical when reviewing video games giving far less 5 stars compared to Vine members. Performing an additional analysis on different category of products might be helpful in determining bias.






