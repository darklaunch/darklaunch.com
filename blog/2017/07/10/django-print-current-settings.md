<p>Display the current Django project settings.</p>

<code name="python">
>>> from django.conf import settings
>>> settings
<LazySettings "myproject.settings">
>>> print(settings)
<Settings "myproject.settings">
>>> import pprint
>>> pprint.pprint({name: getattr(settings, name) for name in dir(settings)})
{'ABSOLUTE_URL_OVERRIDES': {},
 'ADMINS': [],
 'ALLOWED_HOSTS': [],
 'APPEND_SLASH': True,
 'AUTHENTICATION_BACKENDS': [u'django.contrib.auth.backends.ModelBackend'],
 'AUTH_PASSWORD_VALIDATORS': [{'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator'},
                              {'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator'},
                              {'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator'},
                              {'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator'}],
 'AUTH_USER_MODEL': u'auth.User',
[...]
 'USE_TZ': True,
 'USE_X_FORWARDED_HOST': False,
 'USE_X_FORWARDED_PORT': False,
 'WSGI_APPLICATION': 'myproject.wsgi.application',
 'X_FRAME_OPTIONS': u'SAMEORIGIN',
 'YEAR_MONTH_FORMAT': u'F Y'}
</code>