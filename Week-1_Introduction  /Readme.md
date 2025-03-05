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
 
  # SQL Constraints: Ensuring Data Integrity in Databases

SQL constraints are rules enforced on data columns in a table to maintain accuracy, consistency, and reliability in the database. They restrict the type of data that can be entered into a column, ensuring data integrity.

Constraints can be applied at two levels:
- **Column-level**: Applied to a specific column.
- **Table-level**: Applied to multiple columns or the entire table.

## Types of SQL Constraints

### 1. NOT NULL Constraint
The `NOT NULL` constraint ensures that a column cannot store `NULL` values. This means that every row must have a valid (non-null) value for this column.

#### Example:
```sql
CREATE TABLE Students (
  StudentID INT NOT NULL,
  Name VARCHAR(100) NOT NULL,
  Age INT
);
```
Use case: The Name column must always have a value, ensuring that no student record can be created without a name.

### 2. DEFAULT Constraint
The DEFAULT constraint assigns a default value to a column when no value is provided during insertion.

### Example:
```sql
CREATE TABLE Employees (
  EmployeeID INT NOT NULL,
  Name VARCHAR(100),
  Salary DECIMAL(10, 2) DEFAULT 50000.00
);
```
Use case: If no salary is provided for an employee, the Salary column will default to 50,000.
### 3. UNIQUE Constraint
The UNIQUE constraint ensures that all values in a column are different. It prevents duplicate entries in a column.

### Example
```sql
CREATE TABLE Users (
  UserID INT NOT NULL,
  Email VARCHAR(100) UNIQUE,
  Name VARCHAR(100)
);
```
Use case: The Email column must have unique values, ensuring no two users have the same email address

### 4. PRIMARY KEY Constraint
The PRIMARY KEY constraint uniquely identifies each record in a table. It enforces both the UNIQUE and NOT NULL constraints on a column or a group of columns.

### Example:
```sql
CREATE TABLE Products (
  ProductID INT PRIMARY KEY,
  ProductName VARCHAR(100)
);
```
Use case: The ProductID column uniquely identifies each product in the table and cannot have NULL values.
A table can only have one PRIMARY KEY, and it can consist of one or multiple columns (Composite Key).

### 5. FOREIGN KEY Constraint
A FOREIGN KEY is a column (or a group of columns) that links two tables by referring to the PRIMARY KEY of another table. It maintains referential integrity between related tables.

### Example:
```sql
CREATE TABLE Orders (
  OrderID INT PRIMARY KEY,
  CustomerID INT,
  FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

Use case: In the Orders table, the CustomerID is a FOREIGN KEY referencing the CustomerID in the Customers table. This ensures that an order is always associated with an existing customer.

### 6. CHECK Constraint
The CHECK constraint ensures all values in a column meet a specific condition.

### Example:
```sql
CREATE TABLE Employees (
  EmployeeID INT PRIMARY KEY,
  Name VARCHAR(100),
  Age INT CHECK (Age >= 18)
);
```
Use case: The Age column should only allow values greater than or equal to 18, preventing invalid entries.

### 7. INDEX
An INDEX is used to speed up searches and queries by creating an internal structure that allows quick data retrieval. It does not enforce data constraints but improves performance.

### Example:
```sql
CREATE INDEX idx_email ON Users (Email);
```

# Summary of SQL Constraints

| **Constraint**   | **Description**                                                 |
|------------------|-----------------------------------------------------------------|
| **NOT NULL**     | Ensures no `NULL` values in a column.                          |
| **DEFAULT**      | Provides a default value if none is specified.                  |
| **UNIQUE**       | Ensures all values in a column are distinct.                    |
| **PRIMARY KEY**  | Uniquely identifies each record and prevents `NULL` values.     |
| **FOREIGN KEY**  | Links two tables and ensures referential integrity.             |
| **CHECK**        | Ensures that data meets specified conditions.                   |
| **INDEX**        | Improves query performance by speeding up searches.             |




