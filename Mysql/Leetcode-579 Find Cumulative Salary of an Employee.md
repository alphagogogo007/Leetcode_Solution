```sql
# Write your MySQL query statement below






SELECT e1.Id AS Id,e1.Month AS Month, SUM(e2.Salary) AS Salary
FROM Employee AS e1
LEFT JOIN Employee AS e2

ON e1.Id = e2.Id AND e1.Month>=e2.Month AND e1.Month<(e2.Month+3)



WHERE e1.Month NOT IN (SELECT MAX(e3.Month)
                    FROM Employee AS e3
                    WHERE e3.Id = e1.Id
                  GROUP BY e3.Id) 


GROUP BY e1.ID, e1.Month


ORDER BY e1.Id ASC, e1.Month DESC;

;
                  

```
