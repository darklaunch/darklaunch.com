To determine if SSL is used, the `is_ssl()` function will return True
if the page is using SSL (HTTPS or on Port 443), False if not
used.

```php
// From wordpress/wp-includes/load.php
// Previously wordpress/wp-includes/functions.php
function is_ssl() {
    if ( isset( $_SERVER['HTTPS'] ) ) {
        if ( 'on' == strtolower( $_SERVER['HTTPS'] ) ) {
            return true;
        }
        if ( '1' == $_SERVER['HTTPS'] ) {
            return true;
        }
    } elseif ( isset($_SERVER['SERVER_PORT'] ) && ( '443' == $_SERVER['SERVER_PORT'] ) ) {
        return true;
    }
    return false;
}
```

---

Posted Sep 12, 2011.

https://www.darklaunch.com/2011/09/12/php-determine-if-using-ssl-https-or-http.html

---

4 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Apr 4, 2012
            <div>
                <p>thanks for posting this, it helped me big time today</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 29, 2012
            <div>
                <p>Link to original source file</p><p><a href="http://core.svn.wordpress.org/trunk/wp-includes/functions.php">http://core.svn.wordpress.org/trunk/wp-includes/functions.php</a></p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 18, 2013
            <div>
                <p>wtf it should be if (  $_SERVER['HTTPS'] = '1' etc..</p><p></p><p>var you are checking = the value you want to check it against</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 10, 2016
            <div>
                <p>Link to latest <a href="https://github.com/WordPress/WordPress/blob/HEAD/wp-includes/load.php">https://github.com/WordPress/WordPress/blob/HEAD/wp-includes/load.php</a></p>
            </div>
        </div>
    </li>
</ol>
