# PHP Non-blocking fopen, file_get_contents using stream_set_blocking

Here is a php script that calls a urls without blocking and returns immediately.

```php
function call_url($url) {
    // Call the url and return immediately with the length of the data read.
    // Useful for firing off scripts by calling a url.

    $fp = fopen($url, 'r');
    stream_set_blocking($fp, 0); // 0 => non-blocking mode
    $data = fread($fp, 8192); // 1024 * 8 = 8192
    fclose($fp);

    // Return the amount of data read
    return strlen($data);
}
```

---

Posted Mar 23, 2013.

https://www.darklaunch.com/2013/03/23/php-non-blocking-fopen-file-get-contents-using-stream-set-blocking.html

---

1 comment

<ol><li><div>

anonymous &ndash; Sep 12, 2017<div>

Thank you!

</div></div></li></ol>