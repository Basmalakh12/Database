# create ecommerce

```sql
CREATE DATABASE ecommerce CHARACTER SET utf8 COLLATE utf8_general_ci;

use database;

CREATE TABLE customer(
    -> customer_id int unsigned not null primary key auto_increment,
    -> frist_name varchar(255) not null,
    -> second_name varchar(255) not null,
    -> email varchar(255) not null,
    -> address varchar(255) not null,
    -> phone_num varchar(255) not null
    -> );


CREATE TABLE supplier(
    -> supplier_id int unsigned not null primary key auto_increment,
    ->  frist_name varchar(255) not null,
    -> second_name varchar(255) not null,
    ->  email varchar(255) not null,
    -> address varchar(255) not null,
    -> phone_num varchar(255) not null
    -> );


CREATE TABLE product(
    -> product_id int unsigned not null primary key auto_increment,
    -> date timestamp,
    -> description varchar(255),
    -> price int not null,
    -> name varchar(255) not null,
    ->  stock_quntity int not null,
    -> customer_id int unsigned,
    -> supplier_id int unsigned,
    ->  FOREIGN KEY (customer_id) REFERENCES customer(customer_id),
    -> FOREIGN KEY (supplier_id) REFERENCES supplier(supplier_id)
    -> );


CREATE TABLE  category(
    -> category_id int unsigned not null primary key auto_increment,
    -> name varchar(255) not null,
    -> description varchar(255)
    -> );


 CREATE TABLE category_product(
    -> id int unsigned not null primary key auto_increment,
    ->  category_id int unsigned,
    -> product_id int unsigned,
    -> FOREIGN KEY (category_id) REFERENCES category(category_id),
    -> FOREIGN KEY (product_id) REFERENCES product(product_id)
    -> );


  CREATE TABLE custorder(
    -> order_id int unsigned not null primary key auto_increment,
    -> status varchar(255),
    -> date timestamp,
    -> total_amount int not null,
    -> shipping_address varchar(255) not null,
    -> payment_method varchar(255) not null,
    -> customer_id int unsigned,
    -> FOREIGN KEY (customer_id) REFERENCES customer(customer_id)
    -> );


CREATE TABLE orderitem(
    -> orderitem_id int unsigned not null primary key auto_increment,
    -> pricePerUnit int not null,
    ->  quntity int not null,
    -> subtotal int not null,
    -> order_id int unsigned,
    -> FOREIGN KEY (order_id) REFERENCES custorder(order_id)
    -> );


 CREATE TABLE payment(
    -> payment_id int unsigned not null primary key auto_increment,
    -> payment_method varchar(255) not null,
    -> date timestamp,
    -> status varchar(255),
    -> order_id int unsigned,
    -> FOREIGN KEY (order_id) REFERENCES custorder(order_id)
    -> );


 CREATE TABLE review(
    -> review_id int unsigned not null primary key auto_increment,
    -> date timestamp,
    -> comment varchar(255),
    -> rating varchar(255),
    -> customer_id int unsigned,
    -> product_id int unsigned,
    ->  FOREIGN KEY (customer_id) REFERENCES customer(customer_id),
    -> FOREIGN KEY (product_id) REFERENCES product(product_id)
    ->);

```
