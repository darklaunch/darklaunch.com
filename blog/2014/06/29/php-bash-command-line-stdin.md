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