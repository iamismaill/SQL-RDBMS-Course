# Chapter One: Introduction to SQL, Constraints & SQL Data Types

## Overview

Structured Query Language (SQL) is a powerful and widely used language for managing and manipulating relational databases. SQL allows you to interact with databases to store, retrieve, update, and delete data. In this section, we will cover the fundamental concepts and syntax of SQL.

---

## History of SQL

- **1970** — Dr. E. F. "Ted" of IBM is known as the father of relational databases. He described a relational model for databases.
- **1974** — Structured Query Language appeared.
- **1978** — IBM worked to develop Codd's ideas and released a product named System/R.
- **1986** — IBM developed the first prototype of relational database and standardized by ANSI. The first relational database was released by Relational Software and later became Oracle.

---

## Database Basics

A database is an organized collection of data stored in a structured format. It consists of tables, which hold the data, and relationships between the tables. Each table consists of rows (also known as records) and columns (also known as fields). Columns define the type of data that can be stored, such as text, numbers, or dates.

---

## SQL Statements

SQL operates through various statements that allow you to perform different actions on the database. The most common SQL statements are:

- **SELECT**: Retrieves data from one or more tables.
- **INSERT**: Adds new data into a table.
- **UPDATE**: Modifies existing data in a table.
- **DELETE**: Removes data from a table.

---

## Syntax and Structure

SQL statements follow a specific syntax and structure. Here's a basic structure of a `SELECT` statement:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

---
## SQL Queries and RDBMS Concepts

This document covers the essential SQL queries and concepts used in Relational Database Management Systems (RDBMS). It includes instructions for querying, inserting, updating, and deleting data, as well as filtering and sorting data.
---
## Querying Data

To retrieve data from a database, you use the `SELECT` statement. You can specify the columns you want to retrieve and apply various conditions to filter the data.

### Example:
```sql
SELECT column1, column2
FROM table_name;
```
This statement retrieves the values from column1 and column2 in the table_name table.
---
# SQL Data Operations

## Filtering Data
You can filter the retrieved data using the `WHERE` clause. It allows you to specify conditions to match specific records.

### Example:
```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```
## Condition Operators:
= : Equal to
<> : Not equal to
< : Less than
> : Greater than
<= : Less than or equal to
>= : Greater than or equal to


# RDBMS Concepts

A table in a Relational Database Management System (RDBMS) is a structured collection of related data organized in rows and columns. It represents a real-world entity (e.g., Students, Employees, Products).

## Structure of a Table

A table consists of:
- **Columns (Fields/Attributes)**: Define the type of data stored (e.g., id, name, age).
- **Rows (Records)**: Represent actual data entries in the table.
## Example: Student Table

Below is an example of a simple **Student** table in an RDBMS.

| **StudentID** | **Name**  | **Age** | **Major**      |
|---------------|-----------|---------|----------------|
| 1             | John Doe  | 20      | Computer Science|
| 2             | Jane Smith| 22      | Mathematics    |
| 3             | Alice Lee | 21      | Physics        |

### Table Breakdown:
- **Columns**:
  - `StudentID`: A unique identifier for each student.
  - `Name`: The name of the student.
  - `Age`: The age of the student.
  - `Major`: The student's major in university.

- **Rows**:
  - Each row in this table represents an individual student's record.
