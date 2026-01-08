# Bash and SQL Review – README

## Overview

This document is a complete review of **Bash scripting and SQL concepts**. It is written in easy English and structured as notes, covering database normalization, SQL usage with Bash, security topics like SQL Injection, and performance issues like the N+1 problem. Nothing important has been skipped.

---

## Database Normalization

Database normalization is the process of organizing a relational database to reduce data redundancy and improve data integrity.

### Benefits of Normalization

* Reduces duplicated data, saving storage space
* Prevents data inconsistencies
* Improves data integrity using primary and foreign keys
* Makes databases easier to maintain and understand

### Normal Forms

#### 1NF (First Normal Form)

* Each cell contains a single (atomic) value
* Each record is unique (primary key)
* Order of rows and columns does not matter
* Example: Move multiple phone numbers into a separate `student_phones` table

#### 2NF (Second Normal Form)

* Must satisfy 1NF
* No partial dependency on a composite key
* Example: Split an `orders` table into `order_header` and `order_items`

#### 3NF (Third Normal Form)

* Must satisfy 2NF
* No transitive dependency (non-key depends on non-key)
* Example: Move `city_postal_code` into a `cities` table

#### BCNF (Boyce-Codd Normal Form)

* Stronger version of 3NF
* Every determinant must be a superkey
* Tip: 3NF is usually enough for most systems

---

## Key SQL Concepts

* SQL (Structured Query Language) is used to communicate with relational databases
* Common commands: SELECT, INSERT, UPDATE, DELETE, CREATE, ALTER
* JOINs combine data from multiple tables (INNER, LEFT, RIGHT, FULL)

---

## Running SQL Commands Using Bash

### Run SQL Directly

**PostgreSQL:**

* Use `psql` command-line tool

**MySQL:**

* Use `mysql` client

### Run SQL from a File

* PostgreSQL: `psql -f script.sql`
* MySQL: `mysql < script.sql`

---

## Embedding SQL in Bash Scripts

You can embed SQL queries inside Bash scripts using variables.

* Variables make scripts reusable
* Always sanitize variables to avoid SQL injection

---

## Retrieving SQL Results in Bash

### Capture Single Value

* Use command substitution `$( )`
* Useful for counts and calculations

### Retrieve Multiple Rows and Columns

* Use formatting options like `-t -A -F","`
* Loop through results using `while read`

---

## SQL Injection

SQL Injection is a security vulnerability where attackers insert malicious SQL code into input fields.

### Possible Attacks

* Bypass authentication
* Steal sensitive data
* Modify or delete records

### Example

A condition like `OR "1"="1"` always returns true and can bypass login checks.

---

## Preventing SQL Injection

* Use Prepared / Parameterized Statements
* Validate and sanitize user input
* Apply least privilege principle
* Never give admin rights to application accounts

---

## N+1 Problem

The N+1 problem happens when:

* 1 query fetches a list of records
* N additional queries fetch related data

### Why It Is Bad

* Too many database round trips
* Slower performance
* Increased load time

### Solution

* Use JOINs to fetch all related data in one query
* Prefer set-based operations

---

## Assignment

* Review all Bash and SQL concepts
* Understand normalization, security, and performance topics
* Complete and submit the assignment

---

## Conclusion

This README provides a complete and structured review of Bash and SQL topics, focusing on best practices, security, and performance optimization. It is suitable for revision, notes, and practical understanding.
