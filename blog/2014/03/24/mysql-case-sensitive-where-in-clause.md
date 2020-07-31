MySQL WHERE IN case sensitive select clause.

```sql
SELECT
    *
FROM
    `table`
WHERE
    CAST(`column` AS BINARY) NOT IN ('Foo', 'Bar', 'Baz');
```

---


Posted Mar 24, 2014.
https://www.darklaunch.com/2014/03/24/mysql-case-sensitive-where-in-clause.html