```sql

SELECT e1.employee_id  AS employee_id
FROM Employees AS e1
LEFT JOIN Employees AS e2
ON e1.manager_id = e2.employee_id
LEFT JOIN Employees AS e3
ON e2.manager_id = e3.employee_id
LEFT JOIN Employees AS e4
ON e3.manager_id = e4.employee_id
WHERE e4.manager_id = 1 AND e1.employee_id!=1;
```
