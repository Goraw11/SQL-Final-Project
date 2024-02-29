Self-Generated questions:

Question 1: Show a list of the top 5 cities where most customers live.

Query:
```SQL
SELECT "city", COUNT("fullvisitorid") AS "CustomerCount"
FROM "all_sessions"
GROUP BY "city"
ORDER BY "CustomerCount" DESC
LIMIT 5;
```

Answer: 
1. Name not available
2. Mountain View
3. New York
4. San Fransisco
5. Sunnyvale


Question 2: Show a list of items with more than 5000 units in the warehouse. We can use this data to offer offer any sales or discounts on these items to incentivize customers to purchase them. We can do this to free up warehouse space to stock up on items which generate most revenue.

Query:
```SQL
SELECT "name", "stocklevel"
FROM "sales_report"
WHERE "stocklevel" > 5000 
order by "stocklevel" DESC;
```

Answer:


Question 3: Customers from which countries spend the most time on the website?

Query:

Answer:



Question 4: Customers spend most time looking at which items on the website?

Query:

Answer:



Question 5: Show a list of top 5 items with the highest sentiment scores.

Query:

Answer:
