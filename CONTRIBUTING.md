# Contributing to Database Management Lab

Thank you for your interest in contributing to this project! This is an academic repository, but we welcome suggestions, improvements, and corrections.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Guidelines](#guidelines)
- [Style Guide](#style-guide)
- [Commit Messages](#commit-messages)

## 🤝 Code of Conduct

This project adheres to academic integrity principles. Please:

- Be respectful and constructive in all interactions
- Provide proper attribution for any borrowed code or concepts
- Help maintain the educational value of this repository
- Follow your institution's academic integrity policies

## 🎯 How Can I Contribute?

### Reporting Issues

If you find any issues with the SQL scripts or documentation:

1. Check if the issue already exists in the Issues tab
2. Create a new issue with a clear title and description
3. Include relevant details:
   - Which experiment/file is affected
   - Expected vs. actual behavior
   - Steps to reproduce (if applicable)
   - Your database version and environment

### Suggesting Enhancements

Enhancement suggestions are welcome! Consider:

- Query optimization improvements
- Better documentation or comments
- Additional test cases
- Alternative approaches to problems
- Correcting errors or mistakes

### Pull Requests

1. **Fork the repository** and create your branch from `main`
   ```bash
   git checkout -b feature/improvement-name
   ```

2. **Make your changes**
   - Follow the SQL style guide below
   - Add comments to explain complex queries
   - Test your changes thoroughly

3. **Commit your changes**
   ```bash
   git commit -m "feat: Add description of changes"
   ```
   
4. **Keep secrets out of git**
   - Never commit passwords, API keys, connection strings, or `.env` files
   - Use placeholders in examples (e.g., `DB_USER=student`, `DB_PASS=changeme`)
   - If you spot a secret, rotate it and open a removal PR immediately (see [SECURITY.md](SECURITY.md))

4. **Push to your fork**
   ```bash
   git push origin feature/improvement-name
   ```

5. **Open a Pull Request**
   - Provide a clear description of changes
   - Reference any related issues
   - Explain the reasoning behind your changes

## 📝 Guidelines

### SQL Scripts

- **Formatting**: Use consistent indentation (2 or 4 spaces)
- **Comments**: Add comments for complex queries
- **Testing**: Test all queries before submitting
- **Compatibility**: Ensure compatibility with MariaDB 10.4+ / MySQL 8.0+

### Documentation

- Use clear, concise language
- Include code examples where helpful
- Keep README.md up to date
- Add screenshots for visual clarification (if needed)

### File Organization

- Keep experiment files in their respective folders
- Name files descriptively: `expt[number]_[description].sql`
- Include output files with `_raw` or `_output` suffix
- Don't commit temporary or generated files

## 🎨 Style Guide

### SQL Code Style

```sql
-- Use uppercase for SQL keywords
SELECT column_name
FROM table_name
WHERE condition = value;

-- Use lowercase for database objects
CREATE TABLE employee (
  emp_id INT PRIMARY KEY,
  emp_name VARCHAR(50) NOT NULL,
  dept_id INT,
  FOREIGN KEY (dept_id) REFERENCES department(dept_id)
);

-- Indent nested queries
SELECT e.emp_name,
       (SELECT d.dept_name 
        FROM department d 
        WHERE d.dept_id = e.dept_id) AS department
FROM employee e;

-- Add comments for complex logic
-- Calculate total salary with bonus
SELECT emp_name,
       salary + COALESCE(bonus, 0) AS total_compensation
FROM employee;
```

### Comments

```sql
-- Single-line comments for brief explanations

/*
 * Multi-line comments for:
 * - Complex query explanations
 * - Algorithm descriptions
 * - Important notes and warnings
 */
```

### Naming Conventions

- **Tables**: `PascalCase` or `snake_case` (be consistent)
- **Columns**: `snake_case` or `camelCase` (be consistent)
- **Constraints**: Descriptive names (e.g., `fk_employee_department`)
- **Indexes**: `idx_tablename_columnname`

## 📨 Commit Messages

Follow conventional commit format:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- `feat`: New feature or experiment
- `fix`: Bug fix or correction
- `docs`: Documentation changes
- `style`: Code formatting (no logic change)
- `refactor`: Code restructuring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### Examples

```bash
feat(expt5): Add correlated subquery examples

fix(expt3): Correct JOIN syntax in query 5

docs(readme): Update installation instructions

refactor(expt8): Optimize transaction queries for better performance
```

## 🧪 Testing Your Changes

Before submitting:

1. **Test SQL scripts**
   ```bash
   mysql -u root -p < your_script.sql
   ```

2. **Verify output**
   - Check that queries return expected results
   - Ensure no syntax errors
   - Verify data integrity

3. **Check compatibility**
   - Test on MariaDB 10.4+
   - Test on MySQL 8.0+ (if possible)
   - Use non-production databases and synthetic data only

4. **Review documentation**
   - Update README.md if needed
   - Add comments to new code
   - Check for typos

## ❓ Questions?

If you have questions about contributing:

- Open an issue with the `question` label
- Refer to the main [README.md](README.md)
- Check existing issues and pull requests

## 📚 Resources

- [SQL Style Guide](https://www.sqlstyle.guide/)
- [MariaDB Documentation](https://mariadb.com/kb/en/)
- [MySQL Documentation](https://dev.mysql.com/doc/)
- [Conventional Commits](https://www.conventionalcommits.org/)

---

Thank you for contributing to this educational project! Your improvements help future students learn database management more effectively. 🎓
