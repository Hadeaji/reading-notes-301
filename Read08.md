# SQL

## Introduction to SQL

What is SQL?
Means Structured Query Language

It is simple language that allow programers to easily transform data to and from databases using the relational databases

The relational database represents a collection of related (two-dimensional) tables similar to Excel sheets.

## SQL Lesson 1: SELECT queries 101

when you want to call it you have to use the SELECT statment to call the data from their specefic sheet

EX:

`SELECT Title, Year`
`FROM movies;`

the most basic query we could write would be one that selects for a couple columns (properties) of the table with all the rows (instances).

You can use the `*` to call all the info in your database

## SQL Lesson 2: Queries with constraints (Pt. 1)

In case you data base contain a Huge number of columns and rows and you want to reduse the results in order to find the ones you need you can use the `WHERE` statment

it i really similar to the if statment in JS 
and her ethe Operators you can use in it

![ex](/files/Read08-1.png)

EX:

`SELECT *`
`FROM movies`
`WHERE year BETWEEN 2000 And 2010`

used to get the movies between 2000 and 2010

## SQL Lesson 3: Queries with constraints (Pt. 2)

You can also use `WHERE` for the case-insensitive string comparison

And here is the Operators you will need

![ex](/files/Read08-2.png)

EX:

`SELECT *`
`FROM movies`
`WHERE title LIKE "WALL-_";`

The example used to get all the movies that begain with WALL- and missing one character

## SQL Lesson 4: Filtering and sorting Query results

In case of huge amount of data their is a chance the the data have the same properties in some columns and here comes the job of the `DISTINCT` statment

the DISTINCT keyword will blindly remove duplicate rows. :)

EX:

`SELECT DISTINCT director`
`FROM movies`
`ORDER BY director;`

this will list all directors without duplicates

---------
> You can also use the `ORDER BY` clause in order to order your table in an ascending or descending order

often the `LIMIT` and `OFFSET` clauses are used with the `ORDER BY` clause to limit the rows number and chossing the starting point

EX:

`SELECT title`
`FROM movies`
`ORDER BY title ASC`
`LIMIT 5 OFFSET 5;`

This will list 5 movies sorted alphabetically starting after first 5

## SQL Lesson 13: Inserting rows

But how can you add to the data?

### What is a Schema?

> schema is what describes the structure of each table, and the datatypes that each column of the table can contain.

we need to use an `INSERT` statement, which declares which table to write into, the columns of data that we are filling, and one or more rows of data to insert.

So without further talking let's see and Example:

`INSERT INTO movies`
`VALUES (4, "Toy Story 4", "El Directore", 2015, 90);`

in this example we added 4 values to a predefined columns the movide name ,Director ,Year and Length_minutes.

## SQL Lesson 14: Updating rows

Now we know how to add but how can we `UPDATE` ?

The `UPDATE` statement is Similar to the `INSERT` you have to specify exactly which table, columns, and rows to update.

**Important Note:** the data you are updating has to match the data type of the columns in the table schema.

EX:

`UPDATE movies`
`SET title = "Toy Story 3", director = "Lee Unkrich"`
`WHERE id = 11;`

In this Ex we have updated the title and director to the row that have the id 11

## SQL Lesson 15: Deleting rows

My favorite statment: `DELETE`
use the `WHERE` to choose some values or dont to clear the whole database

`DELETE FROM movies`
`where year < 2005;`

Deleted every row that have a lower year value than 2005

## SQL Lesson 16: Creating tables

To create New databases use `CREATE TABLE` statment and dont forget to use `IF NOT EXISTS` so you avoid errors if you already have the database

When you want to create it you have to specify Each column name, the type of data allowed in that column, an optional table constraint on values being inserted, and an optional default value.

here is the table of Data Type:

![ex](/files/Read08-3.png)

and a table of table constraints:

![ex](/files/Read08-4.png)

## SQL Lesson 17: Altering tables

You can use the `ALTER TABLE` statement to add, remove, or modify columns and table constraints of your corresponding tables.

Adding columns,
Ex:

`ALTER TABLE mytable`
`ADD column DataType OptionalTableConstraint`
    `DEFAULT default_value;`

Removing columns,Ex:

`ALTER TABLE mytable`
`DROP column_to_be_deleted;`

Renaming the table,Ex:

`ALTER TABLE mytable`
`RENAME TO new_table_name;`

## SQL Lesson 18: Dropping tables

Now for the good stuff, when you rage quit and want to delete everything 

USE `DROP TABLE` statement, which differs from the `DELETE` statement in that it also removes the table schema from the database entirely.

EX:

`DROP TABLE IF EXISTS mytable;`
