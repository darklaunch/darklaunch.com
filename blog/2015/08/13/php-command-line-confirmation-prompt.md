Get user confirmation before continuing in PHP script.
```php
<?php
echo 'Continue? [y/n] ';

if (!in_array(trim(fgets(STDIN)), array('y', 'Y'))) {
    echo 'Stopped' . "\n";
    exit;
}

echo 'Continuing' . "\n";
```

Examples
```sh
$ php confirm.php 
Continue? [y/n] n
Stopped
```
```sh
$ php confirm.php 
Continue? [y/n] y
Continuing
```

---

Posted Aug 13, 2015.

https://www.darklaunch.com/2015/08/13/php-command-line-confirmation-prompt.html