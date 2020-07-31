To fix Compatibility View in Internet Explorer, force IE to use the latest rendering engine.

```php
<?php
// Avoid Compatibility View and force IE to use the latest rendering engine.
// Send via an HTTP header as the meta tag doesn't override the "Display
// intranet sites in Compatibility View" setting.
header('X-UA-Compatible: IE=Edge');
```

---


Posted Jun 17, 2013.
https://www.darklaunch.com/2013/06/17/how-to-fix-compatibility-view-in-ie.html