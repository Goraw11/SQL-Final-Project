# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals

This data shows sales related information for a company, including how their clients interacted with them on their website.
My goals with this project were as follows:
1. To understand the data
2. To answer the pre-set questions
3. To have additional insights from the data
4. Having insights from the data, then deciding what are more relevant business questions I can ask this data, and, how can the answers to these questions help this business.

This data shows, among other things, current sales trends, marketing trends, how customers are interacting with the website (including how much time they're spending on the website), etc.

## Process

In this project, I have:
1. Imported the 5 csv files into a database called ecommerce on my PGAdmin (by creating tables, then creating columns, and then extrapolating from CSV to PGAdmin).
2. After this, I:
a. Reviewed the data
b. Conducted data cleaning and scrubbing by employing various queries (I've provided some of my queries in the related documents, for example in the cleaning_data.md file)
3. Answered the required questions
4. Conducted further analysis of the data to get more insights
5. Created some questions myself, which I also then answered using SQL Queries (the intent of the questions I came up with, was with a view of helping the business become more efficient).
        

## Results
Based on my queries, I see that this company does business all over the world. This also means that the marketing spend goes globally. One of my questions was, which cities have the lowest number of customers.
```SQL
SELECT "city", COUNT("fullvisitorid") AS "CustomerCount"
FROM "all_sessions"
GROUP BY "city"
HAVING COUNT("fullvisitorid") < 5
ORDER BY "CustomerCount" DESC;
```

This query returns over 150 cities where they have fewer than 5 customers. 
My recommendation would be to have a plan where they either stop selling to these cities, thus hugely saving on the marketing spend and shipping costs for those areas, or, to have some plan in place. With limited resources and a focus on growth, the company should focus on cities where they have most customers.

This query shows cities with the most customers:
```SQL
SELECT "city", COUNT("fullvisitorid") AS "CustomerCount"
FROM "all_sessions"
GROUP BY "city"
ORDER BY "CustomerCount" DESC
LIMIT 5;
```


## Challenges 
There were a lot of challenges on this project:
1. Being my first SQL project, I had a lot of new learning.
2. Getting used to the tools, including to github.
3. Converting data from csv to PGAdmin seemed like a challenging task until I figured out how to do it.
4. Cleaning the data and to figure out what NOT to remove (As it may be relevant).
5. Scrubbing the data to figure out what's important.

## Future Goals
If I had more time with this data, I would look for more ways for the company to:
1. Save money (streamlining shipping, reducing marketing spend on low-perforing markets, etc.)
2. Save time by becoming efficient.
3. Add convenience to their customers by figuring out ways to make shopping on their e-commerce site even easier.
4. Finding opportunities to cross-sell to those customers who spend a lot of time the company website.
