Parse a page range or number range in python. This is similar to the Print page in Microsoft Word or Office that allows you to select the page or page range to print. Use the following code to parse such a string.

```python
from itertools import groupby
from operator import itemgetter

def group_range(data):
    """
    Return a list of tuple ranges.
    e.g. group_range([1, 3, 5, 6, 7, 8, 9, 10, 11, 12]) returns [(1, 1), (3, 3), (5, 12)]
    """
    ranges = []
    for k, g in groupby(enumerate(data), lambda (i,x):i-x):
        group = map(itemgetter(1), g)
        ranges.append((group[0], group[-1]))
    return ranges

def parse_range(astr):
    """
    Return a range list given a string.
    e.g. parse_range('1,3,5-12') returns [1, 3, 5, 6, 7, 8, 9, 10, 11, 12]
    """
    result = set()
    for part in astr.split(','):
        x = part.split('-')
        result.update(range(int(x[0]), int(x[-1]) + 1))
    return sorted(result)
```

<img alt="" src="/img/uploads/2012-11/print-page-range.png" />

---


Posted Nov 5, 2012.
https://www.darklaunch.com/2012/11/05/python-parse-range-and-parse-group-range.html