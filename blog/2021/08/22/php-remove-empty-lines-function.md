# PHP remove empty lines function

```php
function remove_empty_lines($string) {
    $lines = explode("\n", str_replace(array("\r\n", "\r"), "\n", $string));
    $lines = array_map('trim', $lines);
    $lines = array_filter($lines, function($value) {
        return $value !== '';
    });
    return implode("\n", $lines);
}
```

```php
$string =
    'This is a' . "\n" .
    "\r\n" .
    'bit of text' . "\r" .
    "\t" .
    '   with  ' . "\r" .
    ' a ' . "\r" .
    "\n" .
    'few' . "\r\n" .
    "\r\n" .
    "\r" .
    "\n" .
    'empty' . "\n" .
    '  ' . "\n" .
    "\t\t\t\r" .
    'lines';

var_dump(remove_empty_lines($string));
```

```
string(44) "This is a
bit of text
with
a
few
empty
lines"
```

---

Posted Aug 22, 2021.

https://www.darklaunch.com/2021/08/22/php-remove-empty-lines-function.html