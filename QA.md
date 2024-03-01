What are your risk areas? Identify and describe them.

1. Removing NULL Values:
One can easily insert the code below, and have hundreds of NULL values removed within miliseconds.
```SQL
SELECT *
FROM all_sessions
WHERE totalTransactionRevenue
IS NOT NULL;
```
However, we have to consider the risks:
This will remove the entire row, which obviously has lots of other data in other cells. As such, by removing 1 column of NULL values over hundreds of rows, we risk loosing hundreds of important values - we must do this extremely carefully, and, only if 100% confident that we won't loose other relavant data.


2. Duplicates:
We can easily remove all duplicates, in all columns, with easy query such as this one:
```SQL
DELETE FROM all_sessions
WHERE (fullVisitorId) IN 
(SELECT fullVisitorId
    FROM all_sessions
    GROUP BY fullVisitorId
    HAVING COUNT(*) > 1)
```
However, just like in the first point above, we risk loosing relevant data, which would be in the related fields. Again, this is a risk and needs to be undertaken only if one is very certain that they won't loose crucial values from the related fields.

3. Human / Data Entry errors:
There may be values which do not "look" right. For example, in the productSKU column, I found values that were:
a. Had 14 charecters
b. Had only 7 Charecters
c. Were alphanumeric
D. Only had numbers

In this example query, we can see the minimum and maximum charecter lenght:
```SQL
SELECT *
FROM all_sessions
WHERE productRefundAmount
IS NOT NULL;
```
This again tends to be a risk, as, we do not know if the entries were made erroneously, or, are intentionally that way.

We have several areas of risk in this data:
1. Current sales trends: What kind of impacts can these current sales trends have on the company, specifially on the logitstics, the supply-chain of the company.

2. What kind of impact can these current trends have on our manufacturing and operations, and how can we mitigae those risks.

3. 

QA Process:
Describe your QA process and include the SQL queries used to execute it.
From the table analytics, to divide the unit price by 1,000,000 
Query used: 
```SQL
SELECT unit_price / 1000000.0 
AS result FROM analytics;
```
