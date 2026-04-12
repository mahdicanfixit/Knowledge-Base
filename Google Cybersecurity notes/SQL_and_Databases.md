
*Back to [[Google Cybersecurity Knowledge Base]]*

# SQL & Database Security

## 1. Database Concepts
* **Database vs. Spreadsheet:** Spreadsheets are for individuals; Databases are for massive, simultaneous access.
* **Relational Database:** Stores data in tables that are linked together.
* **SQL (Structured Query Language):** The programming language used to talk to the database.

### Table Structure
* **Field/Column:** The category of data (e.g., `employee_id`, `username`).
* **Record/Row:** A single entry (e.g., `1001`, `jsmith`).
* **Primary Key:** A unique ID for every row (Cannot be empty/null).
* **Foreign Key:** Links to a Primary Key in another table (Can have duplicates).

---

## 2. SQL Syntax Cheat Sheet

| **Join Type**       | **Description**                                                           |
| ------------------- | ------------------------------------------------------------------------- |
| **INNER JOIN**      | Returns rows that have matching values in _both_ tables (The overlap).    |
| **LEFT JOIN**       | Returns _all_ rows from the Left table, and matching rows from the Right. |
| **RIGHT JOIN**      | Returns _all_ rows from the Right table, and matching rows from the Left. |
| **FULL OUTER JOIN** | Returns _all_ rows from both tables, regardless of match.                 |
|                     |                                                                           |
|                     |                                                                           |
### Basic Query
The standard structure of a request:
```sql
SELECT column_name
FROM table_name;
