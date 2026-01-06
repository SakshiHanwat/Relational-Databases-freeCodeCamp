# Relational Databases vs Non-Relational Databases

## What Is a Relational Database?

A relational database is a collection of data organized into **tables**. Each table consists of **rows** and **columns**.

* **Rows** represent individual records. For example, in a user table, each row can represent one user.
* **Columns** represent attributes or fields that describe each record, such as name, age, or national ID number.

A major characteristic of relational databases is their ability to **connect related data across multiple tables** using relationships. These relationships are created through shared attributes, allowing data to be efficiently linked and queried.

---

## Schema in Relational Databases

Relational databases require a **schema**, which defines:

* Tables
* Columns
* Data types
* Relationships
* Constraints

The schema provides a structured blueprint for how data is stored and accessed, ensuring consistency and integrity.

---

## Primary Keys and Foreign Keys

Every table in a relational database has a **primary key**, which uniquely identifies each row in the table.

* **Primary Key**: A unique identifier for each record
* **Foreign Key**: A reference to a primary key in another table, used to establish relationships

These keys are fundamental to linking data between tables.

---

## Example: Wildlife Conservation Database

Consider a wildlife conservation center database:

### Animals Table

* Stores general information about animals
* Columns may include: id, species, size, weight, age
* The `id` column acts as the primary key

### Species Table

* Stores species-related data such as habitat and conservation status
* Each species has a unique species ID

### Veterinary Records Table

* Stores health-related data such as treatments, medications, and checkups

The animals table can reference the species table using a species ID, and veterinary records can be linked to animals using animal IDs. This design avoids data duplication and keeps related information organized.

---

## Queries in Relational Databases

A **query** is a request for specific data from the database. Examples include:

* Finding animals that need veterinary checkups
* Identifying the most critically endangered species
* Counting animals born in captivity

Because of table relationships, complex queries can retrieve meaningful data efficiently.

---

## Advantages of Relational Databases

* Structured data storage
* Strong data integrity through constraints
* Support for large datasets
* Suitable for complex, real-world applications

Relational databases are widely used across industries such as healthcare, education, government, e-commerce, gaming, and social media.

---

## What Are Non-Relational Databases?

Non-relational databases, also known as **NoSQL databases**, store data differently. Instead of tables, data is often stored as:

* Documents
* Key-value pairs
* Graphs
* Wide-column stores

These databases are **more flexible** in structure and often do not require a rigid schema.

---

## Key Differences Between Relational and Non-Relational Databases

| Feature        | Relational Databases    | Non-Relational Databases   |
| -------------- | ----------------------- | -------------------------- |
| Data Structure | Tables (rows & columns) | Documents, key-value, etc. |
| Schema         | Fixed, predefined       | Flexible or optional       |
| Relationships  | Strongly enforced       | Usually not enforced       |
| Data Integrity | High                    | Depends on implementation  |
| Flexibility    | Less flexible           | Highly flexible            |

---

## Choosing the Right Database

The choice between relational and non-relational databases depends on:

* Nature of the data
* Application requirements
* Scalability needs
* Data consistency requirements

Both types have advantages and tradeoffs, and selecting the right one is critical for building efficient applications.
