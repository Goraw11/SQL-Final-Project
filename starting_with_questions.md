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
SELECT
    City,
    Country,
    v2productCategory,
    COUNT(*) AS OrderCount
FROM
    all_Sessions
GROUP BY
    City,
    Country,
    v2productCategory
ORDER BY
    City,
    Country,
    OrderCount DESC;

Answer:
Yes, there is a pattern in the types of products ordered from visitors in each city and country.
We see that "Home/Shop by Brand/YouTube/" is the most popular product category.
followed by Home/apparel and the 3rd most ordered is home/drinkware



**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:
SELECT city, country, SUM(productquantity) AS quantity_sold
FROM all_sessions
GROUP BY city, country
ORDER BY quantity_sold DESC;

Answer:
Based on the above query, we see that customers Kharagpur in India and Stanford in the USA have ordered the most.

**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:
SELECT city,
        SUM(transactionrevenue) AS total_revenue
    FROM all_sessions
    GROUP BY city
ORDER BY total_revenue DESC;

Answer:
Yes, we can. We can derive a list of cities where most of the customers live in, in a descending order.




