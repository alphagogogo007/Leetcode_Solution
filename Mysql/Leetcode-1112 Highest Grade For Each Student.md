```sql
# Write your MySQL query statement below

SELECT e1.student_id AS student_id, 
    (SELECT MIN(course_id)
     FROM Enrollments AS e2
     WHERE e2.student_Id = e1.student_id AND e2.grade = MAX(e1.grade)) AS course_id,
     
     MAX(e1.grade) AS grade
FROM Enrollments AS e1
GROUP BY e1.student_id
ORDER BY e1.student_id ASC;
```
