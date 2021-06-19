# PHP WhoAmI; whoami www-data using exec()

PHP scripts typically runs under the `www-data` user. Verify this using the following code:

```php
$command = 'whoami';
echo exec($command) . "\n";
```

---

Posted Sep 12, 2010.

https://www.darklaunch.com/2010/09/12/php-whoami-whoami-www-data-using-exec.html