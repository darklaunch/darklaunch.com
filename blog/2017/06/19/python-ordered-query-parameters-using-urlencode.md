Order query parameters using urlencode.

```python
from collections import OrderedDict

from django.utils.http import urlencode

params = {
    'a': 1,
    'b': 2,
    'c': 3,
}
print(urlencode(OrderedDict(params))) # a=1&c=3&b=2 (incorrect)

params = [
  ('a', 1),
  ('b', 2),
  ('c', 3),
]
print(urlencode(OrderedDict(params))) # a=1&b=2&c=3 (correct)
```