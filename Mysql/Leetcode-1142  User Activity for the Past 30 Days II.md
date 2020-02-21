```sql


SELECT IF(ROUND(AVG(tb1.counts) ,2) IS NULL,0, ROUND(AVG(tb1.counts) ,2) )    AS average_sessions_per_user
FROM (

    SELECT COUNT(DISTINCT a1.session_id) AS counts
    FROM Activity AS a1
    WHERE a1.activity_date BETWEEN "2019-06-28" AND "2019-07-27"
    GROUP BY a1.user_id) AS tb1;
```
