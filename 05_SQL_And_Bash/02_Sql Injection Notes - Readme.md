# SQL Injection – Notes

## What Is SQL Injection?

SQL Injection is a **web security vulnerability** in which an attacker manipulates or interferes with the SQL queries that a web application sends to its database. By inserting **malicious SQL code** into user input fields, an attacker can make the database execute unintended commands.

This usually happens when user input is directly included in SQL queries using **string concatenation or interpolation** without proper validation or protection.

---

## How SQL Injection Happens

Web applications often take user input from:

* Login forms
* Search boxes
* URL parameters

If this input is directly added to SQL queries, attackers can inject harmful SQL code.

### Example of a Vulnerable Query

```
SELECT * FROM users WHERE username = 'username_input' AND password = 'password_input';
```

Here, the username and password are directly embedded into the SQL query.

If an attacker enters the following in the username field:

```
" " OR "1"="1" --
```

And anything in the password field, the query becomes:

```
WHERE username = " " OR TRUE
```

Since `1 = 1` is always true and `--` comments out the rest of the query, the condition always passes. This may allow the attacker to log in without valid credentials.

---

## Impact of SQL Injection Attacks

Depending on the attacker’s goal, SQL injection can:

* Bypass authentication
* Steal sensitive data from the database
* Modify database records
* Delete data or entire tables
* Gain unauthorized access to the database

Because of these risks, SQL injection is considered a **serious security threat**.

---

## How to Prevent SQL Injection

There are two main strategies to prevent SQL injection attacks:

### 1. Avoid Dynamic SQL with String Concatenation

Never build SQL queries by directly concatenating user input into strings.

---

### 2. Use Parameterized Statements (Prepared Statements)

Parameterized queries separate **SQL code** from **user data**. The database treats user input strictly as data, not executable SQL.

This is the **most effective method** to prevent SQL injection.

---

## Input Validation

Input validation is an important **secondary security measure**. It ensures that user input follows expected formats and values.

It is especially important for:

* Table names
* Column names
* Sorting order (ASC/DESC)

Whenever possible:

* Do NOT accept table or column names from user input
* Define them directly in the application code

---

## Limiting Database Permissions

Even if an SQL injection attack occurs, its impact can be reduced by using **least-privilege access**:

* Grant only required permissions to database users
* Use read-only access where possible
* Never assign admin privileges to application database accounts

Giving admin access is extremely dangerous because attackers could gain full control over the database.

---

## Why Developers Must Take SQL Injection Seriously

SQL injection is one of the **most common web attacks**. Every developer must understand how it works and how to prevent it.

By using parameterized queries, validating input, and restricting database permissions, you can protect your application and keep user data safe.

---

## Questions and Answers

### 1. What is the primary goal of an SQL injection attack?

**Answer:** To interfere with the database queries executed by an application.

### 2. Which is the most effective way to prevent SQL injection?

**Answer:** Using parameterized statements or queries.

### 3. What can an attacker do if a login form is vulnerable to SQL injection?

**Answer:** Bypass the login process without valid credentials.
