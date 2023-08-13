# DML Data Manipulation Language

- INSERT
- UPDATA
- DELET
- SELECT

## The SQL INSERT INTO Statement

- The INSERT INTO statement is used to insert new records in a table.

```sql
 use store;

 SHOW TABLES;
+----------------------+
| Tables_in_store      |
+----------------------+
| customers_products   |
| products             |
| products_orders      |
| products_orders_list |
| users                |
| users_profiles       |
+----------------------+

 describe users;
+-----------+--------------+------+-----+---------+----------------+
| Field     | Type         | Null | Key | Default | Extra          |
+-----------+--------------+------+-----+---------+----------------+
| user_id   | int unsigned | NO   | PRI | NULL    | auto_increment |
| username  | varchar(30)  | NO   |     | NULL    |                |
| password  | char(72)     | NO   |     | NULL    |                |
| lastlogin | datetime     | YES  |     | NULL    |                |
| privilege | tinyint(1)   | YES  |     | 2       |                |
+-----------+--------------+------+-----+---------+----------------+

INSERT INTO users(username, password,lastlogin,privilege) VALUES('mohamed ',md5('yahia'),now() ,1);

SELECT * FROM users;
+---------+----------+----------------------------------+---------------------+-----------+
| user_id | username | password                         | lastlogin           | privilege |
+---------+----------+----------------------------------+---------------------+-----------+
|       1 | mohamed  | 64832d781603ac2e962874ac918ad155 | 2023-08-11 01:52:12 |         1 |
+---------+----------+----------------------------------+---------------------+-----------+

INSERT INTO users SET  username = 'ahmed',password = md5('ibrahim'), lastlogin = now(),privilege = 2;

 SELECT * FROM users;
+---------+----------+----------------------------------+---------------------+-----------+
| user_id | username | password                         | lastlogin           | privilege |
+---------+----------+----------------------------------+---------------------+-----------+
|       1 | mohamed  | 64832d781603ac2e962874ac918ad155 | 2023-08-11 01:52:12 |         1 |
|       2 | ahmed    | f1c083e61b32d3a9be76bc21266b0648 | 2023-08-11 02:07:23 |         2 |
+---------+----------+----------------------------------+---------------------+-----------+

```

## SQL UPDATE Statement

- The UPDATE statement is used to modify the existing records in a table.

```sql
UPDATE  users SET  username = 'ahmed',password = md5('9876543') WHERE user_id = 2;
UPDATE   users ,users2  SET  users.password = users2.password  WHERE user_id = 2;
```

## SQL DELETE Statement

- The DELETE statement is used to delete existing records in a table.

```sql
ELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';

DELETE FROM Customers;
```

## The SQL SELECT Statement

```sql
SELECT * FROM Customers WHERE Country='Germany' FETCH FIRST 3 ROWS ONLY;

SELECT * FROM Customers WHERE Country='Germany' LIMIT 3;

SELECT TOP 3 * FROM Customers WHERE Country='Germany';

```