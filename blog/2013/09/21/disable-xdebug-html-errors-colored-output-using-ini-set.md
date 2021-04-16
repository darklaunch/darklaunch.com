To disable xdebug's colorized html output, use the following `ini_set()`.

```php
ini_set('xdebug.default_enable', false);
ini_set('html_errors', false);
```

This removes the html tags including the pre tag with a "xdebug-var-dump" class when using `var_dump()`:

```html
&lt;pre class='xdebug-var-dump' dir='ltr'&gt;
```

---

Posted Sep 21, 2013.

https://www.darklaunch.com/2013/09/21/disable-xdebug-html-errors-colored-output-using-ini-set.html

---

2 comments

<ol><li><div>

anonymous &ndash; Aug 23, 2017<div>

This is exactly what I needed! Thanks a ton!!

</div></div></li><li><div>

anonymous &ndash; Apr 16, 2021<div>

Thank you!!

</div></div></li></ol>