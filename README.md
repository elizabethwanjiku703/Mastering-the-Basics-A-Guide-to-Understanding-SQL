# Introduction
Welcome to my inaugural post on SQL basics! In this beginner-friendly guide, we'll explore the essential concepts of using the SQL statements in SQL to retrieve and manipulate data from databases. Whether you're new to SQL or looking to refresh your querying skills, this post is designed to provide you with a solid foundation in SQL queries. 
I've curated this content based on my learnings from reputable source [Mode's SQL Tutorial](https://mode.com/sql-tutorial). I encourage you to click on the shared link to delve deeper into the topics and expand your knowledge.
## SQL SELECT
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
> In this query, SELECT helps you pick the "year" column, and FROM tells the database to look for this information in the learning_sql table.

### Selecting All Columns
Now, let's talk about the wildcard symbol. When you use, it's like saying, "Show me everything!" It selects all columns from the specified table, giving you a comprehensive view of the data. For instance, if you want to see all the details of housing units, you can use * to select all columns:
```
SELECT *
FROM learning_sql.us_housing_units;
```
![Select_2](https://github.com/elizabethwanjiku703/Mastering-the-Basics-A-Guide-to-Understanding-SQL/blob/main/Select_2.JPG)
> This query will fetch all columns (such as year, month, month_name, etc.) from the "learning_sql" table, providing a complete snapshot of each housing's information.

### Using Aliases with AS
Now, let's introduce the concept of aliases. When you use AS in SQL, it's like giving a column a nickname. This can be handy for renaming columns or making the output more readable. For example, if you want to rename the "year" column as "Year" in your query, you can do so using AS:
```
SELECT	year AS Year, 
	month AS Month, 
	month_name AS Month_Name
FROM learning_sql.us_housing_units;
```

![Select_3](https://github.com/elizabethwanjiku703/Mastering-the-Basics-A-Guide-to-Understanding-SQL/blob/main/Select_3.JPG)
Also, at some point you might forget using the AS when writing your query in such a case, you can do the following;

```
SELECT year "Year", month "Month"
FROM learning_sql.us_housing_units;
```

![Select_4](https://github.com/elizabethwanjiku703/Mastering-the-Basics-A-Guide-to-Understanding-SQL/blob/main/Select_4.JPG)
> As you can see, the results are the same as using aliases, but I think due to readability it's better to us AS
By mastering the art of using SELECT and FROM in SQL queries, you gain the power to retrieve and display data in a way that suits your needs, making data manipulation a breeze.

## SQL LIMIT
The LIMIT statement in SQL is used to restrict the number of rows returned by a query. It is particularly useful when you want to see only a certain number of rows from a result set, especially when dealing with large datasets. Here's a simple explanation of how the LIMIT statement works:
Imagine you have a table with a lot of rows, but you are only interested in seeing the first few rows. You can use the LIMIT statement to specify the maximum number of rows you want to retrieve from the database.
For example, if you want to see only the first 15 rows of a table, you can use the LIMIT statement like this:

```
SELECT * 
FROM learning_sql.us_housing_units
LIMIT 15;
```

![Limit_1](https://github.com/elizabethwanjiku703/Mastering-the-Basics-A-Guide-to-Understanding-SQL/blob/main/Limit_1.JPG)

This query will return only the first 15 rows from the "learning_sql.us_housing_units" table. You can adjust the number in the LIMIT statement to retrieve a different number of rows based on your needs.
Also, you can limit the rows if you are using the MySQL Workbench on topo of the script editor, you can see somoething written **"Don't Limit"** as shown on the picture below. 

![Limit_2](https://github.com/elizabethwanjiku703/Mastering-the-Basics-A-Guide-to-Understanding-SQL/blob/main/Limit_2.jpg)

> In summary, the LIMIT statement is a simple and effective way to control the number of rows returned by a query, making it easier to work with large datasets and focus on the specific data you need.

## SQL WHERE
The SQL WHERE clause is like a filter that helps you find specific rows in a database table that meet certain conditions. It allows you to narrow down your search and retrieve only the data that matches the criteria you specify.
Here's a simple explanation of how the WHERE clause works:
Imagine you have a table with a lot of rows, but you are interested in finding rows that meet specific conditions, such as employees with a certain job title or customers from a particular city. This is where the WHERE clause comes in. When you use the WHERE clause in a SQL query, you can add conditions that the rows must satisfy to be included in the result set. For example, if you want to find all housing units where the month_name was "I",, you can write a query like this:
- Please note if the where statement is accompanied by a number then no need to use parentheses.

```
SELECT *
FROM learning_sql.us_housing_units
WHERE month = 1
```

The results would look like this:

![Where_1](https://github.com/elizabethwanjiku703/Mastering-the-Basics-A-Guide-to-Understanding-SQL/blob/main/Where_1.JPG)

When writing a WHERE statement with a name (not a number), it is important to use parentheses. For example, if you want to find all housing units where the month_name is 'January', you should write the query like this:

```
SELECT *
FROM learning_sql.us_housing_units
WHERE month_name = "January";
```

![Where_2](https://github.com/elizabethwanjiku703/Mastering-the-Basics-A-Guide-to-Understanding-SQL/blob/main/Where_2.JPG)

> Note that when using MySQL Workbench, it is crucial to use double parentheses for conditions like column names to avoid errors. Paying attention to these details can help prevent common mistakes that may occur during query writing. 
