PHP Curl Class: an object-oriented wrapper for curl functions. Supports REST request methods: GET, POST, PUT, PATCH, and DELETE. Examples:

```php
require __DIR__ . '/vendor/autoload.php';

$curl = new Curl();
$curl->setUserAgent('SomeBot (+https://www.example.com/bot.html)');
$curl->get('https://www.example.com/');

if ($curl->error) {
    echo 'Error: ' . $curl->errorCode . ': ' . $curl->errorMessage;
} else {
    echo $curl->response;
}

var_dump($curl->requestHeaders);
var_dump($curl->responseHeaders);
```

More examples and download at https://github.com/php-curl-class/php-curl-class

---

Posted Aug 22, 2013.
https://www.darklaunch.com/2013/08/22/php-curl-class