To find non-ascii characters using a SELECT query, run a query similar to the following:

<code name="sql">
SELECT
    *
FROM
    `mytable`
WHERE
    `column` REGEXP(CONCAT('[', char(128), '-', char(255), ']'))
</code>
