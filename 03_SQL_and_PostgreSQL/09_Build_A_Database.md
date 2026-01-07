# Mario Database Project (PostgreSQL)

## Overview

This project is part of the **freeCodeCamp Relational Database** curriculum. It demonstrates how to design, create, populate, and query a relational database using **PostgreSQL**. The database models characters from the Mario universe and shows practical usage of **primary keys, foreign keys, one-to-one relationships, one-to-many relationships, and many-to-many relationships**.

---

## Technologies Used

* PostgreSQL 12+
* SQL (DDL & DML)
* psql (PostgreSQL CLI)
* Bash (command-line interaction)

---

## Database Name

`mario_database`

---

## Step 1: Database Setup

### Terminate Existing Connections

Before recreating the database, existing connections are terminated:

```sql
SELECT pg_terminate_backend(pg_stat_activity.pid)
FROM pg_stat_activity
WHERE usename = 'freecodecamp';
```

### Create the Database

```sql
DROP DATABASE IF EXISTS mario_database;
CREATE DATABASE mario_database;
```

Connect to the database:

```sql
\connect mario_database
```

---

## Step 2: Tables and Schema Design

### 1. characters Table

Stores basic information about Mario characters.

**Columns:**

* `character_id` (Primary Key)
* `name`
* `homeland`
* `favorite_color`

This table represents the **main entity** of the database.

---

### 2. more_info Table (One-to-One Relationship)

Stores additional information for each character.

**Columns:**

* `more_info_id` (Primary Key)
* `birthday`
* `height_in_cm`
* `weight_in_kg`
* `character_id` (Foreign Key, UNIQUE)

Each character can have **only one** record in this table.

---

### 3. sounds Table (One-to-Many Relationship)

Stores sound files associated with characters.

**Columns:**

* `sound_id` (Primary Key)
* `filename` (UNIQUE)
* `character_id` (Foreign Key)

One character can have **multiple sounds**, but each sound belongs to **one character**.

---

### 4. actions Table

Stores actions that characters can perform.

**Columns:**

* `action_id` (Primary Key)
* `action` (UNIQUE)

Examples: run, jump, duck

---

### 5. character_actions Table (Many-to-Many Relationship)

Implements a many-to-many relationship between characters and actions.

**Columns:**

* `character_id` (Foreign Key)
* `action_id` (Foreign Key)

**Composite Primary Key:**

* (`character_id`, `action_id`)

This table allows:

* One character to perform many actions
* One action to be performed by many characters

---

## Step 3: Sequences and Auto-Increment

Sequences are used to auto-generate primary key values:

* `characters_character_id_seq`
* `more_info_more_info_id_seq`
* `sounds_sound_id_seq`
* `actions_action_id_seq`

These sequences are linked to their respective ID columns using `DEFAULT nextval(...)`.

---

## Step 4: Data Insertion

Sample data is inserted for:

* Characters (Mario, Luigi, Peach, etc.)
* Actions (run, jump, duck)
* Sounds (voice clips)
* Additional character information
* Character-action mappings

This ensures the database is fully populated and ready for querying.

---

## Step 5: Constraints Used

### Primary Keys

Ensure each record is uniquely identifiable.

### Foreign Keys

Maintain relationships between tables:

* `more_info.character_id → characters.character_id`
* `sounds.character_id → characters.character_id`
* `character_actions.character_id → characters.character_id`
* `character_actions.action_id → actions.action_id`

### Unique Constraints

Prevent duplicate data:

* Unique action names
* Unique sound filenames
* One-to-one enforcement in `more_info`

---

## Step 6: Example Queries and JOINs

### Characters with Additional Info

Uses INNER JOIN between `characters` and `more_info`.

### Characters with Sounds

Uses LEFT JOIN to include characters without sounds.

### Characters with Actions

Uses JOIN across three tables:

* `characters`
* `character_actions`
* `actions`

This demonstrates a **many-to-many JOIN**.

---

## Database Tables Summary

| Table Name        | Relationship Type |
| ----------------- | ----------------- |
| characters        | Main Entity       |
| more_info         | One-to-One        |
| sounds            | One-to-Many       |
| actions           | Lookup Table      |
| character_actions | Many-to-Many      |

---

## Learning Outcomes

By completing this project, you learn:

* How to design a normalized relational database
* How to use primary and foreign keys effectively
* How to implement one-to-one, one-to-many, and many-to-many relationships
* How to use PostgreSQL sequences
* How to write JOIN queries across multiple tables

---

## Conclusion

This Mario Database project is a complete example of relational database design and querying using PostgreSQL. It reflects real-world database patterns and is an excellent foundation for building more complex SQL-based applications.
