# Python sort ordered dict by multiple keys

Sort an ordered dictionary by more than one key:

```python
import collections

collections.OrderedDict(sorted(my_dict.items(), key=lambda item: (item[1], item[0]), reverse=True))
```

---

Posted Jan 24, 2020.

https://www.darklaunch.com/2020/01/24/python-sort-ordered-dict-by-multiple-keys.html