📘 Class 4 — INSERT, SELECT, ALTER TABLE
🧩 Topic
INSERT, SELECT, ALTER TABLE

🔹 সব কলাম SELECT করা
SELECT * FROM TableName;
Example:

SELECT * FROM students;
🔹 নির্দিষ্ট কলাম SELECT করা
SELECT column1, column2, ... FROM TableName;
Example:

SELECT Name, Roll FROM students;
🖥️ Terminal View
MariaDB [cstustudent]> SELECT Name, Roll FROM students;
+---------+--------+
| Name    | Roll   |
+---------+--------+
| Brisrty | 100    |
+---------+--------+
1 row in set (0.012 sec)
🔄 টেবিলের নাম পরিবর্তন করা
RENAME TABLE OldName TO NewName;
Example:

RENAME TABLE students TO student_data;
🖥️ Terminal View
MariaDB [cstustudent]> RENAME TABLE students TO student_data;
Query OK, 0 rows affected (0.015 sec)

MariaDB [cstustudent]> SHOW TABLES;
+----------------------+
| Tables_in_cstustudent |
+----------------------+
| student_data          |
+----------------------+
1 row in set (0.002 sec)
✏️ ALTER TABLE — কলাম পরিবর্তন, যোগ বা বাদ দেওয়া
🔹 নতুন কলাম যোগ করা
ALTER TABLE student_data ADD COLUMN Address VARCHAR(100);
🔹 কলামের নাম পরিবর্তন করা
ALTER TABLE student_data CHANGE COLUMN Roll StudentRoll VARCHAR(10);
🔹 কলাম মুছে ফেলা
ALTER TABLE student_data DROP COLUMN Address;
✅ Summary
এই ক্লাসে শিখেছো:

SELECT দিয়ে ডাটা দেখা
নির্দিষ্ট কলাম বাছাই করা
টেবিল rename করা
ALTER TABLE দিয়ে column add, rename বা delete করা
💡 Tip:
Practice করার সময় সব কমান্ড ; দিয়ে শেষ করবে।
ভুল spelling যেমন FROLM বা databese দিলে syntax error আসবে।
