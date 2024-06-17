# DDL
* CREATE: Used to create a new table, database, index, or other objects.

```
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    position VARCHAR(50),
    salary DECIMAL(10, 2)
);
```
```
ALTER TABLE employees ADD COLUMN hire_date DATE;

```
