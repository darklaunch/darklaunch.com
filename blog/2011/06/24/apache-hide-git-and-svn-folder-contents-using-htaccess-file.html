<p>To hide .git and .svn folder contents you need create a .htaccess file with the following:</p>

<code>
php_flag display_errors on
RedirectMatch 404 /\\.git(/.*|$)
RedirectMatch 404 /\\.svn(/.*|$)
</code>

<p>Another useful setting is to turn on error_reporting:</p>

<code>
php_flag display_errors on
php_value error_reporting 7
</code>

<p>normal errors - bit value 1</p>
<p>normal warnings - bit value 2</p>
<p>parser errors - bit value 4</p>
<p>1 + 2 + 4 = 7</p>

<p>Or simply use a whitelist approach:</p>

<code>
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
</code>