---
layout: post
title:      "SQLite Basics"
date:       2020-04-15 18:34:58 +0000
permalink:  sqlite_basics
---


This is an overview of the basics of SQL. SQL is used in programming to manage data held in a database. In order to gather the data that we need from the database, we use queries. 

There are four basic types of categories of datatypes:

1) Text - Plain Text
2) Integer - Anthing you want to represent as a whole number.
3) Real =  Anything that's a plain old decimal like 1.3.
4) Blob - Holds binary data.


Creating a database in your terminal:

```
sqlite3 database_name.db
```

Here we are creating table named dogs that will have columns id, name, and age. Id will have the data type of an integer, name will have the data type of TEXT, and age will have the data type of INTEGER. Id will have the PRIMARY KEY added. Primary keys are crucial because it will help distinguish between rows. Every row will have a unqiue id number. This helps distinguish between two rows who might have similar names.

```
CREATE TABLE dogs (id INTEGER PRIMARY KEY, name TEXT, age INTEGER);
```

You can insert data to a table by using INSERT TO. Using the cats table that we just created, lets insert a dog to the table. 

```
INSERT INTO dogs VALUES (1, "riley", 2);
```

In order to alter the table and give it another column, we can use ALTER TABLE. 

```
ALTER TABLE dogs ADD residence TEXT;
```

Using Select to retrieve data:

```
SELECT name FROM dogs;

SELECT name, age FROM dogs;

```

The * opertator signifies ALL. It can be used like this in order to select all the columns from a table:

```
SELECT * FROM dogs;
```

Using WHERE to locate a specific row. In this example, we are going to select all the information from the row that contains the name Rex in a column named name.

```
SELECT * FROM dogs WHERE name = "rex";
```

You can also use math operations like this:

```
SELECT * FROM dogs WHERE age < 2;
```

To drop a table simply:

```
DROP TABLE dogs;
```

And thats it for now! For my next blog post, I will get deeper into SQL.
 


