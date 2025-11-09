# dbms01
Design and Develop SQL DDL statements on Schema given. 
Problem Statement: Design and Develop SQL DDL statements on Schema given.
Schema:
employee_master (emp_id,first name,middle,last name,department,manager id.)
branch_master (branch id ,branch name)
1. Insert records in branch_master
2. Insert records in employee_master.
3. Create index on emp_name column of employee_master.
4. Create a view containing employee details


✅ Step 1: Create Tables
sql
CREATE TABLE branch_master (
  branch_id   INT PRIMARY KEY,
  branch_name VARCHAR(100)
);

CREATE TABLE employee_master (
  emp_id      INT PRIMARY KEY,
  first_name  VARCHAR(100),
  middle_name VARCHAR(100),
  last_name   VARCHAR(100),
  department  VARCHAR(100),
  manager_id  INT
);

✅ Step 2: Insert Records
sql
-- Insert into branch_master
INSERT INTO branch_master VALUES (1, 'Pune');
INSERT INTO branch_master VALUES (2, 'Mumbai');

-- Insert into employee_master
INSERT INTO employee_master 
VALUES (101, 'Rahul', 'K.', 'Sharma', 'SALES', 201);
INSERT INTO employee_master 
VALUES (102, 'Sneha', 'R.', 'Patil', 'HR', 202);







✅ Step 3: Create Index
👉 Suppose exam asks “create index on emp_name” — but we don’t have a single emp_name column. We can create index on first_name (simplest):
Sql

CREATE INDEX idx_emp_fname
ON employee_master(first_name);


✅ Step 4: Create View
sql
CREATE VIEW emp_view AS
SELECT emp_id,
       first_name,
       middle_name,
       last_name,
       department,
       manager_id
FROM employee_master;

