# CREATE BLOG

```SQL
 CREATE DATABASE blog;
 USE blog;

 CREATE TABLE employee (
    -> emp_id int unsigned not null primary key auto_increment,
    -> name varchar(255) not null,
    -> image varchar(255),
    -> email varchar(255) not null unique,
    -> password varchar(255) not null,
    -> status varchar(255) 
    -> );

 ONE2ONE

 CREATE TABLE contact( 
    -> contact_id int unsigned not null auto_increment,
    -> name varchar(255) not null, image varchar(255) not null,
    -> message text,
    -> phone varchar(255) not null,
    -> emp_id int unsigned,
    -> foreign key (emp_id) REFERENCES employee (emp_id) 
    );

 ONE2MANY

 CREATE TABLE achievement (
    ->  achivement_id int unsigned not null  primary key auto_increment,
    -> name varchar(255) not null,
    -> image varchar(255) not null,
    -> description text,
    -> date timestamp,
    ->  emp_id int unsigned,
    -> foreign key (emp_id) references employee(emp_id)
    -> );

    MANY2MANY

  CREATE TABLE artical(
    -> artical_id int unsigned not null  primary key auto_increment);

  CREATE TABLE comment(
    -> comment_id int unsigned not null  primary key auto_increment,
    -> emp_id int unsigned,
    -> artical_id int unsigned,
    -> foreign key (emp_id) references employee(emp_id),
    ->  foreign key(artical_id) references artical(artical_id)
    -> );


  CREATE TABLE tag(
    -> tag_id int unsigned not null  primary key auto_increment,
    -> name varchar(255) not null
    -> );

 CREATE TABLE artical_tag(
    -> id int unsigned not null  primary key auto_increment,
    -> artical_id int unsigned,
    -> tag_id int unsigned ,
    -> foreign key(artical_id) references artical(artical_id),
    -> foreign key(tag_id) references tag(tag_id)
    -> );
 
 CREATE TABLE category(
    -> category_id int unsigned not null  primary key auto_increment,
    -> name varchar(255) not null,
    -> image varchar(255) not null,
    -> description text,
    -> created_at timestamp
    -> );


 CREATE TABLE artical_category(
    -> id int unsigned not null  primary key auto_increment,
    -> artical_id int unsigned,
    -> category_id int unsigned,
    -> foreign key(artical_id) references artical(artical_id),
    -> foreign key(category_id) references category(category_id)
    -> );


```