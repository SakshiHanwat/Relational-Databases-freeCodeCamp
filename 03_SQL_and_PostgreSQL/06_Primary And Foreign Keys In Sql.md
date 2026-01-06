# Primary and Foreign Keys in SQL

## Introduction

In SQL, **primary keys** and **foreign keys** are fundamental concepts used to establish relationships between tables and maintain data integrity in relational databases. They ensure that data is accurate, consistent, and logically connected across multiple tables.

---

## Primary Keys

### What Is a Primary Key?

A **primary key** is a column or a combination of columns that uniquely identifies each record (row) in a table.

### Key Characteristics of Primary Keys

* Each table can have **only one primary key**.
* The value of a primary key must be **unique** for every row.
* Primary key columns **cannot contain NULL values**.
* Primary keys help optimize data retrieval and indexing.

### Defining a Primary Key in PostgreSQL

You can define a primary key by adding the `PRIMARY KEY` constraint after the column definition:

```
column_name data_type PRIMARY KEY
```

### Example: Single-Column Primary Key

```
CREATE TABLE students (
  student_id SERIAL PRIMARY KEY,
  name VARCHAR(100)
);
```

In this example:

* `student_id` uniquely identifies each student.
* The `SERIAL` type automatically generates unique values.

---

## Composite Primary Keys

### What Is a Composite Primary Key?

A **composite primary key** is used when a single column is not sufficient to uniquely identify a record. Instead, a combination of two or more columns together ensures uniqueness.

### Defining a Composite Primary Key

```
CREATE TABLE table_name (
  column1 data_type,
  column2 data_type,
  column3 data_type,
  PRIMARY KEY (column1, column2)
);
```

### Example: Course Enrollments

```
CREATE TABLE course_enrollments (
  student_id INT,
  course_id INT,
  PRIMARY KEY (student_id, course_id)
);
```

In this case:

* A student can enroll in multiple courses.
* A course can have multiple students.
* The same student cannot enroll in the same course more than once.

---

## Foreign Keys

### What Is a Foreign Key?

A **foreign key** is a column (or set of columns) in one table that references the **primary key** of another table. It is used to create a relationship between two tables.

### Key Characteristics of Foreign Keys

* A table can have **multiple foreign keys**.
* Foreign key values must match existing primary key values in the referenced table or be NULL (if allowed).
* Foreign keys help maintain **referential integrity**.

### Example: Customers and Orders Relationship

```
CREATE TABLE customers (
  customer_id SERIAL PRIMARY KEY,
  first_name VARCHAR(100) NOT NULL
);

CREATE TABLE orders (
  order_id SERIAL PRIMARY KEY,
  customer_id INTEGER,
  FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
);
```

In this example:

* `customer_id` is the primary key in the `customers` table.
* The `orders` table includes `customer_id` as a foreign key.
* Each order is linked to a valid customer.

---

## Why Primary and Foreign Keys Matter

* They prevent **duplicate and invalid data**.
* They avoid **orphaned records** (records referencing non-existent data).
* They accurately model **real-world relationships**.
* They are the foundation of **relational database design**.

---

## Summary

Primary keys uniquely identify records within a table, while foreign keys create meaningful relationships between tables. Together, they ensure data consistency, integrity, and efficient querying in relational databases.
