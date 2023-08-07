# Introduction to database

- A relational database is a collection of data with a structure that allows you to search and access related information or data points. It primarily consists of tables that organize and display data in a way that makes it easy for people to use.
- is usually controlled by a database management system (DBMS)
- A DBMS serves as an interface between the database and its end users or programs, allowing users to retrieve, update, and manage how the information is organized and optimized

## What Is an RDBMS?

- relational database management system
- is a database of items that stores data based on how the items relate to one another in the system.
- RDBMS programs typically store data in the form of rows in a table in which you can find the specific information you want.

### Characteristics of an RDBMS

- Format of the system
  - An RDBMS organizes data items and data sets into rows and columns in a table. Each column corresponds to a category, and the rows identify each data item in the set. It organizes information in a way that users can easily identify how the data items in the table relate to each other. Having a structured format makes it easier for users to understand, run queries, and isolate information in the overall complex data set. You can also easily manipulate the data in the rows and columns using various commands to transform the data into usable information for other computer systems.

- Relationship between data items
  - An RDBMS organizes data items in a table according to each item's relationship with the other items. The data set has various characteristics and traits that help users identify the organization of the data items within the RDBMS.

- Consistency
  - Relational databases show consistency throughout each transaction completed in the RDBMS. Consistency means that the rules and defining characteristics within the relational database remain the same throughout all the data points and after each transaction or query. It's also beneficial for users to work with consistent data across the relational database because the information updates across all the applications and programs. This means that users have access to the same data sets regardless of the commands or queries they run.

## Data Definition Language (DDL)

- Data Definition Language (DDL) is used to create and modify the structure of objects in a database using predefined commands and a specific syntax. These database objects include tables, sequences, locations, aliases, schemas and indexes.

- 1. CREATE Syntax
  - CEATE DATABASE IF NOT EXISTS employees CHARACTER SET = utf8 COLLATE utf8_general_ci;

- 2. ALTER Syntax
  - ALTER DATABASE IF NOT EXISTS company CHARACTER SET = utf8 COLLATE utf8_general_ci;

- 3. DROP Syntax
  - DROP DATABASE IF NOT EXISTS company;
  - DROP DATABASE company;

## Relational databases vs. non-relational databases

- A non-relational database stores and retrieves displayed and organized data, which may have no relation to each other, outside of a table format.
- sometimes faster to perform queries with a non-relational database than with a relational database because the system only uses the same document to deliver an answer.
