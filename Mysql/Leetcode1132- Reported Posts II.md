```sql
# Write your MySQL query statement below


SELECT ROUND(AVG(tb2.ave_val)*100,2) AS average_daily_percent
FROM(
    SELECT  SUM(IF(tb1.remove_date IS NULL,0,1))/(COUNT(*)) AS ave_val
    FROM(
    
        SELECT a1.action_date AS action_date,MIN(r1.remove_date) AS remove_date
        FROM Actions AS a1


        LEFT JOIN Removals AS r1
        ON a1.post_id = r1.post_id
        WHERE a1.extra = "spam"
        GROUP BY a1.action_date,a1.post_id) AS tb1
    GROUP BY tb1.action_date ) AS tb2
```   

