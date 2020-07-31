To measure execution times or duration of a php function or script, use the following:

```php
function start($name) {
    global $stats;

    if (defined('DEBUG') && !DEBUG) {
        return;
    }

    $start = microtime(true);

    if (empty($stats)) {
        $stats['start'] = $start;
        $stats['stop'] = '';
        $stats['duration'] = '';
    }

    $stats[$name]['start'] = $start;
    $stats[$name]['stop'] = '';
    $stats[$name]['duration'] = '';
}

function stop($name='', $return=false, $precision=2) {
    global $stats;

    if (defined('DEBUG') && !DEBUG) {
        return;
    }

    $stop = microtime(true);

    if (!empty($name)) {
        $stats[$name]['stop'] = $stop;
        $stats[$name]['duration'] = round($stats[$name]['stop'] -
                                          $stats[$name]['start'], $precision);
    }
    else {
        $stats['stop'] = $stop;
        $stats['duration'] = round($stats['stop'] -
                                   $stats['start'], $precision);

        // only show duration
        unset($stats['start']);
        unset($stats['stop']);
        foreach ($stats as $key => $value) {
            if (isset($stats[$key]['start'])) {
                $stats[$key] = $stats[$key]['duration'];
            }
        }

        $summary = print_r($stats, true);
        $summary = trim($summary);
        $summary = preg_replace('/^Array\n/', '', $summary);

        if (!($return === false)) {
            return $summary;
        }
        else {
            echo $summary;
        }
    }
}
```

Example usage:
```php
function some_task() {
    sleep(2);
}

function another_task() {
    for ($i = 0; $i <= 100; $i++) {
        usleep(1000);
    }
}

function yet_another_task() {
    time_sleep_until(time() + 4);
}

// turn on debugging
define('DEBUG', true);

// task 1
start('some task');
some_task();
stop('some task');

// task 2
start('another task');
another_task();
stop('another task');

// task 3
start('yet another task');
yet_another_task();
stop('yet another task');

// summary
stop();
```

The above code will output something similar to this.
```
(
    [duration] => 5.16
    [some task] => 2
    [another task] => 0.12
    [yet another task] => 3.04
)
```

---

Posted Jan 30, 2013.

https://www.darklaunch.com/2013/01/30/php-measure-execution-elapsed-time-for-functions-or-scripts.html