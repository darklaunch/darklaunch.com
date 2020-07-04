<img alt="" src="/img/uploads/2011-10/how-can-i-see-the-raw-sql-queries-django-is-running.png" />

To see the raw SQL queries Django is running, do the following:

In your settings file (typically settings.py), ensure DEBUG is set to True
```py
DEBUG = True
```
Then import connection from django.db and print connection.queries
```py
import pprint

from django.db import connection


pprint.pprint(connection.queries)
```
If your queries are slowing you down, look into using select_related() to follow foreign keys