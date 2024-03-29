# Enable HTTP Basic Authentication / Authorization with Django & mod_wsgi

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

---

Posted Jul 17, 2012.

https://www.darklaunch.com/2012/07/17/enable-http-basic-authentication-authorization-with-django-mod-wsgi.html