📘 Database Learning Journey

💡 Complete Notes from Class 1 to Class 3 (DBMS, SQL, MariaDB Practice)

🏫 Class 1 — Introduction to DBMS
⚙️ 1️⃣ Termux Setup for Database

📲 Step-by-Step Commands:

pkg install mariadb
mysqld_safe &
mysql -u root


✅ এখন তুমি ডাটাবেস তৈরি ও SQL কমান্ড ব্যবহার করতে প্রস্তুত!

📚 2️⃣ What is DBMS?

DBMS (Database Management System) হলো এমন সফটওয়্যার যা ডাটাকে store, manage, এবং organize করে।

🔑 Key Points:

ডাটা সংরক্ষণ করে efficient ও secure ভাবে

SQL ব্যবহার করে ডাটা query ও manipulate করা যায়

উদাহরণ: MySQL, MariaDB, PostgreSQL, Oracle DB

🧠 3️⃣ Why DBMS?

✅ ডাটার consistency ও integrity বজায় রাখে
✅ ডাটার security নিশ্চিত করে
✅ সহজে search, update, delete করা যায়

🏫 Class 2 — Step-by-Step Database Tutorial
🧩 1️⃣ Database তৈরি করা
SHOW DATABASES;
CREATE DATABASE mydb;

🧭 2️⃣ Database-এ প্রবেশ করা
USE mydb;

🏗️ 3️⃣ টেবিল তৈরি করা
CREATE TABLE product(
    Name VARCHAR(100),
    Description VARCHAR(100),
    Price INT,
    Variant VARCHAR(100)
);

🎯 Summary
Step	Command	কাজ
1️⃣	SHOW DATABASES	ডাটাবেস দেখা
2️⃣	CREATE DATABASE	নতুন ডাটাবেস তৈরি
3️⃣	USE	ডাটাবেসে প্রবেশ
4️⃣	CREATE TABLE	টেবিল তৈরি
💻 Class 3 — Data Types & Binary Numbers

📘 Topics Covered:

SQL Data Types

Binary Numbers

Table Creation & Data Insertion

🧩 Make Student Database
✅ Step 1: Create Database
CREATE DATABASE cstustudent;
USE cstustudent;

✅ Step 2: Create Table
CREATE TABLE students(
    Name VARCHAR(100),
    Roll VARCHAR(8),
    Phone VARCHAR(15),
    Email VARCHAR(100),
    Gender ENUM('Male','Female')
);

💻 Terminal View
MariaDB [(none)]> CREATE database cstustudent;
Query OK, 1 row affected (0.011 sec)

MariaDB [cstustudent]> CREATE TABLE students(
    -> Name VARCHAR(100),
    -> Roll VARCHAR(8),
    -> Phone VARCHAR(15),
    -> Email VARCHAR(100),
    -> Gender ENUM('Male', 'Female')
    -> );
Query OK, 0 rows affected (0.090 sec)

✍️ Insert Data (Sanjida & Bristy Version)
INSERT INTO students(Name, Roll, Phone, Email, Gender)
VALUES 
("Sanjida", "10", "01300000001", "sanjida@gmail.com", "Female"),
("Bristy", "11", "01700000002", "bristy@gmail.com", "Female");

👁️ Show Data
SELECT * FROM students;

Name	Roll	Phone	Email	Gender
Sanjida	10	01300000001	sanjida@gmail.com
	Female
Bristy	11	01700000002	bristy@gmail.com
	Female
🧠 Task 1 — CEO Table Practice (Updated)
INSERT INTO ceo (id, name, email, phone)
VALUES
(1, "Sanjida", "sanjida@gmail.com", "01300000001"),
(2, "Bristy", "bristy@gmail.com", "01700000002"),
(3, "Sweety", "sweety@gmail.com", "01200000003"),
(4, "Misty", "misty@gmail.com", "01300000004");

SELECT * FROM ceo;

id	name	email	phone
1	Sanjida	sanjida@gmail.com
	01300000001
2	Bristy	bristy@gmail.com
	01700000002
3	Sweety	sweety@gmail.com
	01200000003
4	Misty	misty@gmail.com
	01300000004
🖥️ Full MariaDB Terminal Practice
Microsoft Windows [Version 10.0.22631.6060]
(c) Microsoft Corporation. All rights reserved.

C:\Users\USER>mysql -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.4.32-MariaDB mariadb.org binary distribution

MariaDB [(none)]> SHOW DATABASE;
ERROR 1064 (42000): You have an error in your SQL syntax;
MariaDB [(none)]> SHOW DATABASES;
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

MariaDB [(none)]> CREATE DATABASE sbgem;
Query OK, 1 row affected (0.002 sec)

MariaDB [(none)]> USE sbgem;
Database changed

MariaDB [sbgem]> CREATE TABLE students(
    -> name VARCHAR(100),
    -> phone VARCHAR(15),
    -> email VARCHAR(100),
    -> roll VARCHAR(10),
    -> class ENUM('1','2','3','4','5','6','7','8','9'));
Query OK, 0 rows affected (0.043 sec)

MariaDB [sbgem]> INSERT INTO students(name,phone,email)
    -> VALUES
    -> ("Sanjida","013#######","sanjida@gmail.com"),
    -> ("Bristy","017#######","bristy@gmail.com"),
    -> ("Sweety","012#######","sweety@gmail.com"),
    -> ("Misty","013#######","misty@gmail.com");
Query OK, 4 rows affected (0.091 sec)

MariaDB [sbgem]> SELECT * FROM students;
+---------+------------+-------------------+------+-------+
| name    | phone      | email             | roll | class |
+---------+------------+-------------------+------+-------+
| Sanjida | 013####### | sanjida@gmail.com | NULL | NULL  |
| Bristy  | 017####### | bristy@gmail.com  | NULL | NULL  |
| Sweety  | 012####### | sweety@gmail.com  | NULL | NULL  |
| Misty   | 013####### | misty@gmail.com   | NULL | NULL  |
+---------+------------+-------------------+------+-------+
4 rows in set (0.001 sec)

✅ Summary

Data Types ও Binary Concept শিখেছি

Database ও Table তৈরি করেছি

Sanjida ও Bristy–র তথ্য দিয়ে Data Insert করেছি

Terminal Output পুরোপুরি প্র্যাকটিক্যাল দেখা হয়েছে

✨ Prepared by: Sanjida & Bristy
📅 Course: Database Management System
