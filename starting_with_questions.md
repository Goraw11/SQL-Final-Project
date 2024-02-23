Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
SELECT
  city,
  country,
  SUM(totaltransactionrevenue) AS total_revenue
FROM all_sessions
WHERE totaltransactionrevenue IS NOT NULL
  AND city != 'Unknown'
GROUP BY city, country
ORDER BY total_revenue DESC;

Answer: 
Based on the above query, we see USA is the highest spender on this website.
6 out of the top 7 spenders are cities in the USA - 6th highest spender being Tel Aviv in Israel.




**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:
SELECT
  city,
  country,
  AVG(totaltransactionrevenue) AS avg_products_ordered
FROM all_sessions
GROUP BY city, country;



Answer:
We see that top 3 cities where the products were sold were as follows:
San Francisco
Kharagpur
Stanford




**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:



Answer:





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:



Answer:





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:



Answer:



Self-Generated questions:
1. What products are ordered the most:
   Code: select *
from sales_report
order by total_ordered DESC

2. 



