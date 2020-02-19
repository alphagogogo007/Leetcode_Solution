```sql
# Write your MySQL query statement below


SELECT p1.product_id AS product_id,  (SELECT p4.new_price
                                     FROM Products AS p4
                                     WHERE p4.product_id = p1.product_id AND p4.change_date = MAX(p1.change_date)) AS price
FROM Products AS p1
WHERE p1.change_date<="2019-08-16"
GROUP BY p1.product_id

UNION ALL

SELECT DISTINCT p2.product_id AS product_id, 10 AS price
FROM Products AS p2
WHERE p2.change_date>"2019-08-16" AND p2.product_id NOT IN (SELECT DISTINCT p3.product_id 
                                                            FROM Products AS p3
                                                            WHERE p3.change_date<="2019-08-16" );

```
