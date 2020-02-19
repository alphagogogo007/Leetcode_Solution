```sql
# Write your MySQL query statement below


SELECT u1.user_id AS buyer_id, u1.join_date AS join_date, IF(tb1.counts IS NULL,0, tb1.counts) AS orders_in_2019
FROM Users AS u1
LEFT JOIN 
    (SELECT o1.buyer_id AS buyer_id, COUNT(*) AS counts
    FROM Orders AS o1
    WHERE o1.order_date BETWEEN "2019-01-01" AND "2019-12-31"
    GROUP BY o1.buyer_id) AS tb1
ON tb1.buyer_id=u1.user_id;






```
