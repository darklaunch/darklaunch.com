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

<ol>
    <li>
        <div>
            anonymous &ndash; Dec 12, 2013
            <div>
                <p>see also debugsqlshell in django-debug-toolbar.</p><p></p><p>github.com/django-debug-toolbar/django-debug-toolbar/blob/master/debug_toolbar/management/commands/debugsqlshell.py</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 12, 2013
            <div>
                <p>also:</p><p></p><p>import logging</p><p>l = logging.getLogger('django.db.backends')</p><p>l.setLevel(logging.DEBUG)</p><p>l.addHandler(logging.StreamHandler())</p><p></p><p>stackoverflow.com/questions/2314920/django-show-log-orm-sql-calls-from-python-shell</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 18, 2013
            <div>
                <p>Also:</p><p></p><p>&gt;&gt;&gt; queryset = MyModel.objects.all()</p><p>&gt;&gt;&gt; print queryset.query</p><p>SELECT "myapp_mymodel"."id", ... FROM "myapp_mymodel"</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jan 13, 2014
            <div>
                <p>from django.db import connection</p><p>print connection.queries</p><p></p><p>works for the update() command as well.</p>
            </div>
        </div>
    </li>
</ol>
