Display a loading animation using php.
```php
$spin_marks = array('⠏', '⠛', '⠹', '⠼', '⠶', '⠧');
$ticks = 0;
while (true) {
    $ticks += 1;
    echo ' loading... ' . $spin_marks[$ticks % count($spin_marks)] . "\r";
    usleep(100000);
}
```
Screenshot:
<img alt="" src="/img/uploads/2019-08/php-loading-animation.png" />