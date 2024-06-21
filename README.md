# NNN
Nerd Nurturing Network

## What is this repository for?
This repository is for practicing sharing code relating to SQL projects and supporting the Nerd Nurturing Network.

## AdventureWorks 2022
We will be using the version available here: https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2022.bak

For instructions on how to install this on your home PC: https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms

## Software Prerequisites
- Visual Studio 2022 (Community is free)
    - Include: Data Storage and Processing
  ![image](https://github.com/Clanatk/NNN/assets/33404493/7705e83d-7e80-4b1a-ad10-d63be4fc023d)

- SQL Server 2022 (Developer Edition)
    - TODO: Setup Instructions

## Github Usage
- Each person should maintain their own branch. Committing changes directly to the main branch is not permitted!

# SQL Best Practices for Beginners (ANSI Standards)

## Introduction
This document provides best practices for writing SQL code, using ANSI standards. Examples will be provided in T-SQL. We will use PascalCase for table and column names, ensure all tables are in First Normal Form (1NF), and name constraints using the format `TableName_ColumnName_xx`, where `xx` denotes the constraint type (e.g., pk, uk, fk).

## Understanding First Normal Form (1NF)
First Normal Form (1NF) is a property of a relation in a relational database. A table is in 1NF if:
1. All columns contain atomic, indivisible values.
2. Each column contains values of a single data type.
3. Each column name is unique.
4. The order in which data is stored does not matter.

### Example of a 1NF Table
```sql
CREATE TABLE Employee (
    EmployeeID INT PRIMARY KEY,
    FirstName NVARCHAR(50),
    LastName NVARCHAR(50),
    DateOfBirth DATE,
    Email NVARCHAR(100)
);
```

## Naming Conventions
- **Tables and Columns**: Use PascalCase (e.g., `Employee`, `FirstName`).
- **Constraints**: Use the format `TableName_ColumnName_xx` (e.g., `Employee_EmployeeID_pk`).

## Common SQL Operations

### SELECT
```sql
SELECT FirstName, LastName, Email
FROM Employee;
```

### INSERT
```sql
INSERT INTO Employee (FirstName, LastName, DateOfBirth, Email)
VALUES ('John', 'Doe', '1985-06-15', 'john.doe@example.com');
```

### UPDATE
```sql
UPDATE Employee
SET Email = 'john.newemail@example.com'
WHERE EmployeeID = 1;
```

### DELETE
```sql
DELETE FROM Employee
WHERE EmployeeID = 1;
```

## Stored Procedures and Error Handling

### Basic Stored Procedure with Error Handling
```sql
CREATE PROCEDURE AddEmployee
    @FirstName NVARCHAR(50),
    @LastName NVARCHAR(50),
    @DateOfBirth DATE,
    @Email NVARCHAR(100)
AS
BEGIN
    BEGIN TRY
        INSERT INTO Employee (FirstName, LastName, DateOfBirth, Email)
        VALUES (@FirstName, @LastName, @DateOfBirth, @Email);
    END TRY
    BEGIN CATCH
        PRINT 'Error occurred while adding an employee.';
    END CATCH
END;
```

## Indexing Best Practices
- **Primary Key Index**: Automatically created when a primary key is defined.
- **Clustered Index**: One per table, usually on the primary key.
- **Non-Clustered Index**: Use for columns frequently used in WHERE clauses or joins.

### Example of Creating an Index
```sql
CREATE INDEX IX_Employee_Email
ON Employee (Email);
```

## Basic Security Best Practices
- **Avoid SQL Injection**: Use parameterized queries or stored procedures.
- **Least Privilege**: Grant only the necessary permissions to users.
- **Encrypt Sensitive Data**: Use encryption for sensitive information.

### Example of a Parameterized Query
```sql
DECLARE @Email NVARCHAR(100);
SET @Email = 'john.doe@example.com';

SELECT FirstName, LastName
FROM Employee
WHERE Email = @Email;
```

## Joins and Subqueries

### INNER JOIN
```sql
SELECT e.FirstName, e.LastName, d.DepartmentName
FROM Employee e
INNER JOIN Department d ON e.DepartmentID = d.DepartmentID;
```

### Subquery
```sql
SELECT FirstName, LastName
FROM Employee
WHERE EmployeeID IN (SELECT EmployeeID FROM DepartmentEmployee WHERE DepartmentID = 1);
```

## Choosing Data Types
- Use appropriate data types for the data to ensure data integrity and optimize storage.
- Example: Use `INT` for numeric values without decimals, `DECIMAL` for precise numbers, `NVARCHAR` for variable-length strings.

## Self-Documenting Code
- **Logical Names**: Use meaningful names for tables, columns, and variables.
- **DRY Principle**: Avoid duplicating code by using views, stored procedures, and functions.
- **Comments**: Add comments where necessary to explain complex logic.

### Example of Logical Names and DRY Principle
```sql
-- Table with logical names
CREATE TABLE Employee (
    EmployeeID INT PRIMARY KEY,
    FirstName NVARCHAR(50),
    LastName NVARCHAR(50),
    DateOfBirth DATE,
    Email NVARCHAR(100)
);

-- View to avoid duplicating SELECT logic
CREATE VIEW EmployeeBasicInfo AS
SELECT FirstName, LastName, Email
FROM Employee;
```

## Basic Performance Optimization
- **Indexes**: Use indexes to speed up queries.
- **Query Optimization**: Write efficient queries, avoid unnecessary columns in SELECT statements.
- **Avoid Cursors**: Use set-based operations instead of cursors where possible.

### Example of Query Optimization
```sql
-- Efficient query by selecting only necessary columns
SELECT FirstName, LastName
FROM Employee
WHERE DateOfBirth > '1980-01-01';
```

By following these best practices, you can write clean, efficient, and maintainable SQL code.
