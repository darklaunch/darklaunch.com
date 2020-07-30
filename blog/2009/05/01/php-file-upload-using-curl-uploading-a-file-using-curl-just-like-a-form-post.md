Upload a file using PHP and cURL.

```php
<?php
$ch = curl_init();
curl_setopt($ch, CURLOPT_RETURNTRANSFER => true);  // return web page string
curl_setopt($ch, CURLOPT_HEADER => false);         // don't return headers
curl_setopt($ch, CURLOPT_FOLLOWLOCATION => false); // follow redirects
curl_setopt($ch, CURLOPT_USERAGENT => 'Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1)');
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'POST');
curl_setopt($ch, CURLOPT_URL, 'http://127.0.0.1/upload.php');
curl_setopt($ch, CURLOPT_HEADER, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, array( 'image' => '@' . getcwd() . '/image.jpg',));
echo curl_exec($ch);
```

NOTE: Avoid using `curl_setopt_array()`. Use `curl_setopt()` instead.

---

Posted May 1, 2009.
https://www.darklaunch.com/2009/05/01/php-file-upload-using-curl-uploading-a-file-using-curl-just-like-a-form-post