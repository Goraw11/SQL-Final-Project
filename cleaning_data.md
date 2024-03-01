What issues will you address by cleaning the data?

Above are some of the Data cleaning techniques which I applied, which helped me to:
1. Removing NULL values
2. Removing Inconsistencies to standardization
3. Removing duplicates
4. Data relevance - ensuring that the fields are relevant

In reference to the table: all_sessions


1. Removing NULL values
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

Another example is the productRefundAmount field.
```SQL
SELECT *
FROM all_sessions
WHERE productRefundAmount
IS NOT NULL;
```
The above query shows us that out of the 15133 fields, 0 fields have a value in the productRefundAmount column. We do not know if we need to assume, that absolutely no customers ever asked for a refund (extremely unlikely), or, if the data is just entirely missing. Either way, this can limit us from making important business decisions.

2. Removing Inconsistencies to standardization
There were also a lot of inconsistencies in the data.
For example, a simple field, productSKU, should be uniform in terms of the total number of charecters, and it's format (for example ABC123456). Here, neither the lenght, nor the format was uniform.
```SQL
SELECT MIN(LENGTH(productSKU)) AS min_length,
       MAX(LENGTH(productSKU)) AS max_length
FROM all_sessions;
```
We suspect that this could be because of a entry error or some type of human error. Either way, this data doesn't help us derive a lot of understanding, as it's inconsisten.

3. Removing duplicates
I used the below query to remove duplicates from the 'fullVisitorId' column. [This removed over 900 duplicate entries]
```SQL
DELETE FROM all_sessions
WHERE (fullVisitorId) IN 
(SELECT fullVisitorId
    FROM all_sessions
    GROUP BY fullVisitorId
    HAVING COUNT(*) > 1)
```

Similarly, I used the below query in the column 'visitId' in order to remove duplicates from that column. [This removed 8 duplicate entries] 
```SQL
DELETE 
FROM all_sessions
WHERE (visitId) IN 
(SELECT visitId
    FROM all_sessions
    GROUP BY visitId
    HAVING COUNT(*) > 1)
```


5. Data relevance - ensuring that the fields are relevant


One of the pre-set data cleaning, which was provided in this project, was, from table "analytics", to divide the unit price by 1,000,000
I have applied the below query to solve for this:
```SQL
SELECT unit_price / 1000000.0 AS result
FROM analytics;
```


In conclusion,
The issues to address by cleaning the data are to make the data more user-friendly, usable, and efficient to work with, all of which have been addressed above.
