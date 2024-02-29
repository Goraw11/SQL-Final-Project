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


Question 2: Show a list of items with more than 5000 units in the warehouse. [The company can use this data to offer offer any sales or discounts on these items to incentivize customers to purchase them. We can do this to free up warehouse space to stock up on items which generate most revenue.]

Query:
```SQL
SELECT "name", "stocklevel"
FROM "sales_report"
WHERE "stocklevel" > 5000 
order by "stocklevel" DESC;
```

Answer:
We see that we have several thousand quanities of the below 3 items:
22 oz Water Bottle
Sunglasses
Spiral Notebook and Pen Set

Question 3: Show top 5 best-rated products

Query:
```SQL
SELECT sentimentscore, total_ordered, name
FROM "sales_report"
ORDER BY "sentimentscore" DESC
LIMIT 5;
```

Answer:
This company has several items which receive amazing reviews from it's customers, however, here's the top 5 products which receive the best ratings:
1. Recycled Paper Journal Set
2. Stylus Pen w/LED Light
3. Men's 100% Cotton Short Sleeve Hero Tee White
4. Metal Texture Roller Pen
5. Men's Short Sleeve Hero Tee Charcoal


Question 4: Show a list of cities which have less than 5 customers. [The company may use this information to reduce their marketing spend in these cities, as, they already do not have many customers this. This would also help to reduce shipping costs for the company]

Query:
```SQL
SELECT "city", COUNT("fullvisitorid") AS "CustomerCount"
FROM "all_sessions"
GROUP BY "city"
HAVING COUNT("fullvisitorid") < 5
ORDER BY "CustomerCount" DESC;
```

Answer:
This shows us a list of over 156 cities! The company can save a lot by reducing their marketing spend in these cities, and save on shipping costs. The company may also consider to altogether stop selling in these geographies.
Here's a list of the top 5 cities with less than 5 customers each.
1. Karachi	4
2. Pozuelo de Alarcon	4
3. Riyadh	4
4. Zhongli District 4
5. Maracaibo	4


Question 5: Show a list of top 5 items with the highest sentiment scores.

Query:

Answer:
