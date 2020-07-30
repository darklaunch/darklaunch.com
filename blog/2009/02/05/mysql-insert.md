To safely save data to a database and safely print data stored in a database

```php
// Safely save data to a database
$query = sprintf('
    INSERT INTO `mytable`(
        `foo`,
        `bar`
    )
    VALUES(
        "%s",
        "%s"
    )',
    mysql_real_escape_string($foo),
    mysql_real_escape_string($bar)
);
```

```php
// Safely print data stored in a database
echo htmlspecialchars($foo, ENT_QUOTES, 'UTF-8');
echo htmlspecialchars($bar, ENT_QUOTES, 'UTF-8');
```

---

Posted Feb 5, 2009.
https://www.darklaunch.com/2009/02/05/mysql-insert