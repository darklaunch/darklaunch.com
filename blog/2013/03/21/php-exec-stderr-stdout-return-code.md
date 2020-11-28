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

---

Posted Mar 21, 2013.

https://www.darklaunch.com/2013/03/21/php-exec-stderr-stdout-return-code.html

---

5 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Aug 16, 2013
            <div>
Thanks. Is there any way to both read stderr and allow it out as if it hasn't been interfered with?
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 16, 2013
            <div>
`tee' might be what you're looking for.
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 16, 2013
            <div>
"tee - read from standard input and write to standard output and files"
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 8, 2014
            <div>
Hi, thanks for this useful piece of code. Could you clarify under which license you're providing it (I'd suggest public domain, CC0, or BSD-2 clause), and if you are the original writer ? Thank you !
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 8, 2014
            <div>
@license, public domain.
            </div>
        </div>
    </li>
</ol>
