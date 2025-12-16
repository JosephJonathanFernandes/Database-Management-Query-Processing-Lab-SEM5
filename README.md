# Database Management & Query Processing Lab - Semester 5

[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](LICENSE)
[![SQL](https://img.shields.io/badge/Language-SQL-orange.svg)]()
[![MariaDB](https://img.shields.io/badge/Database-MariaDB%2010.4-blue.svg)]()
[![Status](https://img.shields.io/badge/Status-Learning%20%7C%20Non--Production-yellow.svg)]()

> **Academic Project** | Computer Science & Engineering | Semester 5 (2024)

> **Learning-only notice:** This repository is maintained as an educational lab. Do not deploy directly to production systems or use with real-world/PII datasets.

## 📚 Course Overview

This repository contains a comprehensive collection of database management and query processing laboratory experiments completed during the 5th semester. The lab focuses on practical implementation of database concepts using SQL and MariaDB/MySQL.

### Learning Objectives

- Understanding relational database design and normalization
- Mastering SQL query writing and optimization
- Implementing database constraints and integrity rules
- Working with stored procedures, triggers, and functions
- Learning transaction management and concurrency control
- Exploring database indexing and performance tuning

## ✅ Project Status & Intended Use

- Status: Active learning repository (non-production)
- Scope: Coursework examples for database management and query processing
- Data: Use only synthetic/sample data—never real customer or personal data
- Secrets: Do not commit credentials, connection strings, or API keys (see [SECURITY.md](SECURITY.md))

## 📂 Repository Structure

```
Database-Management-Query-Processing-Lab-SEM5/
├── Experiment 1/        # Database Creation & DDL Operations
├── Experiment 2/        # DML Operations & Data Manipulation
├── Experiment 3/        # SQL Queries & Joins
├── Experiment 4/        # Advanced Queries & Aggregations
├── Experiment 5/        # Subqueries & Nested Queries
├── Experiment 6/        # Views & Index Management
├── Experiment 7/        # Database Constraints
├── Experiment 8/        # Transaction Management
├── Experiment 9/        # Stored Procedures
├── Experiment 10/       # Triggers & Automation
└── LICENSE
```

## 🧪 Experiments Overview

### Experiment 1: Database Creation & DDL
- Creating databases and tables
- Defining primary keys and foreign keys
- Understanding data types and constraints
- **Files**: `expt1.sql`, `expt1_final.txt`

### Experiment 2: DML Operations
- INSERT, UPDATE, DELETE operations
- Data manipulation techniques
- Bulk data operations
- **Files**: `expt2.sql`, `expt2a.sql`

### Experiment 3: SQL Queries & Joins
- SELECT statements and filtering
- INNER JOIN, LEFT JOIN, RIGHT JOIN
- CROSS JOIN and SELF JOIN
- **Files**: SQL scripts and raw output files

### Experiment 4: Advanced Queries
- Complex WHERE clauses
- ORDER BY and GROUP BY
- HAVING clause
- **Files**: `expt4.sql`

### Experiment 5: Subqueries
- Nested SELECT statements
- Correlated subqueries
- EXISTS and IN operators
- **Files**: `expt5.sql`

### Experiment 6: Views & Indexes
- Creating and managing views
- Index creation and optimization
- Performance analysis
- **Files**: `expt6.sql`, `expt6_updated.sql`

### Experiment 7: Database Constraints
- CHECK constraints
- UNIQUE constraints
- NOT NULL constraints
- **Files**: `expt6_updated.sql`

### Experiment 8: Transaction Management
- BEGIN, COMMIT, ROLLBACK
- ACID properties
- Transaction isolation levels
- **Files**: Raw output and typescript files

### Experiment 9: Stored Procedures
- Creating stored procedures
- Parameter passing
- Procedure execution
- **Files**: `procedures.txt`, SQL scripts

### Experiment 10: Triggers
- BEFORE and AFTER triggers
- INSERT, UPDATE, DELETE triggers
- Trigger automation
- **Files**: `triggers.txt`, `table_trigger.sql`

## 🛠️ Technologies Used

- **Database**: MariaDB 10.4.32 / MySQL
- **Tools**: phpMyAdmin, MySQL Workbench, Command Line Interface
- **Language**: SQL (Structured Query Language)
- **Version Control**: Git & GitHub

## 🚀 Getting Started

### Prerequisites

- MariaDB 10.4+ or MySQL 8.0+
- phpMyAdmin (optional, for GUI)
- MySQL Command Line Client

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/Database-Management-Query-Processing-Lab-SEM5.git
   cd Database-Management-Query-Processing-Lab-SEM5
   ```

2. **Start your database server**
   ```bash
   # For MariaDB/MySQL on Linux
   sudo systemctl start mariadb
   
   # For Windows (XAMPP/WAMP)
   # Start MySQL service from control panel
   ```

3. **Run experiments**
   ```bash
   # Connect to MySQL
   mysql -u root -p
   
   # Execute an experiment
   source "Experiment 1/expt1.sql"
   ```

### Running Individual Experiments

Each experiment folder contains:
- `.sql` files: Main SQL scripts to execute
- `.txt` files: Output results and documentation
- `typescript.txt`: Terminal session recordings

To run an experiment:
```sql
-- Method 1: From MySQL CLI
mysql -u root -p < "Experiment 1/expt1.sql"

-- Method 2: Inside MySQL
USE expt1;
SOURCE /path/to/expt1.sql;
```

## 📊 Database Schema

The experiments primarily use a common schema involving:

- **Dept** (Department)
  - Deptno (Primary Key)
  - dname
  - location

- **Employee**
  - Empno (Primary Key)
  - ename
  - job
  - mgr
  - hiredate
  - salary
  - commission
  - Deptno (Foreign Key)

*Note: Specific schemas may vary by experiment. Refer to individual SQL files for details.*

## 📝 Documentation

Each experiment folder contains:
- **SQL Scripts**: Complete, executable SQL code
- **Raw Output Files**: Actual query results and outputs
- **Typescript Files**: Terminal session recordings showing execution

## 🔒 Security & Responsible Use

- No secrets in this repo: remove or rotate any accidental credentials immediately (see [SECURITY.md](SECURITY.md))
- Run scripts only in disposable dev environments; do not point at production databases
- Use test data only—scrub any PII before sharing outputs
- Keep local `.env` or config files untracked; sample placeholders are preferred

## 🎓 Learning Outcomes

Upon completing these experiments, students will be able to:

- ✅ Design and implement relational databases
- ✅ Write complex SQL queries for data retrieval
- ✅ Implement database constraints and ensure data integrity
- ✅ Create and manage stored procedures and triggers
- ✅ Understand transaction management and concurrency
- ✅ Optimize database performance using indexes
- ✅ Apply normalization principles
- ✅ Handle real-world database scenarios

## 🤝 Contributing

This is an academic project, but suggestions and improvements are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 👨‍💻 Author

**Alex Joaquim Pereira**
- Academic Year: 2024-2025
- Semester: 5
- Course: Database Management Systems Lab

## 📄 License

This project is licensed under the BSD 3-Clause License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Course instructors and teaching assistants
- MariaDB and MySQL documentation
- Fellow students for collaborative learning

## 📚 References

- [MariaDB Documentation](https://mariadb.com/kb/en/)
- [MySQL Documentation](https://dev.mysql.com/doc/)
- [SQL Tutorial - W3Schools](https://www.w3schools.com/sql/)
- Database System Concepts by Silberschatz, Korth, and Sudarshan

---

**⚠️ Academic Integrity Notice**

This repository is meant for educational purposes and reference. If you're a student working on similar assignments, please use this as a learning resource and reference, but ensure you complete your own work according to your institution's academic integrity policies.

---

<div align="center">
  <sub>Built with 💻 during Semester 5 | Database Management Systems Lab</sub>
</div>
