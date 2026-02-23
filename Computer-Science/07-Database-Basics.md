# Database Basics

A database is an organized collection of structured data, stored and accessed electronically. Databases are essential for almost all applications, including websites, apps, and systems.

---

## 1. What is a Database?
A database stores data in a structured way so that it can be easily:
- Stored
- Retrieved
- Updated
- Deleted
- Analyzed

---

## 2. Types of Databases

### 2.1 Relational Database (RDBMS)
- Data stored in **tables** (rows & columns)
- Uses **SQL** (Structured Query Language)
- Follows ACID properties
- Examples: MySQL, PostgreSQL, SQLite, SQL Server, Oracle

### 2.2 NoSQL Database
- Non-relational
- For unstructured / semi-structured data
- High scalability
- Types:
  - Document (MongoDB)
  - Key-Value (Redis)
  - Columnar (Cassandra)
  - Graph (Neo4j)

---

## 3. Basic Database Concepts

### Table
A collection of related data organized in rows and columns.

### Row (Record / Tuple)
A single entry in a table.

### Column (Field / Attribute)
A category of data (e.g., name, age, id).

### Primary Key
A unique identifier for each row.
- Cannot be null
- No duplicates

### Foreign Key
A field that refers to the primary key of another table.
- Used to **link tables**
- Creates relationships

---

## 4. SQL Basics

SQL = Structured Query Language

### 4.1 DML – Data Manipulation Language
- `SELECT` – Query data
- `INSERT` – Add new data
- `UPDATE` – Modify data
- `DELETE` – Remove data

### 4.2 DDL – Data Definition Language
- `CREATE` – Create table/database
- `ALTER` – Modify structure
- `DROP` – Delete table/database
- `TRUNCATE` – Remove all data

### 4.3 Basic Examples

#### Create Table
```sql
CREATE TABLE users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER,
    email TEXT UNIQUE
);
```

#### Insert
```sql
INSERT INTO users (name, age, email)
VALUES ('Alice', 20, 'alice@example.com');
```

#### Select
```sql
SELECT * FROM users WHERE age > 18;
```

#### Update
```sql
UPDATE users SET age = 21 WHERE id = 1;
```

#### Delete
```sql
DELETE FROM users WHERE id = 1;
```

---

## 5. Keys

### Primary Key
Unique identifier for a table.

### Foreign Key
Links to another table’s primary key.

### Unique Key
No duplicate values, but can be null.

### Composite Key
Key made from multiple columns.

---

## 6. Relationships Between Tables

### One to One
- One user ↔ one profile

### One to Many
- One author ↔ many posts

### Many to Many
- Many students ↔ many courses
- Uses a **junction table**

---

## 7. Indexes
Speed up `SELECT` queries.
- Makes reading faster
- Slows down `INSERT`, `UPDATE`, `DELETE`

---

## 8. ACID Properties (RDBMS)
Guarantee reliable transactions:
- **Atomicity** – All or nothing
- **Consistency** – Data remains valid
- **Isolation** – Transactions don’t interfere
- **Durability** – Data persists after commit

---

## 9. Normalization
Organize tables to:
- Reduce redundancy
- Avoid anomalies
- Improve integrity

Common forms: 1NF, 2NF, 3NF, BCNF

---

## 10. Common Database Interview Questions
1. What is a database?
2. RDBMS vs NoSQL
3. What is SQL?
4. What is a primary key / foreign key?
5. Explain one-to-many / many-to-many
6. What is a transaction?
7. Explain ACID properties
8. What is normalization?
9. What is an index? Pros and cons
10. Difference between DELETE and TRUNCATE
