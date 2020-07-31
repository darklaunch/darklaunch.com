Explode a string with no empty elements. Similar to C# Split String: StringSplitOptions.RemoveEmptyEntries.

```php
function eexplode($separator, $string) {
	$array = explode($separator, $string);
	foreach ($array as $key => $val) {
		if (empty($val)) {
			unset($array[$key]);
		}
	}
	return $array;
}
```

NOTE: `preg_split()` using the `PREG_SPLIT_NO_EMPTY` flag is another option.

---

Posted Apr 6, 2010.

https://www.darklaunch.com/2010/04/06/php-empty-explode.html