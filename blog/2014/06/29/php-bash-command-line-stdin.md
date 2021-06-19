# PHP bash command line stdin

Read stdin using php on the command line. 

```sh
listdir ()
{
    ls | sort | php -r '
        while ($line = fgets(STDIN)) {
            $filename = rtrim($line);
            $modified = date(DATE_W3C, filemtime($filename));
            echo "$modified $filename\n";
        }
    '
}
```

<img alt="" src="/img/uploads/2014-06/bash-stdin-php-command-line.png" />

---

Posted Jun 29, 2014.

https://www.darklaunch.com/2014/06/29/php-bash-command-line-stdin.html