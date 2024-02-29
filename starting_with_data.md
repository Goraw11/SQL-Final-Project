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


Question 2: What colour t-shirt is ordered the most?

Query:

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
