To calculate the difference between two timestamps in seconds or hours use the following:
```sql
SELECT (
    UNIX_TIMESTAMP("2009-08-17 10:00") - 
    UNIX_TIMESTAMP("2009-08-17 09:00")
) AS seconds
>>> 3600
```
```sql
SELECT (
    (UNIX_TIMESTAMP("2009-08-17 10:00") -
     UNIX_TIMESTAMP("2009-08-17 09:00")) / 3600
) AS hours
>>> 1.0000
```