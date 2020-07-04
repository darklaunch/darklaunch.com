```php
function implode_wrapped($before, $after, $array, $glue = '') {
	return $before . implode($after . $glue . $before, $array) . $after;
}
```