Internet Explorer uses MIME sniffing to parse pages and will erroneously render the following page as html:
```php
header('Content-Type: text/plain');
echo '<body>';
echo '<span style="font-size:600%;">';
echo 'normal <strong>bold</strong>';
echo '</span>';
```
To force Internet Explorer to render the page as plain text, add the following before any text is output:
```php
header('Content-Type: text/plain');
echo '                                                  ';
echo '                                                  ';
echo '                                                  ';
echo '                                                  ';
echo '                                                  ';
echo "\n";
```
Example:
The following will render as plain text in Internet Explorer:
```php
header('Content-Type: text/plain');
echo '                                                  ';
echo '                                                  ';
echo '                                                  ';
echo '                                                  ';
echo '                                                  ';
echo "\n";
echo '<body>';
echo '<span style="font-size:600%;">';
echo 'normal <strong>bold</strong>';
echo '</span>';
```
Or simply:
```php
header('Content-Type: text/plain');
echo str_repeat(' ', 250) . "\n";
echo '<body>';
echo '<span style="font-size:600%;">';
echo 'normal <strong>bold</strong>';
echo '</span>';
```
UPDATE: Sending the X-Content-Type-Options response header will stop MIME-sniffing.
```php
header('X-Content-Type-Options: nosniff');
```