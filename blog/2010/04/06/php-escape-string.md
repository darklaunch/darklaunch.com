```php
function escape($str) {
    return str_replace(
        array( '&',     '<',    '>',    '"',      '\''),
        array( '&amp;amp;', '&amp;lt;', '&amp;gt;', '&quot;', '&#039;'),
        $str
    );
}
```

NOTE: `&amp;apos;` is not used as it is not a valid HTML entity reference.

---

Posted Apr 6, 2010.
https://www.darklaunch.com/2010/04/06/php-escape-string