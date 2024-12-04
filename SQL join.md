![image](https://github.com/user-attachments/assets/2b8f9650-cb44-4df3-9f8b-f68cf95ce710)

1. INNER JOIN
Definition: Returns rows where there is a match in both tables.
Behavior: Excludes rows that do not have a match in both tables.
Use Case: When you need only the intersecting data from both tables.
Query Example:

SELECT employees.name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.id;
Result: Only rows where department_id in employees matches id in departments.

2. LEFT JOIN (LEFT OUTER JOIN)
Definition: Returns all rows from the left table and matching rows from the right table. Rows from the left table with no match will have NULL for columns from the right table.
Behavior: Prioritizes the left table, ensuring all its rows are included.
Use Case: When you want to include all data from the left table, even if there is no match in the right table.
Query Example:

SELECT employees.name, departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.id;
Result: All employees will be listed. If an employee does not belong to a department, department_name will show NULL.

3. RIGHT JOIN (RIGHT OUTER JOIN)
Definition: Returns all rows from the right table and matching rows from the left table. Rows from the right table with no match will have NULL for columns from the left table.
Behavior: Prioritizes the right table, ensuring all its rows are included.
Use Case: When you want to include all data from the right table, even if there is no match in the left table.
Query Example:

SELECT employees.name, departments.department_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.id;
Result: All departments will be listed. If a department has no employees, name will show NULL.

4. FULL OUTER JOIN
Definition: Combines the results of both LEFT and RIGHT JOINs. Returns all rows from both tables, with NULL in columns where no match exists.
Behavior: Ensures no data is excluded, even if it has no match in the other table.
Use Case: When you need a complete view of all data from both tables.
Query Example:

SELECT employees.name, departments.department_name
FROM employees
FULL OUTER JOIN departments
ON employees.department_id = departments.id;
Result: All employees and all departments will be included. Rows without matches will have NULL in the unmatched columns.

