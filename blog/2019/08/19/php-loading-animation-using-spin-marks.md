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

---


Posted Aug 19, 2019.
https://www.darklaunch.com/2019/08/19/php-loading-animation-using-spin-marks.html