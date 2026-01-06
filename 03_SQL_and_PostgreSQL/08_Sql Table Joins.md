# SQL Table JOIN Operations

## Introduction

In SQL, **JOIN** operations are used to combine related information from multiple tables. While relational databases organize data into separate tables, JOINs allow you to query related data across these tables efficiently.

There are several types of JOIN operations:

* INNER JOIN
* FULL OUTER JOIN
* LEFT OUTER JOIN
* RIGHT OUTER JOIN
* SELF JOIN
* CROSS JOIN

---

## INNER JOIN

An **INNER JOIN** returns only rows where the values in the joining columns match in both tables. Essentially, it gives the intersection of the data.

### Example Tables

**Products Table:**

| product_id | product_name     | category  | price (USD) | origin    |
| ---------- | ---------------- | --------- | ----------- | --------- |
| 1          | Ice Cream        | Food      | 2.50        | India     |
| 2          | Pizza Margherita | Food      | 12.00       | Italy     |
| 3          | Sushi            | Food      | 18.75       | Japan     |
| 4          | T-Shirt          | Clothing  | 25.00       | USA       |
| 5          | Jeans            | Clothing  | 60.00       | Argentina |
| 6          | Coffee           | Beverages | 35.00       | France    |
| 7          | Juice            | Beverages | 5.00        | Colombia  |

**Sales Table:**

| sale_id | product_id | quantity | sale_date  |
| ------- | ---------- | -------- | ---------- |
| 101     | 1          | 2        | 2025-07-18 |
| 102     | 2          | 3        | 2025-02-13 |
| 103     | 6          | 10       | 2025-06-08 |
| 104     | 5          | 8        | 2025-01-10 |
| 105     | 2          | 1        | 2025-05-15 |

### INNER JOIN Query

```sql
SELECT *
FROM products
INNER JOIN sales
  ON products.product_id = sales.product_id;
```

**Result:**

Only products that have corresponding sales appear in the result.

---

## FULL OUTER JOIN

A **FULL OUTER JOIN** returns all rows from both tables. Matching rows are combined, while unmatched columns are filled with NULL values.

### Query

```sql
SELECT *
FROM products
FULL OUTER JOIN sales
  ON products.product_id = sales.product_id;
```

**Result:**

All products and sales records are included, with NULLs where no match exists.

---

## LEFT OUTER JOIN

A **LEFT OUTER JOIN** returns all rows from the left table, along with matching rows from the right table. Unmatched right-table columns are NULL.

### Query

```sql
SELECT *
FROM products
LEFT JOIN sales
  ON products.product_id = sales.product_id;
```

**Result:**

All products are included. If a product has no sales, the sales columns contain NULL.

---

## RIGHT OUTER JOIN

A **RIGHT OUTER JOIN** returns all rows from the right table, along with matching rows from the left table. Unmatched left-table columns are NULL.

### Query

```sql
SELECT *
FROM products
RIGHT JOIN sales
  ON products.product_id = sales.product_id;
```

**Result:**

All sales records are included. If a sale does not have a corresponding product, product columns are NULL.

---

## SELF JOIN

A **SELF JOIN** allows a table to join with itself. This is useful for comparing different rows within the same table.

---

## CROSS JOIN

A **CROSS JOIN** (Cartesian Join) combines every row from the first table with every row from the second table, generating all possible combinations. No join condition is needed.

---

## Summary

* **INNER JOIN:** Returns only matching rows.
* **FULL OUTER JOIN:** Returns all rows from both tables; unmatched columns are NULL.
* **LEFT OUTER JOIN:** Returns all rows from the left table; unmatched right columns are NULL.
* **RIGHT OUTER JOIN:** Returns all rows from the right table; unmatched left columns are NULL.
* **SELF JOIN:** Joins a table with itself.
* **CROSS JOIN:** Returns all combinations of rows from both tables.

These JOIN operations are essential for querying and analyzing relational data efficiently.

---

## Questions

1. **Which SQL JOIN operation returns only the rows where there is a match in both tables based on the join condition?**

   * LEFT JOIN
   * **INNER JOIN**
   * RIGHT JOIN
   * FULL JOIN

2. **Which SQL JOIN operation would you use if you need to retrieve all customers (left) and, for each customer, any orders (right) they might have placed? Customers with no orders should still be included in the result.**

   * **LEFT JOIN**
   * INNER JOIN
   * RIGHT JOIN
   * FULL JOIN

3. **Which SQL JOIN operation returns all rows from both tables, including unmatched rows (with NULLs for the columns of the table without a match)?**

   * LEFT JOIN
   * INNER JOIN
   * RIGHT JOIN
   * **FULL JOIN**
