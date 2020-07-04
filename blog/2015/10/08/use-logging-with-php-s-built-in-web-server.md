Write to the php built-in web server's log.
```php
<?php
// index.php
error_log(json_encode($_GET), 4);
```
```sh
$ php -S 127.0.0.1:8000 index.php
```
```sh
$ curl -i "http://127.0.0.1:8000/?foo=bar"
HTTP/1.1 200 OK
Host: 127.0.0.1:8000
Connection: close
X-Powered-By: PHP/5.6.5
Content-type: text/html; charset=UTF-8
```

<img alt="" src="/img/uploads/2015-10/php-built-in-webserver-error-log.png" />