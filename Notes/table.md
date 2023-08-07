# table in a database

## What is a table in a database?

- is an organized collection of data within a computer system that can be relational or non-relational.
- Relational databases organize data using tables.
- non-relational databases store information in a more dispersed manner, organizing it into collections.
- A table is a basic element of a relational database. It stores data in a tabular format, which means the system organizes data into rows and columns.
- tables are similar to folders because they store information, they're different in that each table stores information about a specific subject.
- A column is a vertical set of data within a table that contains various attributes or fields ,There are three main types of data that you can store in database columns, including **numerical, text, and date/time**.
- Columns are useful because they allow you to sort and filter data in a table.
- A row in a database table represents a single entry and contains data corresponding to the columns in the table.

## Primary key

- A primary key is a column or set of columns that **contains a unique value** for each row in the table, This value can be a number, a letter, or a combination of both
- Primary keys are useful for identifying table rows and ensuring that no two rows contain the same data
- The primary key is usually the first column in a table
- also known as a primary attribute or unique key.
- can **only be one primary key that users can't change** in a table, and it **can't be null**

## Foreign key

- A foreign key is a column or set of columns in a table containing values that match the primary key of another table
- It helps establish relationships between tables in a database
- A foreign key can be null.
- There can be more than one foreign key in a table.
- The table with the foreign key is the child table, and the one containing the
- primary key is the parent table.
- The values in a foreign key column can be duplicates

## Relationships between tables

- relationships are connections between two or more tables. These are important because they allow you to query data from multiple tables and combine these in a single result.
- They also help establish meaning and organize data in a database in a way that makes sense to users.

### There can be multiple relationships between tables in a database, and these can be any of these three types

- One-to-one
  - This describes a link between two tables, where one record or row in the first table connects to exactly one record or row in the second.

- One-to-many
  - one record in the first table can relate to multiple records or rows in the second table.

- Many-to-many
  - multiple records in the first table can relate to multiple records in the second table and vice versa.
