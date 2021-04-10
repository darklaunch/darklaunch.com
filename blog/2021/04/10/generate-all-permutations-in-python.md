List all possible permutations of lists using a python script.

```python
import itertools
import pprint

group_a = [
    'A',
    'B',
    'C',
]

group_b = [
    '1',
    '2',
    '3',
]

group_c = [
    'Z',
]

iterables = [
    group_a,
    group_b,
    group_c,
]

result = itertools.product(*iterables)
pprint.pprint(list(result))
```

```
[('A', '1', 'Z'),
 ('A', '2', 'Z'),
 ('A', '3', 'Z'),
 ('B', '1', 'Z'),
 ('B', '2', 'Z'),
 ('B', '3', 'Z'),
 ('C', '1', 'Z'),
 ('C', '2', 'Z'),
 ('C', '3', 'Z')]
```

kw: Cartesian product

---

Posted Apr 10, 2021.

https://www.darklaunch.com/2021/04/10/generate-all-permutations-in-python.html