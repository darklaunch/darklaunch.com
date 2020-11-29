```php
function implode_wrapped($before, $after, $array, $glue = '') {
	return $before . implode($after . $glue . $before, $array) . $after;
}
```

---

Posted May 30, 2009.

https://www.darklaunch.com/2009/05/30/php-implode-wrapped-implode-with-before-and-after.html

---

2 comments

<ol><li><div>

anonymous &ndash; Jan 27, 2013<div>

Clever!

</div></div></li><li><div>

anonymous &ndash; Apr 11, 2020<div>

You are the man!!!

</div></div></li></ol>