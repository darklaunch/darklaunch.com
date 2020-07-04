Fix "PHP Fatal error:  Call to undefined function imagepng()" by installing the gd extension.

```sudo apt-get install php5-gd```

```php
<?php
var_dump(extension_loaded('gd'));
```