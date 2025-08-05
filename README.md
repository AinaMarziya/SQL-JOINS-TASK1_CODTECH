# 📌 Internship Task2 – SQL JOINs

*Intern Name:* Aina Marziya  
*Internship Organization:* CODTECH  
*Task:* 1
*Topic:* SQL JOIN Operations  
*Tool Used:* MySQL 8.0 Command Line Client

## 🛠 Tables Created

### Employees Table:
```sql
CREATE TABLE Employees (
    emp_id INT,
    emp_name VARCHAR(100),
    dept_id INT
);

Departments Table:

CREATE TABLE Departments (
    dept_id INT,
    dept_name VARCHAR(100)
);



📥 Sample Data Inserted

INSERT INTO Employees (emp_id, emp_name, dept_id) VALUES
(1, 'Alice', 10),
(2, 'Bob', 20),
(3, 'Charlie', 30),
(4, 'David', NULL),
(5, 'Eva', 50);

INSERT INTO Departments (dept_id, dept_name) VALUES
(10, 'HR'),
(20, 'Engineering'),
(30, 'Marketing'),
(40, 'Finance');


🔗 SQL JOINs Performed

🔸 INNER JOIN
SELECT e.emp_name, d.dept_name
FROM Employees e
INNER JOIN Departments d ON e.dept_id = d.dept_id;

Output:
+----------+-------------+
| emp_name | dept_name   |
+----------+-------------+
| Alice    | HR          |
| Bob      | Engineering |
| Charlie  | Marketing   |
+----------+-------------+


🔸 LEFT JOIN
SELECT e.emp_name, d.dept_name
FROM Employees e
LEFT JOIN Departments d ON e.dept_id = d.dept_id;

Output:
+----------+-------------+
| emp_name | dept_name   |
+----------+-------------+
| Alice    | HR          |
| Bob      | Engineering |
| Charlie  | Marketing   |
| David    | NULL        |
| Eva      | NULL        |
+----------+-------------+


🔸 RIGHT JOIN
SELECT e.emp_name, d.dept_name
FROM Employees e
RIGHT JOIN Departments d ON e.dept_id = d.dept_id;

Output:
+----------+-------------+
| emp_name | dept_name   |
+----------+-------------+
| Alice    | HR          |
| Bob      | Engineering |
| Charlie  | Marketing   |
| NULL     | Finance     |
+----------+-------------+


🔸 FULL JOIN (Using UNION in MySQL)
SELECT e.emp_name, d.dept_name
FROM Employees e
LEFT JOIN Departments d ON e.dept_id = d.dept_id
UNION
SELECT e.emp_name, d.dept_name
FROM Employees e
RIGHT JOIN Departments d ON e.dept_id = d.dept_id;

Output:
+----------+-------------+
| emp_name | dept_name   |
+----------+-------------+
| Alice    | HR          |
| Bob      | Engineering |
| Charlie  | Marketing   |
| David    | NULL        |
| Eva      | NULL        |
| NULL     | Finance     |
+----------+-------------+
 
