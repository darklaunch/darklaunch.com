Format the mysql select with a dollar sign and two decimal places.
```sql
SELECT
    CONCAT('$',FORMAT(SUM(`invoice_total`),2)) AS month_total
FROM
    `invoices`
WHERE
    `invoices`.`timestamp` > DATE_SUB('2009-02-01', INTERVAL 1 DAY) AND
    `invoices`.`timestamp` < DATE_ADD(LAST_DAY('2009-02-01'), INTERVAL 1 DAY)
LIMIT
    1
```