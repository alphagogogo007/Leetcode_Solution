```sql

SELECT c1.id AS id, c1.movie AS movie, c1.description AS description, c1.rating AS rating
FROM cinema AS c1
WHERE c1.id%2=1 AND c1.description!="boring"
ORDER BY c1.rating DESC;
```
