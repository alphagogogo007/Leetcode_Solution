```sql
# Write your MySQL query statement below



SELECT d1.dept_name AS dept_name, IF(tb1.num IS NULL,0,tb1.num) AS student_number
FROM department AS d1
LEFT JOIN

(
SELECT s1.dept_id AS dept_id, COUNT(*) AS num
FROM student AS s1
GROUP BY s1.dept_id) AS tb1

ON d1.dept_id = tb1.dept_id
ORDER BY tb1.num DESC, d1.dept_name ASC;
```
