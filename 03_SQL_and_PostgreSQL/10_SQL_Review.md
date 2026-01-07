# SQL and PostgreSQL Review

## Introduction to Relational Databases

Relational databases organize data into **tables** composed of **rows** and **columns**. Each row represents a single record, while each column represents an attribute of that record.

### Advantages of Relational Databases

* Highly **scalable** and reliable
* Widely applicable across domains such as **healthcare, business, gaming, and e-commerce**
* Structured design ensures **data consistency and integrity**

### Common Use Cases

* Web applications
* Inventory management systems
* E-commerce platforms
* Healthcare systems
* Enterprise-level applications

---

## Key Concepts

### Schema

A **schema** defines the structure of a relational database, including tables, columns, data types, constraints, and relationships between tables.

### Primary Keys

Primary keys are **unique identifiers** for each row in a table. They ensure data integrity and are used to relate tables through foreign keys.

### Foreign Keys

Foreign keys reference the **primary key of another table**, creating a logical relationship between tables.

### Relationships

Relationships connect tables using primary and foreign keys, enabling normalized data storage and meaningful queries.

### Entity Relationship Diagrams (ERDs)

ERDs visually represent tables (entities) and the relationships between them within a database schema.

### Data Integrity

Data integrity ensures stored data remains **accurate, consistent, and valid**, enforced using constraints, keys, and data types.

---

## SQL Basics

### Queries

Queries are used to retrieve specific data from a database.

```
SELECT * FROM dogs WHERE age < 3;
```

### WHERE Clause

The `WHERE` clause filters records based on conditions using comparison operators such as `<`, `=`, and `>`.

### ORDER BY Clause

Used to sort query results based on one or more columns.

```
SELECT columns FROM table_name ORDER BY column_name;
```

---

## Table Operations

### CREATE TABLE

Used to create a new table in the database.

```
CREATE TABLE first_table();
```

### ALTER TABLE ADD COLUMN

Adds a new column to an existing table.

```
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
```

### ALTER TABLE DROP COLUMN

Removes a column from an existing table.

```
ALTER TABLE table_name DROP COLUMN column_name;
```

### ALTER TABLE RENAME COLUMN

Renames an existing column.

```
ALTER TABLE table_name RENAME COLUMN column_name TO new_name;
```

### DROP TABLE

Deletes an entire table from the database.

```
DROP TABLE table_name;
```

### ALTER DATABASE RENAME

Renames an existing database.

```
ALTER DATABASE database_name RENAME TO new_database_name;
```

### DROP DATABASE

Deletes an entire database.

```
DROP DATABASE database_name;
```

---

## Constraints and Data Integrity

### NOT NULL Constraint

Ensures a column cannot store NULL values.

```
column_name VARCHAR(50) NOT NULL
```

### ADD PRIMARY KEY

Adds a primary key constraint to a table.

```
ALTER TABLE table_name ADD PRIMARY KEY(column_name);
```

### DROP CONSTRAINT

Removes a constraint from a table.

```
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```

### FOREIGN KEY Constraint

Adds a foreign key referencing another table.

```
ALTER TABLE table_name ADD COLUMN column_name DATATYPE REFERENCES referenced_table(referenced_column);
```

### UNIQUE Constraint

Ensures all values in a column are unique.

```
ALTER TABLE table_name ADD UNIQUE(column_name);
```

### SET NOT NULL on Existing Column

```
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;
```

### Composite Primary Key

A primary key made of multiple columns.

```
CREATE TABLE course_enrollments (
  student_id INT,
  course_id INT,
  PRIMARY KEY (student_id, course_id)
);
```

---

## Data Manipulation (CRUD)

### INSERT

```
INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);
```

### INSERT with Multiple Rows

```
INSERT INTO dogs (name, age) VALUES
('Gino', 3),
('Nora', 2);
```

### UPDATE

```
UPDATE table_name SET column_name = new_value WHERE condition;
```

### DELETE

```
DELETE FROM table_name WHERE condition;
```

---

## Data Types

* **NUMERIC(10,2)** – Precise decimal values
* **TEXT** – Variable-length text
* **INTEGER / SMALLINT / BIGINT** – Whole numbers
* **SERIAL** – Auto-incrementing integers (PostgreSQL)
* **VARCHAR(n)** – Character strings with length limit
* **DATE** – Date values
* **TIME** – Time values
* **TIMESTAMP** – Date and time values
* **BOOLEAN** – True/False values

---

## Database Relationships

### Types of Relationships

* One-to-one
* One-to-many
* Many-to-one
* Many-to-many
* Self-referencing (recursive)

### One-to-One

Each record in one table corresponds to exactly one record in another table.

Example: Employees → Vehicles

### One-to-Many

One record relates to multiple records in another table.

Example: Customers → Orders

### Many-to-Many (Using Junction Table)

```
CREATE TABLE books_authors (
  author_id INT REFERENCES authors(id),
  book_id INT REFERENCES books(id)
);
```

### Self-Referencing Relationship

A table references itself.

Example: Employees reporting to other employees.

---

## Advanced SQL (Joins)

### INNER JOIN

Returns matching rows from both tables.

### LEFT JOIN

Returns all rows from the left table and matching rows from the right table.

### RIGHT JOIN

Returns all rows from the right table and matching rows from the left table.

### FULL OUTER JOIN

Returns all rows from both tables.

### SELF JOIN

Joins a table with itself.

### CROSS JOIN

Returns the Cartesian product of two tables.

---

## PostgreSQL Specific Commands

* `psql --username=freecodecamp --dbname=postgres`
* `\l` – List databases
* `CREATE DATABASE database_name;`
* `\c database_name` – Connect to database
* `\d` – List tables
* `\d table_name` – Describe table
* `\q` – Exit psql

---

## Relational vs Non-Relational Databases

Relational databases use structured schemas and ensure consistency. Non-relational (NoSQL) databases offer flexibility for unstructured or rapidly changing data.

---

## Popular RDBMS Systems

* MySQL
* PostgreSQL
* SQLite
* Microsoft SQL Server
* Oracle Database

---

## Best Practices

* Use **snake_case** naming conventions
* Design normalized schemas
* Use constraints to enforce data integrity

---

## Assignment

Review all SQL and PostgreSQL concepts covered in this document.
