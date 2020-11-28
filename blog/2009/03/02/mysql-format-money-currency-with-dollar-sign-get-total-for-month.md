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

---

Posted Mar 2, 2009.

https://www.darklaunch.com/2009/03/02/mysql-format-money-currency-with-dollar-sign-get-total-for-month.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Oct 19, 2012
            <div>
Thanks so much I've been trying format the output for hours
            </div>
        </div>
    </li>
</ol>
