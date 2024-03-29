# Force Plain Text Format in Internet Explorer WITHOUT Registry Hack [SOLVED]

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

Example: The following will render as plain text in Internet Explorer:

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

UPDATE: Sending the `X-Content-Type-Options` response header will stop MIME-sniffing.

```php
header('X-Content-Type-Options: nosniff');
```

---

Posted Oct 8, 2009.

https://www.darklaunch.com/2009/10/08/force-plain-text-format-in-internet-explorer-without-registry-hack-solved.html

---

2 comments

<ol><li><div>

anonymous &ndash; Mar 9, 2012<div>

Thanks, just what I was looking for.

</div></div></li><li><div>

anonymous &ndash; Nov 29, 2012<div>

As used in wordpress:

```
/**
 * Send a HTTP header to disable content type sniffing in browsers which support it.
 *
 * @link http://blogs.msdn.com/ie/archive/2008/07/02/ie8-security-part-v-comprehensive-protection.aspx
 * @link http://src.chromium.org/viewvc/chrome?view=rev&revision=6985
 *
 * @since 3.0.0
 * @return none
 */
function send_nosniff_header() {
    @header( 'X-Content-Type-Options: nosniff' );
}
```

https://core.svn.wordpress.org/trunk/wp-includes/functions.php

</div></div></li></ol>