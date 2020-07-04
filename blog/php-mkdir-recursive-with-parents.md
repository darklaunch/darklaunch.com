Recursively create directories in PHP with mkdir().
```sh
$ mkdir --parents
```
```php
function mkdir_p($directory, $mode=0700) {
    $recursive = TRUE;
    return @mkdir($directory, $mode, $recursive);
}
```

Note the @ is to ignore any existing folder.