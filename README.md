# 🏫 Class 1 — Introduction to DBMS

## 1️⃣ Termux Setup for Database

- Termux ইন্সটল করো  
- MariaDB বা MySQL প্যাকেজ ইন্সটল করো:  
```bash
pkg install mariadb
```
- সার্ভার স্টার্ট করো:  
```bash
mysqld_safe &
```
- MariaDB এ প্রবেশ করো:  
```bash
mysql -u root
```

> এখন তুমি Database তৈরি এবং SQL commands ব্যবহার করতে প্রস্তুত।  

---

## 2️⃣ What is DBMS?

**DBMS (Database Management System)** → এমন software যা ডাটাকে **store, manage এবং organize** করে।  

### Key Points:
- ডাটা সংরক্ষণ করে **efficient এবং secure** ভাবে।  
- SQL ব্যবহার করে ডাটা **query এবং manipulate** করা যায়।  
- উদাহরণ: MySQL, MariaDB, PostgreSQL, Oracle DB  

---

## 3️⃣ Why DBMS?

- ডাটার **consistency** ও **integrity** বজায় রাখে  
- ডাটার **security** নিশ্চিত করে  
- সহজে **search, update, delete** করা যায়  

> ✅ DBMS শেখার মাধ্যমে তুমি Structured Data handle করতে পারবে এবং real-world applications এ কাজ করতে পারবে।


# 🏫 Class 2 — Step by Step Database Tutorial

Step by Step গাইড আমাদের **Database এবং Table তৈরি** করার জন্য।  

---

## 📝 আমাদের কাজ

### 1️⃣ Database তৈরি করা
**Cmd:**  
```sql
SHOW databases;
```
> এই কমান্ড দিয়ে আগে থেকে থাকা ডাটাবেসগুলো দেখা যায়।  

**Cmd (নতুন Database তৈরি করার জন্য):**  
```sql
CREATE DATABASE DatabaseName;
```
> এখানে `DatabaseName` এর জায়গায় নিজের ডাটাবেসের নাম ব্যবহার করবে।  

---

### 2️⃣ Database-এ প্রবেশ করা
**Cmd:**  
```sql
USE DatabaseName;
```
> এটি তোমাকে নির্দিষ্ট ডাটাবেসে প্রবেশ করাবে।  

---

### 3️⃣ টেবিল তৈরি করা
**Cmd:**  
```sql
CREATE TABLE product(
    Name VARCHAR(100),
    Description VARCHAR(100),
    Price INT,
    Variant VARCHAR(100)
);
```
> এই কমান্ড দিয়ে `product` নামে একটি টেবিল তৈরি হবে।  

**Cmd (টেবিলগুলো দেখানোর জন্য):**  
```sql
SHOW TABLES;
```
> এই কমান্ড দিয়ে ডাটাবেসের সব টেবিল দেখা যাবে।  

---

## 🔍 Column Explanation

- **Name**  
  - টাইপ: `VARCHAR(100)`  
  - ব্যাখ্যা: প্রোডাক্টের নাম সংরক্ষণ করে।  

- **Description**  
  - টাইপ: `VARCHAR(100)`  
  - ব্যাখ্যা: প্রোডাক্টের বিস্তারিত বিবরণ।  

- **Price**  
  - টাইপ: `INT`  
  - ব্যাখ্যা: প্রোডাক্টের দাম।  

- **Variant**  
  - টাইপ: `VARCHAR(100)`  
  - ব্যাখ্যা: প্রোডাক্টের ভ্যারিয়েন্ট, যেমন রঙ বা সাইজ।  

---

## 💡 Tips
- সব SQL কমান্ড **`sql` কোড ব্লক**-এ রাখলে GitHub README-তে সুন্দর দেখাবে।  
- ডাটাবেস নাম ও টেবিল নাম ছোট হাতের অক্ষরে রাখলে কোনো সমস্যা হবে না।  
- প্রয়োজনে `ALTER TABLE` দিয়ে Column যোগ বা পরিবর্তন করা যেতে পারে।  

---

🎯 **Summary Steps**  
1. `SHOW databases` → ডাটাবেস দেখা  
2. `CREATE DATABASE` → নতুন ডাটাবেস তৈরি  
3. `USE` → ডাটাবেসে প্রবেশ  
4. `CREATE TABLE` → টেবিল তৈরি  
5. `SHOW TABLES` → টেবিলগুলো দেখো  

> এবার তুমি নিজের E-commerce Database তৈরি করতে প্রস্তুত! 🛒💻

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

---


# 📘 **Class 4 — INSERT, SELECT, ALTER TABLE**

## 🧩 **Topic:** `INSERT`, `SELECT`, `ALTER TABLE`

---

## 🔹 **সব কলাম SELECT করা**
```sql
SELECT * FROM TableName;
````

📖 **Example:**

```sql
SELECT * FROM students;
```

---

## 🔹 **নির্দিষ্ট কলাম SELECT করা**

```sql
SELECT column1, column2, ... FROM TableName;
```

📖 **Example:**

```sql
SELECT Name, Roll FROM students;
```

💻 **Terminal View:**

```
MariaDB [cstustudent]> SELECT Name, Roll FROM students;
+---------+--------+
|  Name   |  Roll  |
+---------+--------+
| Brisrty |  100   |
+---------+--------+
1 row in set (0.012 sec)
```

---

## 🔄 **টেবিলের নাম পরিবর্তন করা**

```sql
RENAME TABLE OldName TO NewName;
```

📖 **Example:**

```sql
RENAME TABLE students TO student_data;
```

💻 **Terminal View:**

```
MariaDB [cstustudent]> RENAME TABLE students TO student_data;
Query OK, 0 rows affected (0.015 sec)

MariaDB [cstustudent]> SHOW TABLES;
+----------------------+
| Tables_in_cstustudent |
+----------------------+
| student_data         |
+----------------------+
1 row in set (0.002 sec)
```

---

## ✏️ **ALTER TABLE — কলাম পরিবর্তন, যোগ বা বাদ দেওয়া**

### ➕ **নতুন কলাম যোগ করা**

```sql
ALTER TABLE student_data ADD COLUMN Address VARCHAR(100);
```

### 🧩 **কলামের নাম পরিবর্তন করা**

```sql
ALTER TABLE student_data CHANGE COLUMN Roll StudentRoll VARCHAR(10);
```

### ❌ **কলাম মুছে ফেলা**

```sql
ALTER TABLE student_data DROP COLUMN Address;
```

---

## ✅ **Summary**

এই ক্লাসে তুমি শিখেছো —

* 🧠 `SELECT` দিয়ে ডাটা দেখা
* 🎯 নির্দিষ্ট কলাম বাছাই করা
* 🔄 টেবিল `RENAME` করা
* 🛠️ `ALTER TABLE` দিয়ে column **add**, **rename** বা **delete** করা

---

## 💡 **Tip**

⚙️ Practice করার সময় সব কমান্ড **`;`** দিয়ে শেষ করবে।

🚫 ভুল বানান যেমন `FROLM` বা `databese` দিলে **syntax error** আসবে।

---


