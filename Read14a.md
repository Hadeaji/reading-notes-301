# DB Normalization

## What is the DB Normalization?

is a process used to organize a database into tables and columns.

## Why Would You Do It

1. when you do it you will be reducing the amount of duplicated data and save space
2. you will avoid a lot of data modification issues
3. It will be easier for you to get the data and search through the DB

## Data Duplication and Modification Anomalies

The Problems Of Duplicated:

1. It increases storage and decrease performance.
2. It becomes more difficult to maintain data changes due to amount of same data

## modifications

When inserting, updating or deleting some info it is always causes some kind of harm to the database in case of insiting lets say if you need an exact id to add to but there is incomplate data their or whanted to delete a cell but you will have to delete the whole row..etc..

## Search and Sort Issues

> EX:

`SELECT SalesOffice`
`FROM SalesStaff`
`WHERE Customer1 = ‘Ford’ OR`
      `Customer2 = ‘Ford’ OR`
      `Customer3 = ‘Ford’`

The customer info is divided into many columns so it would be really troublesome to get his data or sort by it

## database normalization

1. ***First Normal Form*** – The information is stored in a relational table where There are no repeating groups of columns.

2. ***Second Normal Form*** – The table is in first normal form and all the columns depend on the table’s primary key.

3. ***Third Normal Form*** – the table is in second normal form and all of its columns are not transitively dependent on the primary key

Easy Enough Right? Cool.
