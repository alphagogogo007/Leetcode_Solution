```sql
SELECT e1.business_id AS business_id

FROM Events AS e1
LEFT JOIN     
    (SELECT e2.event_type AS event_type, AVG(e2.occurences) AS occurences
      FROM Events AS e2
      GROUP BY e2.event_type) AS tb1
    
ON tb1.event_type = e1.event_type
WHERE e1.occurences> tb1.occurences
                     

GROUP BY e1.business_id
HAVING COUNT(DISTINCT e1.event_type)>1;


```
