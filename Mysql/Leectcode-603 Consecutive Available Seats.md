```sql

SELECT seat_id

FROM (

SELECT DISTINCT c1.seat_id AS seat_id
FROM cinema AS c1
WHERE c1.free = 1 AND (SELECT c2.free
                      FROM cinema AS c2
                      WHERE c2.seat_id = c1.seat_id+1) = 1

UNION

SELECT DISTINCT c3.seat_id AS seat_id
FROM cinema AS c3
WHERE c3.free = 1 AND (SELECT c4.free
                      FROM cinema AS c4
                      WHERE c4.seat_id = c3.seat_id-1) = 1
                      
                      ) AS tb1
ORDER BY seat_id ASC;
```
