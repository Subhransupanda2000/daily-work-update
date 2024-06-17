# DDL DML DRL

* DDL commands deal with defining the structure of database. Here are some common DDL commands:
```
CREATE: Used to create new database objects like tables, views, indexes, etc.
ALTER: Allows modifying the structure of existing objects.
DROP: Used to delete database objects entirely.
```
* DML (Data Manipulation Language): DML commands focus on manipulating data within the database. Some important DML commands include:

```
INSERT: Used to add new rows of data to a table.
UPDATE: Allows modifying existing data in a table.
DELETE: Used to remove rows from a table.
```
* DQL is fetching and manipulating data retrieved from the database.
```
SELECT: This is the workhorse for retrieving filter data based on conditions, and sort the results.
```
```
CREATE TABLE customers (
  id INT PRIMARY KEY AUTO_INCREMENT,  -- Auto-increments a unique ID for each customer
  name VARCHAR(255) NOT NULL,
  email VARCHAR(255) UNIQUE,   -- Ensures unique email addresses
  city VARCHAR(255)
);
```
```
INSERT INTO customers (name, email, city)
VALUES ('John Doe', 'john.doe@example.com', 'New York');
```
```
SELECT *
FROM customers;
```
```
ALTER TABLE customers ADD phone VARCHAR(20);

```
```
ALTER TABLE customers MODIFY email VARCHAR(100);
ALTER TABLE customers DROP COLUMN city;
DELETE FROM customers
WHERE email = 'john.doe@example.com';
ALTER TABLE customers RENAME COLUMN name TO customer_name;

```
