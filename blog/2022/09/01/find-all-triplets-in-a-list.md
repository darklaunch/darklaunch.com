# Find all triplets in a list

Find all triplets in a list of numbers using python:

```python
import itertools
import pprint

input_list = [-3, 1, 2, 0, 5]

result = itertools.combinations(input_list, 3)
triplets = list(result)
pprint.pprint(triplets)
```

```
[(-3, 1, 2),
 (-3, 1, 0),
 (-3, 1, 5),
 (-3, 2, 0),
 (-3, 2, 5),
 (-3, 0, 5),
 (1, 2, 0),
 (1, 2, 5),
 (1, 0, 5),
 (2, 0, 5)]
```

kw: combination tuples

---

Posted Sep 1, 2022.

https://www.darklaunch.com/2022/09/01/find-all-triplets-in-a-list.html