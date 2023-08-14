# SQL SELECT Statement

- The SELECT statement is used to select data from a database.
- SELECT column1, column2, ... FROM table_name;
- SELECT * FROM table_name;

```sql
SELECT CustomerName, City FROM Customers;
SELECT * FROM Customers;
```

---

- to get all the columns from the Customers table.

```SQL
SELECT * FROM Customers;
```

---

- Write a statement that will select the City column from the Customers table.

```SQL
SELECT city from Customers;
```

## SQL SELECT DISTINCT Statement

- The SELECT DISTINCT statement is used to return only distinct (different) values.
- Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.
- SELECT DISTINCT column1, column2, ... FROM table_name;

- selects only the DISTINCT values from the "Country" column in the "Customers" table:

```sql
SELECT DISTINCT Country FROM Customers;
```

## The SQL SELECT TOP Clause

- The SELECT TOP clause is used to specify the number of records to return.

- The SELECT TOP clause is useful on large tables with thousands of records. Returning a large number of records can impact performance.
- SELECT TOP number|percent column_name(s) FROM table_name WHERE condition;

```SQL
SELECT TOP 3 * FROM Customers;
SELECT TOP 50 PERCENT * FROM Customers;
SELECT * FROM Customers FETCH FIRST 50 PERCENT ROWS ONLY;
SELECT TOP 3 * FROM Customers WHERE Country='Germany';
```

- SELECT column_name(s) FROM table_name WHERE condition LIMIT number;

```SQL
SELECT * FROM Customers
WHERE Country='Germany'
LIMIT 3;
```

## SQL BETWEEN Operator

- The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.

- The BETWEEN operator is inclusive: begin and end values are included.

- SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value1 AND value2;

```sql
SELECT * FROM Customers WHERE salary between 1500 and 3500;
```

## SQL IN Operator

- The IN operator allows you to specify multiple values in a WHERE clause.

- The IN operator is a shorthand for multiple OR conditions.
- SELECT column_name(s) FROM table_name WHERE column_name IN (value1, value2, ...);

```sql
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');
```
