# Fix "NameError: name 'OrderedDict' is not defined"

To fix the `NameError OrderedDict is not defined` error, do the following:

```python
import collections

try:
    from collections import OrderedDict
except ImportError:
    OrderedDict = dict
```

The `OrderedDict` is available in more recent versions of python. Use this as a fallback for OrderedDict support.

```bash
$ python test.py
Traceback (most recent call last):
  File "test.py", line 8, in <module>
    foo = OrderedDict()
NameError: name 'OrderedDict' is not defined
```

---

Posted Sep 17, 2012.

https://www.darklaunch.com/2012/09/17/fix-nameerror-name-ordereddict-is-not-defined.html