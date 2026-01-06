# How to Insert and View Data in a Table (SQL)

This document explains the fundamental SQL commands used to insert data into a table and retrieve (view) that data using queries. These concepts are essential for working with relational databases.

---

## Example Table Structure

We will use the following `dogs` table as an example:

```sql
CREATE TABLE dogs (
  id SERIAL,
  name VARCHAR(100),
  age INTEGER
);
```

### Table Explanation

* `id`: Automatically generated unique identifier for each record (auto-incremented).
* `name`: Stores the dog's name as text.
* `age`: Stores the dog's age as a whole number.

---

## Inserting Data into a Table

### Insert a Single Record (Recommended Method)

```sql
INSERT INTO dogs (name, age)
VALUES ('Gino', 3);
```

**Why this method is safe:**

* Columns are explicitly defined.
* Values are mapped correctly to columns.
* Reduces chances of errors if table structure changes.

---

### Insert a Record Without Specifying Columns

```sql
INSERT INTO dogs
VALUES ('Gino', 3);
```

**Note:**

* This method depends on column order.
* More error-prone and generally not recommended.

---

### Insert Multiple Records at Once

```sql
INSERT INTO dogs (name, age)
VALUES
  ('Gino', 3),
  ('Nora', 2);
```

* Allows inserting multiple rows in a single command.
* Improves performance when adding bulk data.

---

## Viewing Data from a Table

### Select All Columns

```sql
SELECT *
FROM dogs;
```

* `*` is a wildcard that represents all columns.

**Sample Output:**

```
 id | name | age
----+------+-----
  1 | Gino |   3
  2 | Nora |   2
```

---

### Select Specific Columns

```sql
SELECT name, age
FROM dogs;
```

* Retrieves only the selected columns.

---

### Filter Data Using WHERE Clause

#### Example: Dogs Younger Than 3 Years

```sql
SELECT *
FROM dogs
WHERE age < 3;
```

**Result:**

```
 id | name | age
----+------+-----
  2 | Nora |   2
```

---

#### Example: Get Age of a Specific Dog

```sql
SELECT age
FROM dogs
WHERE name = 'Gino';
```

**Result:**

```
 age
-----
  3
```

---

## Key Takeaways

* `INSERT INTO` is used to add new records to a table.
* `SELECT` is used to retrieve data from tables.
* `*` selects all columns.
* `WHERE` filters records based on conditions.
* Always prefer inserting data by explicitly specifying column names.

These commands form the foundation of data manipulation in SQL and are used extensively in real-world applications.
