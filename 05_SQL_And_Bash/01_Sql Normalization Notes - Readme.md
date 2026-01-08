# Normalization in SQL – Notes

## What Is Normalization in SQL?

Normalization is the process of organizing a relational database using a set of rules called **normal forms**. The main goals of normalization are to **reduce data redundancy** (repeated data) and **improve data integrity** (accuracy and consistency of data).

When a database is normalized, the data is divided into smaller, well-structured tables. These tables are connected using **primary keys** and **foreign keys**. Even though the data is split across multiple tables, no information is lost. Instead, the database becomes easier to manage, update, and maintain.

---

## Why Normalization Is Important

Normalization helps in:

* Reducing storage space by avoiding duplicate data
* Preventing data inconsistencies
* Avoiding insertion, update, and deletion anomalies
* Making the database easier to understand and maintain

For example, if a customer’s address is stored in many order records and the address changes, you would need to update it in many places. With normalization, the address is stored only once, so it needs to be updated in just one table.

---

## Normal Forms Overview

Normal forms are a series of rules used to organize database tables. Each higher normal form builds on the previous one and adds stricter rules.

The commonly used normal forms are:

* First Normal Form (1NF)
* Second Normal Form (2NF)
* Third Normal Form (3NF)
* Boyce-Codd Normal Form (BCNF)

---

## First Normal Form (1NF)

A table is in **First Normal Form (1NF)** if:

1. Each cell contains only a single (atomic) value.
2. Each row is unique (no duplicate records).
3. The order of rows and columns does not matter.

### Example

If a students table stores multiple phone numbers in one column (comma-separated), it violates 1NF. Instead, phone numbers should be stored in a separate table with one phone number per row and a foreign key referencing the student.

The focus of 1NF is to keep data **simple and atomic**.

---

## Second Normal Form (2NF)

A table is in **Second Normal Form (2NF)** if:

* It is already in 1NF, and
* All non-key attributes are **fully dependent on the entire primary key**.

This rule is important when the table has a **composite primary key** (a primary key made of more than one column).

---

## Superkeys and Candidate Keys

### Superkey

A **superkey** is any set of columns that uniquely identifies each row in a table.

Example superkeys:

* customer_id
* { customer_id, name }
* { customer_id, name, email }
* email (if email is unique)

### Candidate Key

A **candidate key** is a minimal superkey. It contains only the columns required to uniquely identify a row.

In the example above:

* customer_id and email are candidate keys
* name is not part of any candidate key because it does not uniquely identify a record

The key difference is that superkeys may include extra attributes, while candidate keys do not.

---

## Partial Dependency and 2NF Example

A **partial dependency** occurs when a non-key attribute depends on only part of a composite primary key.

### Example

Orders table:

order_id | item_id | order_date | quantity | order_shipping_city

Primary Key: (order_id, item_id)

Here, order_shipping_city depends only on order_id, not on item_id. This is a partial dependency and violates 2NF.

### Solution

Split the table into:

**order_header**
order_id | order_date | order_shipping_city

**order_items**
order_id | item_id | quantity

Now both tables are in 2NF.

---

## Third Normal Form (3NF)

A table is in **Third Normal Form (3NF)** if:

* It is in 2NF, and
* All non-key attributes depend **only on the primary key**, not on other non-key attributes

This rule removes **transitive dependencies**.

---

## Transitive Dependency and 3NF Example

A **transitive dependency** occurs when:

Primary Key → Non-key Attribute → Another Non-key Attribute

### Example

order_id | customer_id | customer_city | city_postal_code | order_date | quantity

Primary Key: order_id

Dependency chain:
order_id → customer_id → customer_city → city_postal_code

This causes data repetition and update problems.

### Solution

Split into three tables:

**orders**
order_id | customer_id | order_date | quantity

**customers**
customer_id | city_name

**cities**
city_name | city_postal_code

This removes the transitive dependency and satisfies 3NF.

---

## Boyce-Codd Normal Form (BCNF)

BCNF is a stricter version of 3NF.

A table is in **Boyce-Codd Normal Form (BCNF)** if:

* It is in 3NF, and
* Every determinant (left-hand side of a functional dependency) is a superkey

BCNF ensures that any attribute that determines another attribute must be a candidate key or a superset of it.

---

## Conclusion

Normalization is essential for designing efficient and reliable relational databases. It reduces redundancy, improves data integrity, saves storage, and makes databases easier to maintain. In most real-world applications, databases are normalized up to **Third Normal Form (3NF)**.

---

## Questions and Answers

### 1. Which normal form is concerned with replacing groups of data with single values?

**Answer:** First Normal Form (1NF)

### 2. A table is in Second Normal Form (2NF) if it is in 1NF and:

**Answer:** All non-key attributes are fully functionally dependent on the entire primary key.

### 3. Which normal form addresses transitive dependencies?

**Answer:** Third Normal Form (3NF)
