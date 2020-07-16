Access the first element in a python dict in a non-destructive fashion.
```python
from collections import OrderedDict

d = OrderedDict([
    ('a', 1),
    ('b', 2),
    ('c', 3),
])
key = dict.iterkeys().next()
print(key) # "a"
```
Note: Be careful with unordered dictionaries.
```python
dict = {'a': 1, 'b': 2, 'c': 3}
key = dict.iterkeys().next()
print(key) # Not always "a"
```