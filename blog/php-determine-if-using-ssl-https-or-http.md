To determine if SSL is used, the is_ssl() function will return True
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