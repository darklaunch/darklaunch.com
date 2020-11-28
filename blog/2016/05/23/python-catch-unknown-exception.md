Unable to catch the python exception?

First, use a catch all exception and see what exception it throws. The class and module will hint at where you may import the exception to catch from.

```python
import logging

try:
    thing_that_raises_exception()
except Exception as error:
    logging.error(
        'unhandled exception (class=%s; module=%s)',
        error.__class__ if hasattr(error, '__class__') else 'unknown',
        error.__module__ if hasattr(error, '__module__') else 'unknown')
```

keywords: Django, MySQL, except ProgrammingError, django.db.utils.ProgrammingError

---

Posted May 23, 2016.

https://www.darklaunch.com/2016/05/23/python-catch-unknown-exception.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Jan 26, 2017
            <div>
Worked. Thanks!
            </div>
        </div>
    </li>
</ol>
