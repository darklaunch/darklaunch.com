```php
<?php
# server.php
$content_length_bytes = 1e6; // 1 megabyte.
$content_length_bytes *= 3;

// Send binary file header.
header('Content-Type: application/octet-stream');
header('Content-Length: ' . $content_length_bytes);
header('Content-Disposition: attachment; filename="somefile.bin"');

$bytes = 1000;
$length = $content_length_bytes / $bytes;
$str = str_repeat('.', $bytes);
$micro_seconds = 20000;

for ($i = 0; $i < $length; $i++) {
    echo $str;

    // Slow the download.
    usleep($micro_seconds);
}
```

Start the server.
```bash
$ php -S 127.0.0.1:8080 server.php
```

Show the download progress including Total, Received, Xferd, Average Dload, Speed Upload, Time Total, Time Spent, Time Left, Current Speed:
```
curl -i http://127.0.0.1:8080/server.php -o /dev/null
```