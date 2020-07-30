View a string's newlines and tabs in Python.

```python
>>> import pprint
>>> s = 'a\n\tb\nc'
>>> print(s)
a
	b
c
>>> print(pprint.pformat(s))
'a\n\tb\nc'
```

---

Posted Sep 6, 2017.
https://www.darklaunch.com/2017/09/06/python-view-newlines-tabs-in-string