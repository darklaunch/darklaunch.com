<img alt="" src="/img/uploads/2011-11/django-change-admin-user-password.png" />

Change a user's password from the command line, use the changepassword command. It will prompt you to change the password for the specified user.
```py
./manage.py changepassword admin
```
```py
django-admin.py changepassword admin
```

You can also change a password programmatically:</a>
```py
from django.contrib.auth.models import User
admin = User.objects.get(username='admin')
admin.set_password('mynewpassword')
admin.save()
```