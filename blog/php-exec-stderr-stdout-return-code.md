Run a command in php and get standard output (stdout), standard error (stderr), and the return code / return value.
```php
function pipe_exec($cmd, $input='') {
    $proc = proc_open($cmd, array(array('pipe', 'r'),
                                  array('pipe', 'w'),
                                  array('pipe', 'w')), $pipes);
    fwrite($pipes[0], $input);
    fclose($pipes[0]);

    $stdout = stream_get_contents($pipes[1]);
    fclose($pipes[1]);

    $stderr = stream_get_contents($pipes[2]);
    fclose($pipes[2]);

    $return_code = (int)proc_close($proc);

    return array($return_code, $stdout, $stderr);
}
```
```php
// Example usage.
list($return_code, $stdout, $stderr) = pipe_exec('ls');
```