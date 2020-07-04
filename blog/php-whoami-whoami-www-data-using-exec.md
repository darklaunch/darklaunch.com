PHP scripts typically runs under the www-data user. Verify this using the following code:

```php
$command = 'whoami';
echo exec($command) . "\n";
```