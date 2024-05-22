# Introduction
Welcome to my inaugural post on SQL basics! In this beginner-friendly guide, we'll explore the essential concepts of using the SQL statements in SQL to retrieve and manipulate data from databases. Whether you're new to SQL or looking to refresh your querying skills, this post is designed to provide you with a solid foundation in SQL queries. 
I've curated this content based on my learnings from reputable source [Mode's SQL Tutorial](https://mode.com/sql-tutorial). I encourage you to click on the shared link to delve deeper into the topics and expand your knowledge.
## SELECT statement for retrieving data
In SQL, the SELECT statement is like a magic wand that helps you fetch data from a database. Imagine it as a tool that allows you to pick and choose exactly what information you want to see. When you use **SELECT** in a query, you are telling the database, "Hey, show me these specific columns or pieces of data." It's like creating a shopping list where you only write down the items you need from the store. Now, let's talk about the FROM part. The FROM statement tells the database where to look for the data you want. It's like giving directions to a treasure hunter, guiding them to the right location where the treasure is buried. So, when you combine **SELECT and FROM** in a query, you are essentially saying, "I want to see these specific pieces of information, and I want to find them in this particular place."
### Selecting Specific Columns
When you use SELECT in a query, you are essentially creating a customized view of your data. You can specify which columns you want to see by listing their names after the SELECT keyword. It's like handpicking the pieces of information that matter to you. For example, if you want to see the year of all the Housing Unit Table from the [U.S. Census Website](https://www.census.gov/econ/currentdata/), you would use SELECT to choose the **"year"** column and FROM to specify the **"learning_sql.us_housing_units"** table as shown below;
> Kindly note, I used MySQL Workbench and thus I saved my table as learning_sql. You can use any name when creating a schema.
The query would look something like this:
```
SELECT year
FROM learning_sql.us_housing_units;
```
![Schema](https://github.com/elizabethwanjiku703/Mastering-the-Basics-A-Guide-to-Understanding-SQL/blob/main/Schema.JPG)
![Select_1](https://github.com/elizabethwanjiku703/Mastering-the-Basics-A-Guide-to-Understanding-SQL/blob/main/Select_1.JPG)

