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
# NORMALIZATION
* Functional Dependency:
* A functional dependency exists between two sets of attributes (columns) in a table when the value of one set of attributes determines the value of the other set. In simpler terms, if you know the value for a specific set of columns, you automatically know the value for another set.

* A table named "Orders" with columns "Order ID," "Customer ID," "Product ID," and "Quantity." There's a functional dependency between "Order ID" and ("Customer ID," "Product ID"). This means that knowing the "Order ID" uniquely identifies the combination of "Customer ID" and "Product ID" for that specific order.

* 1NF (First Normal Form):
The most basic level of database normalization. A table is considered to be in 1NF if it adheres to these rules:
* Atomic Values: Each cell in the table should contain a single atomic value (indivisible unit of data). This means no repeating groups or lists within a single cell.
* Unique Identifiers: Each table should have a primary key, which is a column or set of columns that uniquely identifies each row in the table. No duplicate rows are allowed based on the primary key.
* 2NF (Second Normal Form):
* A table is considered to be in 2NF if it meets all the requirements of 1NF and also eliminates a specific type of redundancy:

* No Partial Dependency: There should be no partial dependencies on the candidate key (possible primary keys). This means all non-key attributes (attributes not part of the primary key) must be fully dependent on the entire candidate key, not just a part of it.
Here's an example of a violation of 2NF:

Imagine a table named "Customers" with columns "Customer ID," "Name," "Email," and "City." There might be a functional dependency between "Customer ID" and "City." This creates a partial dependency because "City" only depends on "Customer ID," not necessarily needing the entire information stored in "Name" and "Email" (which could be another candidate key). To achieve 2NF, you might need to separate "City" into a different table linked to the "Customer ID" through a foreign key relationship.
