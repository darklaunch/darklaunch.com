Sort an unordered dictionary in python using sorted.

```python
>>> from collections import OrderedDict
>>> d = {'a': 1, 'c': 3, 'b': 2}
>>> OrderedDict(d)
OrderedDict([('a', 1), ('c', 3), ('b', 2)])
>>> OrderedDict(sorted(d.items()))
OrderedDict([('a', 1), ('b', 2), ('c', 3)])
```

Using strings for keys may cause unexpected ordering.

```python
>>> from collections import OrderedDict
>>> d = {str(x): chr(x + 96) for x in range(1, 15)}
>>> d = OrderedDict(sorted(d.items()))
>>> for k, v in d.iteritems():
...     print(k, v)
...
('1', 'a')
('10', 'j')
('11', 'k')
('12', 'l')
('13', 'm')
('14', 'n')
('2', 'b')
('3', 'c')
('4', 'd')
('5', 'e')
('6', 'f')
('7', 'g')
('8', 'h')
('9', 'i')
```

Use the "key" parameter when calling sorted() to sort a dictionary into numerical ascending order.

```python
>>> from collections import OrderedDict
>>> d = {str(x): chr(x + 96) for x in range(1, 15)}
>>> d = OrderedDict(sorted(d.items(), key=lambda k: int(k[0])))
>>> for k, v in d.iteritems():
...     print(k, v)
...
('1', 'a')
('2', 'b')
('3', 'c')
('4', 'd')
('5', 'e')
('6', 'f')
('7', 'g')
('8', 'h')
('9', 'i')
('10', 'j')
('11', 'k')
('12', 'l')
('13', 'm')
('14', 'n')
```

---


Posted Apr 8, 2017.
https://www.darklaunch.com/2017/04/08/python-sort-an-ordereddict.html