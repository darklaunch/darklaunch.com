```php
function js_escape($str) {
	for ($i = 0, $l = strlen($str), $new_str = ''; $i < $l; $i++) {
		$new_str .= (ord(substr($str, $i, 1)) < 16 ? '\\x0' : '\\x') . dechex(ord(substr($str, $i, 1)));
	}
	return $new_str;
}
```

Example:
```php
$var = '"Convinced myself, I seek not to convince." -Edgar Allan Poe';
```
<script type="text/javascript">
function doSomething(foo) {
	alert(foo);
}
</script>
```html
<input value="Click me" onclick="doSomething('<?php echo js_escape($var); ?>');" type="button" />
<!--
<input value="Click me" onclick="doSomething('\x22\x43\x6f\x6e\x76\x69\x6e\x63\x65\x64\x20\x6d\x79\x73\x65\x6c\x66\x2c\x20\x49\x20\x73\x65\x65\x6b\x20\x6e\x6f\x74\x20\x74\x6f\x20\x63\x6f\x6e\x76\x69\x6e\x63\x65\x2e\x22\x20\x2d\x45\x64\x67\x61\x72\x20\x41\x6c\x6c\x61\x6e\x20\x50\x6f\x65');" type="button" />
-->
```

---

Posted Apr 7, 2010.

https://www.darklaunch.com/2010/04/07/php-encode-javascript-string-encode-double-quotes-single-quotes-onclick-parameter.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Jul 1, 2011
            <div>

Thank you very much dude!!! It showed me some way to my problem. Have a great day.

thanks,
Sreedhar

            </div>
        </div>
    </li>
</ol>
