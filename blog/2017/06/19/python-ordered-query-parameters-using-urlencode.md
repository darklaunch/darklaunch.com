# Python ordered query parameters using urlencode

Order query parameters using `urlencode`.

```python
from collections import OrderedDict

from django.utils.http import urlencode

params = {
    'a': 1,
    'b': 2,
    'c': 3,
}
print(urlencode(OrderedDict(params))) # Incorrect.
```

Unordered query parameters:

```
a=1&c=3&b=2
```

Ordered query parameters:

```python
params = [
  ('a', 1),
  ('b', 2),
  ('c', 3),
]
print(urlencode(OrderedDict(params))) # Correct.
```

```
a=1&b=2&c=3
```

---

Posted Jun 19, 2017.

https://www.darklaunch.com/2017/06/19/python-ordered-query-parameters-using-urlencode.html