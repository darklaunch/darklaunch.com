# PHP Recursively list directories and files; recursive listing scan and traversal

PHP List directory files and folders.

```php
error_reporting(E_ALL | E_STRICT);
ini_set('display_errors', 1);

header('Content-Type: text/plain');

$dir = dirname(__FILE__);

foreach (new RecursiveIteratorIterator(new RecursiveDirectoryIterator($dir)) as $item) {
    if ($item->isFile() || $item->isDir()) {
        echo $item . PHP_EOL;
    }
}
```

---

Posted Jun 4, 2010.

https://www.darklaunch.com/2010/06/04/php-recursively-list-directories-and-files-recursive-listing-scan-and-traversal.html