# one-one relationship:
* Two entities are connected with a line that typically has a '1' on both ends indicating the one-to-one relationship.
* ```
  CREATE TABLE Person (
    person_id INT PRIMARY KEY,
    name VARCHAR(100)
  );

  CREATE TABLE Passport (
    passport_id INT PRIMARY KEY,
    person_id INT,
    FOREIGN KEY (person_id) REFERENCES Person(person_id)
  );

  ```
  * In this above example one person has only one passport.Thats why we can say this as one to one relationship
# one-many relationship:
* A one-to-many relationship in a database is where a single record in one table (the "parent" table) can relate to multiple records in another table (the "child" 
  table), but each record in the child table is related to only one record in the parent table.
```
CREATE TABLE Customers (
    customer_id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100)
);
CREATE TABLE Orders (
    order_id INT PRIMARY KEY,
    order_date DATE,
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES Customers(customer_id)
);
```
* In this above example we can see custemer id (PK) is in table 2 this how we have to represent one to many entities.
# many-many relationship
* A many-to-many relationship in a database occurs when multiple records in one table are associated with multiple records in another table. This relationship is typically implemented using a junction table (also known as a bridge table or associative table) that holds foreign keys referencing the primary keys of the two tables involved in the relationship.
```
CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    name VARCHAR(100)
);
CREATE TABLE Courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100)
);
CREATE TABLE Enrollments (
    student_id INT,
    course_id INT,
    PRIMARY KEY (student_id, course_id),
    FOREIGN KEY (student_id) REFERENCES Students(student_id),
    FOREIGN KEY (course_id) REFERENCES Courses(course_id)
);
```
# cap theorm
![Screenshot (886)](https://github.com/Subhransupanda2000/daily-work-update/assets/123824203/21fd39c4-aa6c-487a-986a-16266fac43d2)
# Read through cache
![Screenshot (887)](https://github.com/Subhransupanda2000/daily-work-update/assets/123824203/ebf61603-92c2-4aad-855d-638a07200cad)
![Screenshot (888)](https://github.com/Subhransupanda2000/daily-work-update/assets/123824203/2333a951-729f-4e4d-8a5d-356da96f3c5d)
# Write through cache
![Screenshot (889)](https://github.com/Subhransupanda2000/daily-work-update/assets/123824203/ac1deb71-51df-40c8-bae1-0dc0d6f68003)





