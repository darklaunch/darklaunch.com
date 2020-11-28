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

---

Posted Jun 5, 2013.

https://www.darklaunch.com/2013/06/05/php-mkdir-recursive-with-parents.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Jun 10, 2013
            <div>
what about:
`mkdir($_SERVER['DOCUMENT_ROOT'] . _PATH . '/' . $directory, 777, true);`
            </div>
        </div>
    </li>
</ol>
