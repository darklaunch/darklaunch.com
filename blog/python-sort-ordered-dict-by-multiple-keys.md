Sort an ordered dictionary by more than one key:

```python
import collections

collections.OrderedDict(sorted(my_dict.items(), key=lambda item: (item[1], item[0]), reverse=True))
```