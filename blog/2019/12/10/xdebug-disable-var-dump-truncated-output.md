# Xdebug disable var_dump truncated output

Disable truncated html output when using var_dump by configuring xdebug using ini_set:

```php
ini_set('xdebug.var_display_max_depth', '-1');
ini_set('xdebug.var_display_max_children', '-1');
ini_set('xdebug.var_display_max_data', '-1');
```

---

Posted Dec 10, 2019.

https://www.darklaunch.com/2019/12/10/xdebug-disable-var-dump-truncated-output.html