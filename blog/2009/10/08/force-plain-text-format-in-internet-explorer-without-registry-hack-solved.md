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

---

Posted Oct 8, 2009.

https://www.darklaunch.com/2009/10/08/force-plain-text-format-in-internet-explorer-without-registry-hack-solved.html

---

2 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Mar 9, 2012
            <div>
                <p>Thanks, just what I was looking for.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 29, 2012
            <div>
                <p>As used in wordpress:</p><p></p><p>/**</p><p> * Send a HTTP header to disable content type sniffing in browsers which support it.</p><p> *</p><p> * @link <a href="http://blogs.msdn.com/ie/archive/2008/07/02/ie8-security-part-v-comprehensive-protection.aspx">http://blogs.msdn.com/ie/archive/2008/07/02/ie8-security-part-v-comprehensive-protection.aspx</a></p><p> * @link <a href="http://src.chromium.org/viewvc/chrome?view=rev&amp;revision=6985">http://src.chromium.org/viewvc/chrome?view=rev&amp;revision=6985</a></p><p> *</p><p> * @since 3.0.0</p><p> * @return none</p><p> */</p><p>function send_nosniff_header() {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;@header( 'X-Content-Type-Options: nosniff' );</p><p>}</p><p></p><p><a href="http://core.svn.wordpress.org/trunk/wp-includes/functions.php">http://core.svn.wordpress.org/trunk/wp-includes/functions.php</a></p>
            </div>
        </div>
    </li>
</ol>
