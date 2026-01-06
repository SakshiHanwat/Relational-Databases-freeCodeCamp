# SQL Basic Data Types

This README provides a clear overview of the most commonly used data types in SQL, with examples based on PostgreSQL. Understanding data types is essential for designing efficient, reliable, and scalable relational databases.

---

## What Are Data Types in SQL?

When creating a table in SQL, each column must be assigned a **data type**. A data type defines the kind of values that can be stored in a column, such as numbers, text, dates, or logical values.

Choosing the correct data type:

* Ensures data accuracy and integrity
* Improves database performance
* Makes the schema easier to understand and maintain

---

## Basic Syntax for Creating a Table

```sql
CREATE TABLE table_name (
  column1 data_type column_constraint,
  column2 data_type column_constraint,
  column3 data_type column_constraint
);
```

Each column definition includes:

* Column name
* Data type
* Optional constraints (e.g., NOT NULL, UNIQUE)

---

## Main Categories of SQL Data Types

SQL data types are commonly grouped into the following categories:

1. Numeric
2. Date and Time
3. Character and String
4. Unicode
5. Binary
6. Miscellaneous

This document focuses on the most frequently used data types in PostgreSQL.

---

## Numeric Data Types

### INTEGER

```sql
units_sold INTEGER
```

* Stores whole numbers
* Uses 4 bytes of storage
* Range: -2,147,483,648 to 2,147,483,647
* Commonly used for counts and numeric values

### SMALLINT and BIGINT

* **SMALLINT**: Smaller range of integers
* **BIGINT**: Larger range of integers
* Choice depends on the expected size of values

### SERIAL

```sql
id SERIAL
```

* Commonly used for primary key columns
* Automatically generates sequential integer values
* Internally treated as an INTEGER with auto-increment behavior
* Does not allow NULL values

Example behavior:

* First row → 1
* Second row → 2
* Third row → 3

**MySQL equivalent:**

```sql
id INT AUTO_INCREMENT
```

---

## Character and String Data Types

### VARCHAR

```sql
name VARCHAR(50)
```

* Stores variable-length text
* Maximum length must be specified
* Efficient for short to medium-length strings

### TEXT

```sql
description TEXT
```

* Stores text of unlimited length
* Suitable for long descriptions or documents

---

## Date and Time Data Types

### DATE

```sql
event_date DATE
```

* Stores calendar dates (year, month, day)

### TIME

```sql
start_time TIME
```

* Stores time values (hours, minutes, seconds)

### TIMESTAMP

```sql
event_timestamp TIMESTAMP
```

* Stores both date and time

### TIMESTAMP WITH TIME ZONE

```sql
event_timestamp TIMESTAMP WITH TIME ZONE
```

* Includes time zone information
* Useful for global applications

---

## Boolean Data Type

### BOOLEAN

```sql
is_active BOOLEAN
```

* Stores logical values
* Possible values: TRUE or FALSE
* Commonly used for status flags

---

## Summary Table

| Data Type | Purpose               |
| --------- | --------------------- |
| INTEGER   | Whole numbers         |
| SERIAL    | Auto-incrementing IDs |
| VARCHAR   | Limited-length text   |
| TEXT      | Long text             |
| DATE      | Date only             |
| TIME      | Time only             |
| TIMESTAMP | Date and time         |
| BOOLEAN   | TRUE / FALSE values   |

---

## Conclusion

Selecting the correct SQL data types is a fundamental step in database design. Proper data typing improves data consistency, enhances performance, and ensures long-term scalability. While data types may vary slightly between database systems, the core concepts remain consistent across relational databases.

For advanced use cases, always refer to the official documentation of your database management system.
