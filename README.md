# bigdata9
Assignment No 9
Implement and execute HiveQL queries to perform data retrieval and manipulation.
1. Setting up Hive
Hive
2. Creating a Hive Table
CREATE TABLE employees (
emp_id INT,
emp_name STRING,
emp_salary DOUBLE,
emp_department STRING
) ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
STORED AS TEXTFILE;
3. Data Manipulation
a. Inserting Data into the Table:
INSERT INTO TABLE employees VALUES (1001, 'John Doe', 60000.00,'Engineering');
b. Updating Data:
INSERT OVERWRITE TABLE employees
SELECT emp_id, emp_name, CASE
WHEN emp_salary < 50000 THEN emp_salary * 1.1
ELSE emp_salary
END AS emp_salary,
emp_department
FROM employees;
c. Deleting Data:
INSERT OVERWRITE TABLE employees
SELECT * FROM employees WHERE emp_id != 1001;
4. Basic Data Retrieval Queries
a. Select all records:
SELECT * FROM employees;
b. Select specific columns:
SELECT emp_name, emp_salary FROM employees;
c. Select with a WHERE clause:
SELECT * FROM employees WHERE emp_salary > 50000;
