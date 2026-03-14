
# 🗄️ MySQL Database – Complete Beginner Guide

## 🚀 Introduction

**MySQL** is one of the most popular **relational database management systems (RDBMS)** used in the world. It allows you to **store, manage, and query structured data efficiently**.

MySQL is widely used in:

* Web applications (like WordPress, e-commerce sites)
* Enterprise software
* Data-driven applications

This guide will teach you **MySQL fundamentals**, best practices, and practical examples for both beginners and professionals.

---

# 📌 What is a Database?

A **database** is a collection of organized data that can be easily accessed, managed, and updated.

A **relational database** stores data in **tables** with **rows and columns**, making it easier to query using **SQL (Structured Query Language)**.

---

# ⚙️ MySQL Installation & Setup

### 1️⃣ Install MySQL

* Windows: Download from [MySQL Official Site](https://dev.mysql.com/downloads/)
* macOS: Use Homebrew

  ```bash id="mysql1"
  brew install mysql
  ```
* Linux: Use package managers like apt or yum

Check installation:

```bash id="mysql2"
mysql --version
```

---

### 2️⃣ Start MySQL Server

```bash id="mysql3"
# Start MySQL server
sudo service mysql start

# Login to MySQL
mysql -u root -p
```

---

# 🧩 MySQL Database Basics

### 1️⃣ Create Database

```sql id="mysql4"
CREATE DATABASE my_database;
```

### 2️⃣ Use Database

```sql id="mysql5"
USE my_database;
```

### 3️⃣ Show Databases

```sql id="mysql6"
SHOW DATABASES;
```

---

# 🗂️ Tables in MySQL

Tables store data in **rows and columns**.

### 1️⃣ Create Table

```sql id="mysql7"
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### 2️⃣ Show Tables

```sql id="mysql8"
SHOW TABLES;
```

### 3️⃣ Describe Table

```sql id="mysql9"
DESCRIBE users;
```

---

# 🔄 CRUD Operations

### 1️⃣ Insert Data

```sql id="mysql10"
INSERT INTO users (name, email) VALUES ('Bikash', 'bikash@example.com');
```

### 2️⃣ Select Data

```sql id="mysql11"
SELECT * FROM users;
SELECT name, email FROM users WHERE id=1;
```

### 3️⃣ Update Data

```sql id="mysql12"
UPDATE users
SET email='bikashd@example.com'
WHERE id=1;
```

### 4️⃣ Delete Data

```sql id="mysql13"
DELETE FROM users WHERE id=1;
```

---

# 🔍 Filtering & Sorting

### WHERE Clause

```sql id="mysql14"
SELECT * FROM users WHERE name='Bikash';
```

### ORDER BY

```sql id="mysql15"
SELECT * FROM users ORDER BY created_at DESC;
```

### LIMIT

```sql id="mysql16"
SELECT * FROM users LIMIT 5;
```

---

# 📊 Aggregate Functions

* `COUNT()` – Count rows
* `SUM()` – Total sum
* `AVG()` – Average value
* `MIN()` / `MAX()` – Minimum/Maximum

Example:

```sql id="mysql17"
SELECT COUNT(*) FROM users;
SELECT AVG(id) FROM users;
```

---

# 🔗 Joins in MySQL

Joins are used to combine data from multiple tables.

### Example Tables

```sql id="mysql18"
CREATE TABLE orders (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    product VARCHAR(50),
    FOREIGN KEY(user_id) REFERENCES users(id)
);
```

### INNER JOIN Example

```sql id="mysql19"
SELECT users.name, orders.product
FROM users
INNER JOIN orders ON users.id = orders.user_id;
```

---

# 🧩 Indexes & Keys

Indexes improve query performance:

```sql id="mysql20"
CREATE INDEX idx_name ON users(name);
```

Primary keys uniquely identify rows:

```sql id="mysql21"
PRIMARY KEY(id)
```

Foreign keys enforce **relationships between tables**.

---

# 🔐 Security & Permissions

Granting user access:

```sql id="mysql22"
CREATE USER 'dev'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON my_database.* TO 'dev'@'localhost';
FLUSH PRIVILEGES;
```

---

# 🧪 Backup & Restore

### Backup

```bash id="mysql23"
mysqldump -u root -p my_database > backup.sql
```

### Restore

```bash id="mysql24"
mysql -u root -p my_database < backup.sql
```

---

# 📚 Best Practices

* Always **use primary keys**
* Normalize tables to reduce redundancy
* Use **indexes** on frequently queried columns
* Regularly **backup** databases
* Use **parameterized queries** to prevent SQL injection

---

# 🎯 Summary Roadmap

1. Learn **SQL basics** – SELECT, INSERT, UPDATE, DELETE
2. Understand **database design** – tables, columns, primary/foreign keys
3. Learn **joins, indexes, aggregate functions**
4. Learn **user management and security**
5. Practice **backup and restore**
6. Explore **advanced topics** – triggers, stored procedures, views, transactions

---

# 🔮 Conclusion

MySQL is a **powerful and reliable RDBMS** used by millions of developers worldwide.

By learning:

* Database design
* CRUD operations
* Joins and indexes
* Security and backups

you can **build robust, scalable, and secure applications**.

Consistent practice with real projects will make you **confident in database management**.

---

⭐ If you found this guide helpful, consider starring the repository and sharing it with other developers.
