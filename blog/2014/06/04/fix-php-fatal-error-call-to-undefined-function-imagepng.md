Fix "PHP Fatal error:  Call to undefined function imagepng()" by installing the gd extension.

```bash
sudo apt-get install php5-gd
```

```php
<?php
var_dump(extension_loaded('gd'));
```

---

Posted Jun 4, 2014.
https://www.darklaunch.com/2014/06/04/fix-php-fatal-error-call-to-undefined-function-imagepng