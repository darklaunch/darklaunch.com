The proper way to make untrusted user input safe when printing data, is to use htmlspecialchars().

```php
<?php
$unsafe_username = $_GET['username'];
echo 'hello ' . htmlspecialchars($unsafe_username, ENT_QUOTES, 'UTF-8');
```

---


Posted Feb 5, 2009.
https://www.darklaunch.com/2009/02/05/the-proper-way-to-make-safe.html