To disable xdebug's colorized html output, use the following `ini_set()`.

```php
ini_set('xdebug.default_enable', false);
ini_set('html_errors', false);
```

This removes the html tags including the pre tag with a "xdebug-var-dump" class when using `var_dump()`:

```html
&lt;pre class='xdebug-var-dump' dir='ltr'&gt;
```