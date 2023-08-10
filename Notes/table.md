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

## Data Definition Language (DDL)

- Data Definition Language (DDL) is used to create and modify the structure of objects in a database using predefined commands and a specific syntax. These database objects include tables, sequences, locations, aliases, schemas and indexes.

- 1. CREATE Syntax
  - CEATE TABLE [IF NOT EXISTS] TBL_NAME CHARACTER SET = utf8 COLLATE utf8_general_ci
  - CEATE TABLE [IF NOT EXISTS] TBL_NAME LIKE TBL_NAME
  - CEATE TABLE [IF NOT EXISTS] TBL_NAME SELECT_STMT

  ```SQL
   CREATE TABLE employees(
    -> emp_id SMALLINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
    -> dob date not null,
    -> address VARCHAR(50) NOT NULL,
    -> salary DECIMAL(7,2) DEFAULT 1500.00,
    -> gender ENUM('Male','Female') NOT NULL DEFAULT'Male',
    -> position VARCHAR(20) NOT NULL, 
    -> serial_number CHAR(30) NOT NULL);
  ```

- 2. ALTER Syntax
  - ALTER TABLE [IF NOT EXISTS] TBL_NAME CHARACTER SET = utf8 COLLATE utf8_general_ci
  - ADDING NEW COLUMNS:
    - ALTER TABLE TBL_NAME ADD COLUMNS COL_NAME (DATA TYPE) [ATRIBUTE] [Constraints]
  - MODIFYING EXISTING COLUMNS:
    - ALTER TABLE TBL_NAME MODIFY COLUMNS COL_NAME (DATA TYPE) [ATRIBUTE] [Constraints]
  - CHANGING EXISTING COLUMNS:
    - ALTER TABLE TBL_NAME CHANGE COLUMNS OLD_COL_NAME NEW_COL_NAME (DATA TYPE) [ATRIBUTE] [Constraints]
  - DELETINNG A COLUMN:
    - ALTER TABLE TBL_NAME DROP COLUMNS COL_NAME

- 3. DROP Syntax
  - DROP TABLE [IF NOT EXISTS] TBL_NAME
  - DROP TABLE TBL_NAME

- 4. RENAME Syntax
  - RENAME TABLE OLD_TBL_NAME TO NEW_TBL_NAME
  