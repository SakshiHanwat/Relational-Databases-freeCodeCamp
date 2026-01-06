# What Is SQL, and How Can You Create a Database with Tables?

## Introduction to SQL

SQL stands for **Structured Query Language**. It was developed in the 1970s and was initially known as **Structured English Query Language (SEQUEL)**. Later, this name was shortened to SQL.

SQL is a programming language used for **storing, managing, and manipulating data** in **relational databases**.

---

## Relational Databases and Tables

Relational databases organize data into **tables**.

* **Rows** represent individual records.
* **Columns** represent attributes or fields of those records.

Each table clearly defines how data is structured and how different data attributes relate to each other.

---

## What Can You Do with SQL?

Using SQL, you can:

* Add data
* Modify existing data
* Delete data
* Retrieve specific data
* Filter, sort, and aggregate information

SQL helps optimize database performance by querying only the required data. It also integrates easily with many programming languages, allowing applications to interact directly with databases.

---

## Why SQL Is Important

* Industry standard language
* Enforces data integrity
* Supports security features like authentication and encryption
* Scalable and portable
* Compatible with multiple database management systems

---

## SQL Commands and Queries

SQL works using commands called **SQL statements** or **SQL queries**. These statements are written using predefined SQL keywords.

By convention, SQL commands end with a **semicolon (;)**.

---

## Connecting to PostgreSQL Using psql

Before executing SQL commands, connect to the PostgreSQL database using the psql shell:

```
psql -U <username> -d <database_name>
```

If you haven't created a database yet, you can connect using the default database named `postgres`.

After connecting, the prompt will change to:

```
postgres=#
```

---

## Creating a Database

To create a new database named `my_database`, use:

```
CREATE DATABASE my_database;
```

SQL keywords are typically written in uppercase for readability.

---

## Connecting to a Database

Inside the psql shell, connect to a database using:

```
\c my_database
```

Note: Commands starting with a backslash () are **psql shell commands**, not SQL commands, and do not require a semicolon.

After connecting, the prompt will change to:

```
my_database=#
```

---

## Creating a Table

Once connected, you can create a table using:

```
CREATE TABLE products (
  id SERIAL,
  name VARCHAR(255)
);
```

This creates a table named `products` with:

* `id`: an auto-incrementing identifier
* `name`: a text field for product names

---

## Naming Conventions

The standard naming convention for tables and columns is **snake_case**:

* lowercase letters
* words separated by underscores

Example:

```
delivery_orders
```

---

## Conclusion

SQL makes it easy to query, manipulate, and analyze structured data. It is a foundational skill for developers working with relational databases and is widely used to solve real-world data problems.
