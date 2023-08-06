# Introduction to database

- A database is an organized collection of structured information, or data, typically stored in a computer system.

- is usually controlled by a database management system (DBMS)

- A DBMS serves as an interface between the database and its end users or programs, allowing users to retrieve, update, and manage how the information is organized and optimized

## Data Definition Language (DDL)

- Data Definition Language (DDL) is used to create and modify the structure of objects in a database using predefined commands and a specific syntax. These database objects include tables, sequences, locations, aliases, schemas and indexes.

- 1. CREATE Syntax
  - CEATE DATABASE IF NOT EXISTS employees CHARACTER SET = utf8 COLLATE utf8_general_ci;

- 2. ALTER Syntax
  - ALTER DATABASE IF NOT EXISTS company CHARACTER SET = utf8 COLLATE utf8_general_ci;

- 3. DROP Syntax
  - DROP DATABASE IF NOT EXISTS company;
  - DROP DATABASE company;
  