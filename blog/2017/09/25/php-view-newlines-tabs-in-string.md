View a string's newlines and tabs in PHP.

```php
function raw($str) {
    $str = str_replace(array("\t", "\r\n", "\r", "\n"),
                       array('\t', '\r\n', '\r', '\n'), $str);
    return $str;
}
```

---

Posted Sep 25, 2017.
https://www.darklaunch.com/2017/09/25/php-view-newlines-tabs-in-string