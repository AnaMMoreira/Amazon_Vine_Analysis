# Amazon Vine Analysis:  Big Data
## Module 16

## Overview of Project

This is a larger project data source which was used to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, one dataset was chosen from approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. The chosen dataset for this project contains user reviews of Outdoor supplies and can be found at the following link (https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Outdoors_v1_00.tsv.gz) In order to manipulate such larger dataset PySpark was used to perform open-source unified analytics engine for large-scale data processing.  The ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into PgAdmin was performed using Colab Notebooks to run our scripts from google drive as mentioned before using Spark.  The purpose of the analysis is to use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset. A summary of the analysis will be generated to submit to the SellBy stakeholders.

## Process:

Using the cloud ETL process, an AWS RDS database was created which contains with tables in PgAdmin, from the selected dataset from the Amazon Review datasets, and extracted the dataset into a DataFrame. The DataFrame was split into four separate DataFrames that match the table schema in PgAdmin. The transformed data was then uploaded into the appropriate tables and queries were run in PgAdmin.  Posteriorly it was confirmed that the data had been uploaded.

## An Amazon Review dataset is extracted as a DataFrame

Using PySpark and Pandas the data was uploaded and the necessary queries and manipulations yielded the sought after DataFrames as shown in Figure 1

Figure1 Data Upload and manipulation

![insert Figure 1](https://github.com/AnaMMoreira/Amazon_Vine_Analysis/blob/main/Figure1_Amazon_Reviews_ETL2.ipynb%20_Colab.pdf)

## Figure 1 shows the extracted dataset transformed into four DataFrames with the correct columns 


## All four DataFrames were loaded into their respective tables in PgAdmin.  Figure 2 shows the ERD generated after the database and corresponding Tables were created in PostgreSQL using PgAdmin.

![insert Figure 2](Figure2 - ERD)

![insert Figure 2](https://github.com/AnaMMoreira/Amazon_Vine_Analysis/blob/main/Figure2_Amazon_vine_analysis_ERD.png)

Figure 3 demonstrates the structure of the Database in PgAdmin and Figures 5a thru 5b demonstrate that the filtered data tables were successfully uploaded into the PostgreSQL database.

Figure 3 PgAdmin Database

![insert Figure 3](https://github.com/AnaMMoreira/Amazon_Vine_Analysis/blob/main/Figure3_PgAdmin_table_Process.png)

Figures 4a-4d PostgreSQL Tables

![insert Figure 4a](https://github.com/AnaMMoreira/Amazon_Vine_Analysis/blob/main/Figure_4a_Table1.png)

![insert Figure 4b](https://github.com/AnaMMoreira/Amazon_Vine_Analysis/blob/main/Figure_4b_Table2.png)

![insert Figure 4c](https://github.com/AnaMMoreira/Amazon_Vine_Analysis/blob/main/Figure_4c_Table3.png)

![insert Figure 4d](https://github.com/AnaMMoreira/Amazon_Vine_Analysis/blob/main/Figure_4d_Table4.png)

## Determining Bias of Vine Reviews

In order to determine if Paid Vine-Users Reviews are influenced to give higher score reviews, given the monetary gain.  A comparison of Paid vs Unpaid High Score User Reviews was developed using a series of data queries and filtering to yield the target numbers that were in question.

Figure5 - Demonstrates how the Amazon Vine-Users Reviews Analysis was conducted in detail.

![insert Figure 5](https://github.com/AnaMMoreira/Amazon_Vine_Analysis/blob/main/Figure5_Amazon_Vine_Analysis.ipynb%20_Colab.pdf)

In Figure 5 it can be observed that the data was loaded Into Spark Dataframe and first filtered by Review Contributors which had more than 20 Reviews.  The selection was further reduced by filtering for Reviews considered Useful by at least 50% of the total reviews.  If one could perhaps equate "usefulness" with a measure of accuracy, then the target croup could be described as High Accuracy and High Frequency.  This yielded a Group of higher frequency of contribution and therefore influential, and considered Reliable given their "Useful" rating or Accuracy.  This subset of target Reviewers was then split into paid and unpaid contributors of the same category of yielding high volume and high ranking reviews.
For the final calculation used for comparison the two subsets were filters by 5-Star Reviews as a measure of Bias.

## Results

 The short and condensed summary table below  in Figure 6 shows that, even though the Paid Group of Significant Contributors is much smaller in size with only 107 individuals, in comparison to 39,869 Unpaid Contributors, its behavior measured in Percent 5-star Reviews given is equivalent.  

Figure 6 Amazon Vine 
 
![insert Figure 2](https://github.com/AnaMMoreira/Amazon_Vine_Analysis/blob/main/Figure6_Amazon_Vine_Analysis_Summary.png)

Both Groups have similar generous 5-star distribution rates of 52.7 % and 52.3 % when ranking products.  On the other hand perhaps people in general regardless of what they have to gain from the exercise, are honest and accurate when thinking analytical about product reviews!       

