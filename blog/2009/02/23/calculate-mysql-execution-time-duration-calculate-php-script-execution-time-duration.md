```php
<?php
$stats = array();
function start(){
    global $stats;
    $stats['time_start'] = microtime(true);
}

function stop() {
    global $stats;
    $stats['time_end'] = microtime(true);
    $stats['time_total'] = $stats['time_end'] - $stats['time_start'];
    echo 'completed in ' . $stats['time_total'] . ' seconds' . "\n";
    exit;
}
?>
```
```php
<?php // example usage
start();

for ($i = 0; $i <= 1000; $i++) {
    // Do something
}

stop();
```

You may may interested in the <a href="http://darklaunch.com/2013/01/30/php-measure-execution-elapsed-time-for-functions-or-scripts">PHP Measure Execution &amp; Elapsed Time for Functions or Scripts</a>

---


Posted Feb 23, 2009.
https://www.darklaunch.com/2009/02/23/calculate-mysql-execution-time-duration-calculate-php-script-execution-time-duration.html