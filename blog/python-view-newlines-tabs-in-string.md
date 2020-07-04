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