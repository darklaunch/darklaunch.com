# Apache hide .git and .svn folder contents using .htaccess file

To hide .git and .svn folder contents you need create a .htaccess file with the following:

```
php_flag display_errors on
RedirectMatch 404 /\\.git(/.*|$)
RedirectMatch 404 /\\.svn(/.*|$)
```

Another useful setting is to turn on error_reporting:

```
php_flag display_errors on
php_value error_reporting 7
```

normal errors - bit value 1
normal warnings - bit value 2
parser errors - bit value 4
1 + 2 + 4 = 7

Or simply use a whitelist approach:

```
# 403 Forbidden for all directory indexes
Options -Indexes

# Add all files to the list of files to hide when listing a directory
IndexIgnore *

# Use whitelist approach.
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_URI} !\.css
RewriteCond %{REQUEST_URI} !\.js
RewriteCond %{REQUEST_URI} !\.png
RewriteCond %{REQUEST_URI} !.*\/$
RewriteRule .* /404 [L,R=302]
```

---

Posted Jun 24, 2011.

https://www.darklaunch.com/2011/06/24/apache-hide-git-and-svn-folder-contents-using-htaccess-file.html