To enable Basic Authentication using Django and mod_wsgi, do the following:

Add WSGIPassAuthorization to apache configuration file (
/etc/apache2/sites-available/mysite.com )

Configure this WSGIPassAuthorization On so that mod_wsgi will pass the HTTP Authentication headers to your Django application so your app will be able to
authenticate the requests.

```
<VirtualHost *:80>
    WSGIPassAuthorization On
    WSGIScriptAlias / /home/www/mysite.com/wsgi.py
</VirtualHost>
```

Restart apache and the now the HTTP_AUTHORIZATION environment variable will be available in the django request.