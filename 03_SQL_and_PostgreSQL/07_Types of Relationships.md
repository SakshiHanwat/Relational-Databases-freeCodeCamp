# Types of Relationships in a Relational Database

## Introduction

Relational databases store data in **tables** made up of rows and columns.  
The **relational** aspect means that records in different tables can be connected through relationships.  
Understanding these relationships is essential for designing **efficient**, **scalable**, and **well-structured** databases.

---

## One-to-One Relationship

### What Is a One-to-One Relationship?

A **one-to-one relationship** exists when:
* Each record in Table A can be associated with **at most one** record in Table B.
* Each record in Table B can be associated with **at most one** record in Table A.

### Example

* Each employee has **one vehicle**.
* Each vehicle belongs to **one employee**.

### Use Case

Useful when splitting data for **security**, **organization**, or **performance** reasons.

---

## One-to-Many Relationship

### What Is a One-to-Many Relationship?

A **one-to-many relationship** exists when:
* One record in Table A can be associated with **multiple records** in Table B.
* Each record in Table B can be associated with **only one** record in Table A.

### Example

* One customer can place **many orders**.
* Each order belongs to **one customer**.

### Note

This is the **most common** relationship type in relational databases.

---

## Many-to-One Relationship

### What Is a Many-to-One Relationship?

A **many-to-one relationship** is the inverse of a one-to-many relationship.

### Example

* Many orders belong to **one customer**.

> Functionally, this is the same as one-to-many, just viewed from the other table's perspective.

---

## Many-to-Many Relationship

### What Is a Many-to-Many Relationship?

A **many-to-many relationship** exists when:
* A record in Table A can be associated with **multiple records** in Table B.
* A record in Table B can be associated with **multiple records** in Table A.

### Example

* An author can write **many books**.
* A book can have **many authors**.

---

### Implementing Many-to-Many with a Junction Table

Relational databases do **not directly support** many-to-many relationships.  
To implement them, we use a **junction table** (or bridge table).

#### Example Tables

* `authors`
* `books`
* `books_authors` (junction table)

#### Junction Table Columns

* `author_id` → Foreign Key referencing `authors`
* `book_id` → Foreign Key referencing `books`

> This transforms the many-to-many relationship into **two one-to-many relationships**, making queries easier and reducing redundancy.

---

## Self-Referencing (Recursive) Relationship

### What Is a Self-Referencing Relationship?

A **self-referencing** relationship occurs when records in a table can reference **other records in the same table**.

### Example

* An employees table where each employee has a `manager_id` referring to another employee.

### Use Case

* Hierarchical data like **employees & managers**, **categories & subcategories**, or **organizational charts**.

---

## Why Database Relationships Matter

* Maintain **data consistency**  
* Avoid **duplicate or orphaned records**  
* Enable **efficient queries**  
* Accurately model **real-world scenarios**  

---

## Summary

Database relationships allow tables to **interact logically**:

* **One-to-One:** Each record matches exactly one record in another table.  
* **One-to-Many / Many-to-One:** One record relates to many in another table.  
* **Many-to-Many:** Multiple records relate to multiple records via a junction table.  
* **Self-Referencing:** Records relate to other records in the same table.

Proper understanding of relationships ensures **data integrity**, **scalability**, and **efficient database design**.
