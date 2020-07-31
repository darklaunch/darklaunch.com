To list the functions available for the imported module, use `inspect.getmembers()`:

```
$ python
```
```python
>>> import inspect
>>> import pprint
>>> import django
>>> pprint.pprint(inspect.getmembers(django))
[('VERSION', (1, 8, 4, 'final', 0)),
 ('__builtins__', { '...' }
 ('__doc__', None),
 ('__file__', '/Library/Python/2.7/site-packages/django/__init__.pyc'),
 ('__name__', 'django'),
 ('__package__', 'django'),
 ('__path__', ['/Library/Python/2.7/site-packages/django']),
 ('__version__', '1.8.3'),
 ('get_version', <function get_version at 0x10bc52320>),
 ('setup', <function setup at 0x10bc57500>),
 ('utils',
  <module 'django.utils' from '/Library/Python/2.7/site-packages/django/utils/__init__.pyc'>)]
>>>
```

Alternatively, use `dir()`:
```python
import pprint
import django
>>> pprint.pprint(dir(django))
['VERSION',
 '__builtins__',
 '__doc__',
 '__file__',
 '__name__',
 '__package__',
 '__path__',
 '__version__',
 'get_version',
 'setup',
 'utils']
```

---

Posted Aug 26, 2015.

https://www.darklaunch.com/2015/08/26/python-list-functions-for-imported-module.html