# DataBase Relationships

- relationships are connections between two or more tables. These are important because they allow you to query data from multiple tables and combine these in a single result.
- They also help establish meaning and organize data in a database in a way that makes sense to users.

## There can be multiple relationships between tables in a database, and these can be any of these three types

- One-to-one
  - This describes a link between two tables, where one record or row in the first table connects to exactly one record or row in the second.

- One-to-many
  - one record in the first table can relate to multiple records or rows in the second table.

- Many-to-many
  - multiple records in the first table can relate to multiple records in the second table and vice versa.

- Self-referencing relationships
  - also known as a recursive relationship, in a database occurs when a column in a table relates to another column in the same table.

  ---

```sql
CREATE DATABASE store CHARACTER SET utf8 COLLATE utf8_general_ci;
  use store;
  
   CREATE TABLE users(
    ->  user_id int unsigned not null primary key auto_increment,
    -> username varchar(30) not null,
    -> password char(72)not null,
    -> lastlogin datetime);

SHOW TABLES;
+-----------------+
| Tables_in_store |
+-----------------+
| users           |
+-----------------+

 describe users;
+-----------+--------------+------+-----+---------+----------------+
| Field     | Type         | Null | Key | Default | Extra          |
+-----------+--------------+------+-----+---------+----------------+
| user_id   | int unsigned | NO   | PRI | NULL    | auto_increment |
| username  | varchar(30)  | NO   |     | NULL    |                |
| password  | char(72)     | NO   |     | NULL    |                |
| lastlogin | datetime     | YES  |     | NULL    |                |
+-----------+--------------+------+-----+---------+----------------+

ALTER TABLE users ADD COLUMN privilege tinyint(1) default 2;

  
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

 CREATE TABLE users_profiles(
    -> profile_id int unsigned not null,
    -> first_name varchar(20) not null,
    -> last_name varchar(20),
    -> facebook_url varchar(100),
    -> image varchar(150),
    -> gender enum('male', 'female') not null,
    -> address varchar(100) not null,
    -> CONSTRAINT fk_profile_id FOREIGN KEY (profile_id) REFERENCES users (user_id)
    -> );
 describe users_profiles;
+--------------+-----------------------+------+-----+---------+-------+
| Field        | Type                  | Null | Key | Default | Extra |
+--------------+-----------------------+------+-----+---------+-------+
| profile_id   | int unsigned          | NO   | MUL | NULL    |       |
| first_name   | varchar(20)           | NO   |     | NULL    |       |
| last_name    | varchar(20)           | YES  |     | NULL    |       |
| facebook_url | varchar(100)          | YES  |     | NULL    |       |
| image        | varchar(150)          | YES  |     | NULL    |       |
| gender       | enum('male','female') | NO   |     | NULL    |       |
| address      | varchar(100)          | NO   |     | NULL    |       |
+--------------+-----------------------+------+-----+---------+-------+
 CREATE TABLE products(
    -> product_id int unsigned not null primary key auto_increment,
    -> product_name varchar(50) not null,
    -> product_price decimal(6,2) not null,
    -> product_quantity smallint(3) not null,
    -> product_created date not null);

  SHOW TABLES;
+-----------------+
| Tables_in_store |
+-----------------+
| products        |
| users           |
| users_profiles  |
+-----------------+

 CREATE TABLE products_orders(
    -> order_id int unsigned not null primary key auto_increment,
    -> customer_id int unsigned not null,
    -> order_timestamp datetime not null default now(),
    -> constraint fk_customer_id foreign key (customer_id) references users (user_id));

 describe products_orders;
+-----------------+--------------+------+-----+-------------------+-------------------+
| Field           | Type         | Null | Key | Default           | Extra             |
+-----------------+--------------+------+-----+-------------------+-------------------+
| order_id        | int unsigned | NO   | PRI | NULL              | auto_increment    |
| customer_id     | int unsigned | NO   | MUL | NULL              |                   |
| order_timestamp | datetime     | NO   |     | CURRENT_TIMESTAMP | DEFAULT_GENERATED |
+-----------------+--------------+------+-----+-------------------+-------------------+

 CREATE TABLE products_orders_list(
    ->  item_id int unsigned not null primary key auto_increment,
    ->  order_id int unsigned not null,
    -> product_id int unsigned not null,
    ->  quantity tinyint(2) not null);

 alter table products_orders_list add constraint fk_order_id foreign key (order_id)references products_orders(order_id);

 alter table products_orders_list add constraint fk_product_id foreign key ( product_id)references products( product_id);

  describe products_orders_list;
+------------+--------------+------+-----+---------+----------------+
| Field      | Type         | Null | Key | Default | Extra          |
+------------+--------------+------+-----+---------+----------------+
| item_id    | int unsigned | NO   | PRI | NULL    | auto_increment |
| order_id   | int unsigned | NO   | MUL | NULL    |                |
| product_id | int unsigned | NO   | MUL | NULL    |                |
| quantity   | tinyint      | NO   |     | NULL    |                |
+------------+--------------+------+-----+---------+----------------+

CREATE TABLE customers_products(
    ->  customer_id int unsigned not null primary key auto_increment,
    ->  product_id int unsigned not null);

alter table customers_products add constraint fk_customer_id2 foreign key (customer_id) references users (user_id);

alter table customers_products add constraint fk_product_id2 foreign key ( product_id) references products( product_id);

 describe customers_products
    -> ;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| customer_id | int unsigned | NO   | PRI | NULL    | auto_increment |
| product_id  | int unsigned | NO   | MUL | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
