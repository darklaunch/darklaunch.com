# Django Show the Raw SQL Query Running

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

---

Posted Oct 23, 2011.

https://www.darklaunch.com/2011/10/23/django-show-the-raw-sql-query-running.html

---

4 comments

<ol><li><div>

anonymous &ndash; Dec 12, 2013<div>

see also debugsqlshell in django-debug-toolbar.

https://github.com/django-debug-toolbar/django-debug-toolbar/blob/master/debug_toolbar/management/commands/debugsqlshell.py

</div></div></li><li><div>

anonymous &ndash; Dec 12, 2013<div>

also:

```
import logging
l = logging.getLogger('django.db.backends')
l.setLevel(logging.DEBUG)
l.addHandler(logging.StreamHandler())
```

https://stackoverflow.com/questions/2314920/django-show-log-orm-sql-calls-from-python-shell

</div></div></li><li><div>

anonymous &ndash; Dec 18, 2013<div>

Also:

```
>>> queryset = MyModel.objects.all()
>>> print queryset.query
SELECT "myapp_mymodel"."id", ... FROM "myapp_mymodel"
```

</div></div></li><li><div>

anonymous &ndash; Jan 13, 2014<div>

```
from django.db import connection
print connection.queries
```

works for the `update()` command as well.

</div></div></li></ol>