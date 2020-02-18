```sql
SELECT ROUND(100*SUM(IF(tb1.order_date=d2.customer_pref_delivery_date,1,0)       )/(COUNT(*)),2) AS immediate_percentage
FROM (

    SELECT d1.customer_id AS customer_id, MIN(order_date) AS order_date
    FROM Delivery AS d1
    GROUP BY d1.customer_id) as tb1
LEFT JOIN Delivery AS d2
ON tb1.customer_Id = d2.customer_Id AND tb1.order_date=d2.order_date;
```
