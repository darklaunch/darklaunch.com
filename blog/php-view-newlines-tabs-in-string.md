View a string's newlines and tabs in PHP.

```php
function raw($str) {
    $str = str_replace(array("\t", "\r\n", "\r", "\n"),
                       array('\t', '\r\n', '\r', '\n'), $str);
    return $str;
}
```