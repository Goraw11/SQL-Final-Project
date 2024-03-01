What issues will you address by cleaning the data?

Inconsistencies of standardization

The issues to address by cleaning the data are to make the data more user-friendly, usable, and efficient to work with.

Broadly speaking, these were the Data cleaning techniques which I applied:
Missing values - for example, removing NULL entries)
Removing Anamolies - example, removing outliers
Removing duplicates
Data relevance - ensuring that the fields are relevant

Queries:
Below, provide the SQL queries you used to clean your data.

1. From table analytics, to divide the unit price by 1,000,000
   Query used:
   SELECT unit_price / 1000000.0 AS result
FROM analytics;



