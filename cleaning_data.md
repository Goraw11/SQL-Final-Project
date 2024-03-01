What issues will you address by cleaning the data?

In reference to the table: all_sessions

Null Fields - This was a major issue in this data set.
There are hundreds of null fields, especially in columns: city (not available in demo dataset), totalTransactionRevenue, transactions, 

For example, 
```SQL
SELECT *
FROM all_sessions
WHERE totalTransactionRevenue
IS NOT NULL;
```

How much $$$ the company made in terms of transaction revenue is a very important piece of data, however, running the above query, we see that out of 15133 fields, only 81 have a value attached in "totalTransactionRevenue" - this limits our understanding of total transaction revenue almost to a negligible level.

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



