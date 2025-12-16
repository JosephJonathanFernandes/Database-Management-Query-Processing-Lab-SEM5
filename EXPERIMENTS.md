# Experiments Overview

This document provides a detailed overview of all laboratory experiments in the Database Management & Query Processing course.

## 📑 Table of Contents

1. [Experiment 1: Database Creation & DDL](#experiment-1-database-creation--ddl)
2. [Experiment 2: DML Operations](#experiment-2-dml-operations)
3. [Experiment 3: SQL Queries & Joins](#experiment-3-sql-queries--joins)
4. [Experiment 4: Advanced Queries](#experiment-4-advanced-queries)
5. [Experiment 5: Subqueries](#experiment-5-subqueries)
6. [Experiment 6: Views & Indexes](#experiment-6-views--indexes)
7. [Experiment 7: Database Constraints](#experiment-7-database-constraints)
8. [Experiment 8: Transaction Management](#experiment-8-transaction-management)
9. [Experiment 9: Stored Procedures](#experiment-9-stored-procedures)
10. [Experiment 10: Triggers](#experiment-10-triggers)

---

## Experiment 1: Database Creation & DDL

### Objective
Learn to create databases, define tables, and implement Data Definition Language (DDL) commands.

### Topics Covered
- CREATE DATABASE
- CREATE TABLE
- ALTER TABLE
- DROP TABLE
- PRIMARY KEY and FOREIGN KEY constraints
- Data types in SQL

### Key Concepts
- Database schema design
- Relational database structure
- Entity-Relationship modeling
- Referential integrity

### Files
- `expt1.sql` - Main SQL script
- `expt1_final.txt` - Output and results
- `expt1.txt` - Additional documentation

### Sample Operations
```sql
CREATE DATABASE expt1;
CREATE TABLE Dept (
    Deptno INT PRIMARY KEY,
    dname VARCHAR(25) NOT NULL,
    location VARCHAR(20)
);
```

---

## Experiment 2: DML Operations

### Objective
Master Data Manipulation Language (DML) commands for inserting, updating, and deleting data.

### Topics Covered
- INSERT INTO statements
- UPDATE statements
- DELETE statements
- Bulk data operations
- Data validation

### Key Concepts
- Data insertion techniques
- Conditional updates
- Safe deletion practices
- Transaction safety

### Files
- `expt2.sql` - Main DML script
- `expt2a.sql` - Additional operations
- `expt2_raw_1.txt`, `expt2_raw_2.txt` - Output files

### Sample Operations
```sql
INSERT INTO Employee VALUES (1001, 'John Doe', 'Manager', NULL, '2024-01-15', 75000, 5000, 10);
UPDATE Employee SET salary = salary * 1.1 WHERE Deptno = 10;
DELETE FROM Employee WHERE emp_status = 'Inactive';
```

---

## Experiment 3: SQL Queries & Joins

### Objective
Learn to write complex SELECT queries and understand different types of JOIN operations.

### Topics Covered
- SELECT statements
- INNER JOIN
- LEFT JOIN / RIGHT JOIN
- FULL OUTER JOIN
- CROSS JOIN
- SELF JOIN

### Key Concepts
- Query optimization
- Join algorithms
- Cartesian products
- Multi-table queries

### Files
- SQL scripts with various join examples
- `expt3_raw_1.txt`, `expt3_raw_2.txt` - Query outputs

---

## Experiment 4: Advanced Queries

### Objective
Explore advanced querying techniques including grouping, aggregation, and filtering.

### Topics Covered
- GROUP BY clause
- HAVING clause
- Aggregate functions (COUNT, SUM, AVG, MIN, MAX)
- ORDER BY
- DISTINCT keyword
- LIMIT clause

### Key Concepts
- Data aggregation
- Statistical queries
- Result set ordering
- Duplicate elimination

### Files
- `expt4.sql` - Advanced query script
- `expt4_raw_1.txt` - Query results
- `typescript.txt` - Terminal session

### Sample Operations
```sql
SELECT Deptno, COUNT(*) as emp_count, AVG(salary) as avg_salary
FROM Employee
GROUP BY Deptno
HAVING COUNT(*) > 5
ORDER BY avg_salary DESC;
```

---

## Experiment 5: Subqueries

### Objective
Understand and implement nested queries and subqueries.

### Topics Covered
- Subqueries in SELECT
- Subqueries in WHERE
- Subqueries in FROM
- Correlated subqueries
- EXISTS operator
- IN operator
- ANY and ALL operators

### Key Concepts
- Query nesting
- Correlated vs. non-correlated subqueries
- Subquery optimization
- Set operations

### Files
- `expt5.sql` - Subquery examples
- `expt5_raw_1.txt` - Results
- `typescript.txt` - Execution log

### Sample Operations
```sql
SELECT emp_name 
FROM Employee 
WHERE salary > (SELECT AVG(salary) FROM Employee);

SELECT * FROM Employee e
WHERE EXISTS (SELECT 1 FROM Dept d WHERE d.Deptno = e.Deptno AND d.location = 'New York');
```

---

## Experiment 6: Views & Indexes

### Objective
Learn to create and manage database views and optimize queries using indexes.

### Topics Covered
- CREATE VIEW
- Updatable views
- CREATE INDEX
- UNIQUE INDEX
- DROP INDEX
- Query performance analysis

### Key Concepts
- View abstraction
- Index types (B-tree, Hash)
- Query optimization
- Index selection strategies

### Files
- `expt6.sql` - View and index definitions
- `expt6_updated.sql` - Updated version
- `expt6_raw_1.txt`, `expt6_raw_2.txt` - Outputs
- `typescript_6.txt`, `typescript_6_1.txt` - Sessions

### Sample Operations
```sql
CREATE VIEW HighEarners AS
SELECT emp_name, salary, dname
FROM Employee e JOIN Dept d ON e.Deptno = d.Deptno
WHERE salary > 70000;

CREATE INDEX idx_salary ON Employee(salary);
```

---

## Experiment 7: Database Constraints

### Objective
Implement and understand various database constraints for data integrity.

### Topics Covered
- NOT NULL constraint
- UNIQUE constraint
- CHECK constraint
- DEFAULT values
- Constraint naming
- Adding/dropping constraints

### Key Concepts
- Data integrity enforcement
- Domain constraints
- Business rule implementation
- Constraint validation

### Files
- `expt6_updated.sql` - Constraint implementations
- `typescript.txt` - Test results

---

## Experiment 8: Transaction Management

### Objective
Understand transaction concepts and implement transaction control.

### Topics Covered
- BEGIN TRANSACTION
- COMMIT
- ROLLBACK
- SAVEPOINT
- ACID properties
- Isolation levels

### Key Concepts
- Atomicity
- Consistency
- Isolation
- Durability
- Concurrency control
- Deadlock handling

### Files
- `expt8_raw_1.txt` - Transaction examples
- `typescript.txt` - Execution trace

### Sample Operations
```sql
START TRANSACTION;
UPDATE Account SET balance = balance - 1000 WHERE account_id = 101;
UPDATE Account SET balance = balance + 1000 WHERE account_id = 102;
COMMIT;
```

---

## Experiment 9: Stored Procedures

### Objective
Create and execute stored procedures for reusable database logic.

### Topics Covered
- CREATE PROCEDURE
- IN, OUT, INOUT parameters
- Control flow (IF, CASE, LOOP)
- Exception handling
- CALL statement
- DROP PROCEDURE

### Key Concepts
- Procedural SQL
- Code reusability
- Parameter passing
- Business logic encapsulation

### Files
- `expt6_updated.sql` - Procedure definitions
- `procedures.txt` - Documentation
- `typescript_9.txt`, `typescript_9_1.txt` - Execution logs

### Sample Operations
```sql
DELIMITER //
CREATE PROCEDURE GetEmployeeCount(IN dept_id INT, OUT emp_count INT)
BEGIN
    SELECT COUNT(*) INTO emp_count
    FROM Employee
    WHERE Deptno = dept_id;
END //
DELIMITER ;

CALL GetEmployeeCount(10, @count);
```

---

## Experiment 10: Triggers

### Objective
Implement database triggers for automated actions and data validation.

### Topics Covered
- CREATE TRIGGER
- BEFORE INSERT/UPDATE/DELETE
- AFTER INSERT/UPDATE/DELETE
- NEW and OLD references
- Trigger activation
- DROP TRIGGER

### Key Concepts
- Event-driven programming
- Automated data validation
- Audit trail implementation
- Cascading operations
- Trigger timing and scope

### Files
- `table_trigger.sql` - Trigger definitions
- `alex_exp10.sql` - Additional triggers
- `triggers.txt` - Documentation
- `expt6_updated.sql` - Updated implementation
- `raw_10_1.txt`, `raw_10_2.txt` - Test outputs
- `typescript.txt` - Execution trace

### Sample Operations
```sql
CREATE TRIGGER before_employee_insert
BEFORE INSERT ON Employee
FOR EACH ROW
BEGIN
    IF NEW.salary < 0 THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Salary cannot be negative';
    END IF;
END;

CREATE TRIGGER after_employee_delete
AFTER DELETE ON Employee
FOR EACH ROW
BEGIN
    INSERT INTO EmployeeAudit VALUES (OLD.Empno, OLD.emp_name, NOW());
END;
```

---

## 🎯 Learning Path

### Beginner Level (Experiments 1-3)
- Database fundamentals
- Basic SQL commands
- Simple queries and joins

### Intermediate Level (Experiments 4-6)
- Advanced querying
- Query optimization
- Database objects (views, indexes)

### Advanced Level (Experiments 7-10)
- Constraints and integrity
- Transactions
- Procedural SQL
- Automation with triggers

---

## 📊 Skills Matrix

| Experiment | DDL | DML | Queries | Advanced SQL | Performance | Automation |
|------------|-----|-----|---------|--------------|-------------|------------|
| 1          | ⭐⭐⭐ | ⭐   | ⭐       | -            | -           | -          |
| 2          | ⭐   | ⭐⭐⭐ | ⭐       | -            | -           | -          |
| 3          | -   | ⭐   | ⭐⭐⭐     | ⭐            | -           | -          |
| 4          | -   | -   | ⭐⭐⭐     | ⭐⭐          | ⭐           | -          |
| 5          | -   | -   | ⭐⭐      | ⭐⭐⭐         | ⭐           | -          |
| 6          | ⭐⭐  | -   | ⭐⭐      | ⭐⭐          | ⭐⭐⭐         | -          |
| 7          | ⭐⭐  | -   | -       | ⭐⭐          | ⭐           | -          |
| 8          | -   | ⭐⭐  | -       | ⭐⭐⭐         | ⭐⭐          | -          |
| 9          | ⭐   | ⭐   | ⭐       | ⭐⭐⭐         | ⭐           | ⭐⭐         |
| 10         | ⭐   | ⭐   | -       | ⭐⭐          | ⭐           | ⭐⭐⭐        |

---

## 🔍 Quick Reference

### Most Common Patterns

**Find employees in a specific department:**
```sql
SELECT e.* FROM Employee e 
JOIN Dept d ON e.Deptno = d.Deptno 
WHERE d.dname = 'Sales';
```

**Calculate department-wise statistics:**
```sql
SELECT d.dname, COUNT(*) as emp_count, AVG(e.salary) as avg_salary
FROM Employee e JOIN Dept d ON e.Deptno = d.Deptno
GROUP BY d.dname;
```

**Find employees earning above average:**
```sql
SELECT * FROM Employee 
WHERE salary > (SELECT AVG(salary) FROM Employee);
```

---

## 📚 Additional Resources

- [SQL Tutorial](https://www.sqltutorial.org/)
- [MariaDB KB](https://mariadb.com/kb/en/)
- [MySQL Reference](https://dev.mysql.com/doc/refman/8.0/en/)
- [Database Normalization](https://en.wikipedia.org/wiki/Database_normalization)

---

*Last Updated: December 2024*
