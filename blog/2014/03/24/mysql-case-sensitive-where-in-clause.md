MySQL WHERE IN case sensitive select clause.

```sql
SELECT
    *
FROM
    `table`
WHERE
    CAST(`column` AS BINARY) NOT IN ('Foo', 'Bar', 'Baz');
```