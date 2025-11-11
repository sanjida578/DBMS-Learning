# 💻 Class 3 — Student Table in MariaDB

---

## 🖥️ Terminal Session Overview

```text
Microsoft Windows [Version 10.0.22631.6060]
(c) Microsoft Corporation. All rights reserved.

C:\Users\USER>mysql -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
```

---

## 🔹 Show Existing Databases

```sql
SHOW DATABASES;
```

**Terminal Output:**
```text
+--------------------+
| Database           |
+--------------------+
| ecommerce          |
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
6 rows in set (0.038 sec)
```

> ❌ ভুল কমান্ডের উদাহরণ:
```sql
SHOW DATABASE;
```
- Syntax Error হয় কারণ সঠিক কমান্ড হলো `SHOW DATABASES;`

---

## 🔹 Create New Database

```sql
CREATE DATABASE sbgem;
USE sbgem;
```

**Terminal Output:**
```text
Query OK, 1 row affected (0.002 sec)
Database changed
```

---

## 🔹 Show Tables in Database

```sql
SHOW TABLES;
```

**Terminal Output:**
```text
Empty set (0.001 sec)
```

---

## 🔹 Create `students` Table

```sql
CREATE TABLE students(
    name VARCHAR(100),
    phone VARCHAR(15),
    email VARCHAR(100),
    roll VARCHAR(10),
    class ENUM('1','2','3','4','5','6','7','8','9')
);
```

**Terminal Output:**
```text
Query OK, 0 rows affected (0.043 sec)
```

---

## 🔹 Show Tables After Creation

```sql
SHOW TABLES;
```

**Terminal Output:**
```text
+-----------------+
| Tables_in_sbgem |
+-----------------+
| students        |
+-----------------+
1 row in set (0.001 sec)
```

---

## 🔹 Describe Table Structure

```sql
DESCRIBE students;
```

**Terminal Output:**
```text
+-------+-------------------------------------------+------+-----+---------+-------+
| Field | Type                                      | Null | Key | Default | Extra |
+-------+-------------------------------------------+------+-----+---------+-------+
| name  | varchar(100)                              | YES  |     | NULL    |       |
| phone | varchar(15)                               | YES  |     | NULL    |       |
| email | varchar(100)                              | YES  |     | NULL    |       |
| roll  | varchar(10)                               | YES  |     | NULL    |       |
| class | enum('1','2','3','4','5','6','7','8','9') | YES  |     | NULL    |       |
+-------+-------------------------------------------+------+-----+---------+-------+
5 rows in set (0.089 sec)
```

---

## 🔹 Insert Data into `students` Table

```sql
INSERT INTO students(name, phone, email)
VALUES
("sanjida","013#######","sa@gmail.com"),
("Bristy","017#######","br@gmail.com"),
("sweety","012#######","sw@gmail.com"),
("misty","013#######","mi@gmail.com");
```

**Terminal Output:**
```text
Query OK, 4 rows affected (0.091 sec)
Records: 4  Duplicates: 0  Warnings: 0
```

---

## 🔹 Select Data from Table

```sql
SELECT * FROM students;
```

**Terminal Output:**
```text
+---------+------------+--------------+------+-------+
| name    | phone      | email        | roll | class |
+---------+------------+--------------+------+-------+
| sanjida | 013####### | sa@gmail.com | NULL | NULL  |
| Bristy  | 017####### | br@gmail.com | NULL | NULL  |
| sweety  | 012####### | sw@gmail.com | NULL | NULL  |
| misty   | 013####### | mi@gmail.com | NULL | NULL  |
+---------+------------+--------------+------+-------+
4 rows in set (0.001 sec)
```

---

> ✅ **Summary:**  
এই ক্লাসে আমরা শিখেছি:  
- Database তৈরি ও ব্যবহার  
- Table তৈরি করা (students)  
- Table structure দেখা (`DESCRIBE`)  
- ডাটাবেসে ডাটা insert ও select করা  
- ENUM data type এবং VARCHAR ব্যবহার  

---# 💻 Class 3 — Student Table in MariaDB

---

## 🖥️ Terminal Session Overview

```text
Microsoft Windows [Version 10.0.22631.6060]
(c) Microsoft Corporation. All rights reserved.

C:\Users\USER>mysql -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
```

---

## 🔹 Show Existing Databases

```sql
SHOW DATABASES;
```

**Terminal Output:**
```text
+--------------------+
| Database           |
+--------------------+
| ecommerce          |
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
6 rows in set (0.038 sec)
```

> ❌ ভুল কমান্ডের উদাহরণ:
```sql
SHOW DATABASE;
```
- Syntax Error হয় কারণ সঠিক কমান্ড হলো `SHOW DATABASES;`

---

## 🔹 Create New Database

```sql
CREATE DATABASE sbgem;
USE sbgem;
```

**Terminal Output:**
```text
Query OK, 1 row affected (0.002 sec)
Database changed
```

---

## 🔹 Show Tables in Database

```sql
SHOW TABLES;
```

**Terminal Output:**
```text
Empty set (0.001 sec)
```

---

## 🔹 Create `students` Table

```sql
CREATE TABLE students(
    name VARCHAR(100),
    phone VARCHAR(15),
    email VARCHAR(100),
    roll VARCHAR(10),
    class ENUM('1','2','3','4','5','6','7','8','9')
);
```

**Terminal Output:**
```text
Query OK, 0 rows affected (0.043 sec)
```

---

## 🔹 Show Tables After Creation

```sql
SHOW TABLES;
```

**Terminal Output:**
```text
+-----------------+
| Tables_in_sbgem |
+-----------------+
| students        |
+-----------------+
1 row in set (0.001 sec)
```

---

## 🔹 Describe Table Structure

```sql
DESCRIBE students;
```

**Terminal Output:**
```text
+-------+-------------------------------------------+------+-----+---------+-------+
| Field | Type                                      | Null | Key | Default | Extra |
+-------+-------------------------------------------+------+-----+---------+-------+
| name  | varchar(100)                              | YES  |     | NULL    |       |
| phone | varchar(15)                               | YES  |     | NULL    |       |
| email | varchar(100)                              | YES  |     | NULL    |       |
| roll  | varchar(10)                               | YES  |     | NULL    |       |
| class | enum('1','2','3','4','5','6','7','8','9') | YES  |     | NULL    |       |
+-------+-------------------------------------------+------+-----+---------+-------+
5 rows in set (0.089 sec)
```

---

## 🔹 Insert Data into `students` Table

```sql
INSERT INTO students(name, phone, email)
VALUES
("sanjida","013#######","sa@gmail.com"),
("Bristy","017#######","br@gmail.com"),
("sweety","012#######","sw@gmail.com"),
("misty","013#######","mi@gmail.com");
```

**Terminal Output:**
```text
Query OK, 4 rows affected (0.091 sec)
Records: 4  Duplicates: 0  Warnings: 0
```

---

## 🔹 Select Data from Table

```sql
SELECT * FROM students;
```

**Terminal Output:**
```text
+---------+------------+--------------+------+-------+
| name    | phone      | email        | roll | class |
+---------+------------+--------------+------+-------+
| sanjida | 013####### | sa@gmail.com | NULL | NULL  |
| Bristy  | 017####### | br@gmail.com | NULL | NULL  |
| sweety  | 012####### | sw@gmail.com | NULL | NULL  |
| misty   | 013####### | mi@gmail.com | NULL | NULL  |
+---------+------------+--------------+------+-------+
4 rows in set (0.001 sec)
```

---

> ✅ **Summary:**  
এই ক্লাসে আমরা শিখেছি:  
- Database তৈরি ও ব্যবহার  
- Table তৈরি করা (students)  
- Table structure দেখা (`DESCRIBE`)  
- ডাটাবেসে ডাটা insert ও select করা  
- ENUM data type এবং VARCHAR ব্যবহার  

---
