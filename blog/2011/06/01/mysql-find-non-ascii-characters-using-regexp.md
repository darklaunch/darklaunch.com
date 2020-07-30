To find non-ascii characters using a SELECT query, run a query similar to the following:

```sql
SELECT
    *
FROM
    `mytable`
WHERE
    `column` REGEXP(CONCAT('[', char(128), '-', char(255), ']'))
```

---

Posted Jun 1, 2011.
https://www.darklaunch.com/2011/06/01/mysql-find-non-ascii-characters-using-regexp