# Bash POST chunked data using nc (netcat)

Create temporary server to display POST data.
```php
<?php
// server.php
var_dump($_POST);
```

Run server.
```bash
$ php -S 127.0.0.1:8000 server.php
```

POST to server using the nc command.
```bash
$ echo -ne "POST / HTTP/1.0\r\nContent-Type: application/x-www-form-urlencoded\r\nTransfer-Encoding: chunked\r\n\r\n4\r\nfoo=\r\n3\r\nbar\r\n0\r\n\r\n" | nc 127.0.0.1 8000
HTTP/1.0 200 OK
Connection: close
Content-type: text/html; charset=UTF-8

array(1) {
  ["foo"]=>
  string(3) "bar"
}
```

---

Posted Sep 19, 2016.

https://www.darklaunch.com/2016/09/19/bash-post-chunked-data-using-nc-netcat.html