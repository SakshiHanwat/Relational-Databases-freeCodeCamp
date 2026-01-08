# Relational Databases, Bash, SQL, and Git – Complete Review Notes

## 1. Terminal, Shell, and Command Line Basics

The command line is a text-based interface where users type commands to interact with the operating system. A terminal is the application that gives access to the command line, while a terminal emulator is an enhanced terminal with extra features. A shell is the program that interprets and executes the commands entered in the terminal, such as Bash. On Windows, common command-line tools include PowerShell, Command Prompt, and Microsoft Terminal. On macOS, the built-in Terminal app is used, along with third-party tools like iTerm or Ghostty. On Linux, terminal options vary by distribution, with popular emulators like kitty. Although the terms terminal, shell, and command line are often used interchangeably, they each have specific meanings.

## 2. Command Line Shortcuts

Arrow keys allow you to move through previously executed commands. The Tab key helps autocomplete commands and file names. Control + L on Linux/macOS or typing cls on Windows clears the terminal screen. Control + C interrupts a running command, and in PowerShell it can also copy selected text. Control + Z on Linux/macOS suspends a running task, which can be resumed using the fg command. Using !! reruns the last executed command instantly.

## 3. Bash Basics

Bash (Bourne Again Shell) is a widely used shell in Unix-like systems. Common commands include pwd to show the current directory, cd to change directories, ls to list files and folders, mkdir to create directories, rmdir to remove empty directories, touch to create files, mv to move or rename files, cp to copy files, rm to delete files, echo to print text or variables, exit to leave the terminal, clear to clear the screen, and find to search for files. Commands like cat, less, and more are used to view file contents in different ways. The man command provides manual pages for commands.

## 4. Command Options and Flags

Options or flags modify how commands behave. Long-form options use two hyphens, such as --help or --version. Short-form options use one hyphen, such as -a or -l. Multiple short options can be combined together. The --help flag is commonly used to quickly understand available options for any command.

## 5. Introduction to Relational Databases

Relational databases organize data into tables consisting of rows and columns. Each row represents a record, and each column represents an attribute. They are scalable, structured, and widely used in domains like web development, healthcare, e-commerce, and enterprise systems.

## 6. Key Database Concepts

A schema defines the structure of a database, including tables, columns, data types, constraints, and relationships. Primary keys uniquely identify each row in a table. Foreign keys reference primary keys in other tables to establish relationships. Entity Relationship Diagrams (ERDs) visually represent how tables relate to each other. Data integrity ensures consistency and accuracy of data.

## 7. SQL Basics

SQL queries are used to retrieve and manipulate data. The SELECT statement retrieves data, and the WHERE clause filters results. ORDER BY is used to sort query results.

## 8. Table Operations

CREATE TABLE creates new tables. ALTER TABLE is used to add, drop, or rename columns. DROP TABLE deletes an entire table. ALTER DATABASE RENAME renames a database, and DROP DATABASE removes it completely.

## 9. Constraints and Data Integrity

Constraints enforce rules on data. NOT NULL prevents null values, PRIMARY KEY ensures uniqueness, FOREIGN KEY links tables, UNIQUE ensures unique values, and composite primary keys use multiple columns. Constraints can be added or removed using ALTER TABLE.

## 10. Data Manipulation (CRUD)

INSERT adds new records, UPDATE modifies existing records, and DELETE removes records. Multiple rows can be inserted in a single statement.

## 11. Data Types

Common data types include NUMERIC, TEXT, INTEGER, SMALLINT, BIGINT, SERIAL or AUTO_INCREMENT for auto-incrementing values, VARCHAR, DATE, TIME, TIMESTAMP, and BOOLEAN.

## 12. Database Relationships

Relational databases support one-to-one, one-to-many, many-to-many (using junction tables), and self-referencing relationships.

## 13. Advanced SQL (Joins)

INNER JOIN returns matching rows, LEFT JOIN returns all rows from the left table, RIGHT JOIN returns all rows from the right table, FULL OUTER JOIN returns all rows from both tables, SELF JOIN joins a table with itself, and CROSS JOIN returns a Cartesian product.

## 14. PostgreSQL Specific Commands

psql is used to interact with PostgreSQL. Commands like \l list databases, \c connects to a database, \d lists tables, \d table_name shows table structure, and \q exits psql.

## 15. Relational vs Non-Relational Databases

Relational databases use structured schemas and ensure consistency, while NoSQL databases are schema-less and flexible. The choice depends on application requirements.

## 16. Popular RDBMS

Common systems include MySQL, PostgreSQL, SQLite, Microsoft SQL Server, and Oracle Database.

## 17. Bash Scripting Basics

Bash scripts are files containing Bash commands. Scripts start with a shebang (#!/bin/bash). Variables are created using VARIABLE=value and accessed using $VARIABLE. User input is handled with read, and comments are added using #.

## 18. Conditionals and Expressions

[[ ]] is used for string, numeric, and file comparisons. (( )) is used for arithmetic operations. Logical operators like &&, ||, and ! combine conditions.

## 19. Loops and Arrays

Loops include while, until, and for loops. Arrays store multiple values and are accessed using indexes.

## 20. Functions

Functions group reusable code blocks and can accept arguments like $1, $2, etc.

## 21. Random Numbers and Math

$RANDOM generates random numbers. Arithmetic operations use (( )) or $(( )).

## 22. Environment and System Info

Environment variables like $HOME, $PATH, and $LANG store system information. Commands like printenv and declare inspect variables.

## 23. File Permissions and Scripts

chmod +x gives execute permission to scripts. Scripts can be run using sh, bash, or ./script.sh.

## 24. Database Normalization

Normalization reduces data redundancy and improves integrity. Normal forms include 1NF, 2NF, 3NF, and BCNF.

## 25. SQL with Bash

SQL commands can be run from Bash using tools like psql or mysql. Query results can be captured into variables and processed in loops.

## 26. SQL Injection and N+1 Problem

SQL injection is a security vulnerability where malicious SQL is injected into queries. It is prevented using prepared statements and validation. The N+1 problem occurs when multiple queries are executed unnecessarily instead of using joins.

## 27. Version Control with Git

Git is a version control system used to track changes. GitHub and GitLab are cloud-based providers. Common Git commands include init, status, add, commit, log, push, pull, clone, branch, merge, reset, and rebase.

## 28. Branching and Collaboration

Branches allow isolated development. Pull requests enable code review and collaboration. Forking allows contributing to external repositories.

## 29. SSH and GPG Keys

SSH keys authenticate secure connections. GPG keys are used to sign commits for verification. Git can be configured to automatically sign commits.

---

These notes provide a complete, structured review of terminal usage, Bash scripting, relational databases, SQL, Git, and collaboration workflows. They are suitable for revision, assignments, and interview preparation.
