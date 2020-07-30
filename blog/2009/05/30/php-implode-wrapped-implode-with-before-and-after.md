```php
function implode_wrapped($before, $after, $array, $glue = '') {
	return $before . implode($after . $glue . $before, $array) . $after;
}
```

---

Posted May 30, 2009.
https://www.darklaunch.com/2009/05/30/php-implode-wrapped-implode-with-before-and-after