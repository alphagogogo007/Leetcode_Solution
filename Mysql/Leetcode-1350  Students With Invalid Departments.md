# Write your MySQL query statement below

SELECT s1.id AS id, s1.name AS name
FROM Students AS s1
WHERE s1.department_id NOT IN (SELECT d1.id
                              FROM Departments AS d1
                              );
