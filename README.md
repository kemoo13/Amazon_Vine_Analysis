# Amazon_Vine_Analysis

### Overview
The purpose of this analysis was to perform an analysis of Amazon reviews using the big-data tool PySpark for ETL. Revivews of video games were assessed for star-rating, helpful_votes, and if they were part of the paid Vine program. The data was transformed, connected to an AWS RDS instance and then loaded into pgAdmin to asses for bias using PySpark.

### Resources
Software:
Google Colaboratory (Google Colab Notebook)
PySpark
Amazon Web Services (AWS)
PostgreSQL 12
pgAdmin 4

Data source:
Amazon Review datasets


### Results

The Amazon database for video games was loaded using PySpark. The database contained various information regarding the reviews for each video game. 
<img src="images/Amazon_database.png" width="700">

Tables were then created in PostgreSQL using the following schema:
<img src="images/amazon_schema.png" width="700">

The database was further assessed for information regarding the Vine Program. This is a service in which manufacturers and publishers are allowed to receive reviews in exchange for their products. The program was broken down in to reviews that were and were not part of the Vine program, as well as what percentage of the 5 star reviews were part of the program. 

The tables produced were as follows:
<img src="images/customer_table.png" width="700">
<img src="images/product_table.png" width="700">
<img src="images/review_table.png" width="700">
<img src="images/vine_table.png" width="700">

The data was then filtered to loaded in to a second Google Colaboratory notebook and the data was further filtered for reviews where the total_votes count is equal to or greater than 20. The votes were then further analyzed by finding reviews where the number of 'helpful_votes' divided by 'total_votes' is equal to or greater than 50%. The result:
<img src="images/helpful_votes_count.png" width="700">

The number of these votes that are part of the vine program were found as follows:
<img src="images/vine_program.png" width="700">

This resulted in 94 reviews as part of the vine program. The number of reviews that were not part of the vine program were found in a similar manner, with a total of 15,663.

The total number of 5-star reviews was collected from the data and further divded in to 'paid' and 'not paid' to indicate whether they were part of the Vine program or not. 
<img src="images/unpaid_5_reviews_code.png" width="700">
<img src="images/paid_5_review_code.png" width="700">

To determine if there was any bias in the Vine program, the percentage of Vine 5-star reviews and non-Vine 5-star reviews were calculated.
<img src="images/percentage_reviews.png" width="700">

### Summary
The analysis has shown that there is not a bias toward 5-star reviews coming from the Vine program. In fact, the data has shown the opposite with a surprising 99.69% of the votes not being part of the Vine program. There is a possibility that this is due to the small portion of the Vine program being analyzed. The database consisiting of video game reviews is only a small subset of the Vine program. In order to get an accurate idea as to whether there is bias within the Amazon Vine program, each category would need to analyzed.
