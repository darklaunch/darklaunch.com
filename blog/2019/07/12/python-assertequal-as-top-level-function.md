A regular assert statement could be more verbose:
```python
first = 'a'
second = 'aa'
assert first == second
```
```bash
$ python script.py
Traceback (most recent call last):
  File "script.py", line 3, in <module>
    assert first == second
AssertionError
```

Here is a top-level function to test an assertion condition in more detail:
```python
import unittest


def assert_equal(first, second):
    class MyTestCase(unittest.TestCase):
        def test(self):
            self.assertEqual(first, second)

    suite = unittest.TestLoader().loadTestsFromTestCase(MyTestCase)
    unittest.TextTestRunner().run(suite)


first = 'a'
second = 'aa'
assert_equal(first, second)
```
```bash
$ python script.py
F
======================================================================
FAIL: test (__main__.MyTestCase)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "script.py", line 7, in test
    self.assertEqual(first, second)
AssertionError: 'a' != 'aa'

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (failures=1)
```

Basic assert in:
```python
first = 'z'
second = ['a', 'b', 'c']
assert first in second
```
```bash
$ python script.py
Traceback (most recent call last):
  File "script.py", line 3, in <module>
    assert first in second
AssertionError
```

Improved assert in:
```python
import unittest


def assert_in(first, second):
    class MyTestCase(unittest.TestCase):
        def test(self):
            self.assertIn(first, second)

    suite = unittest.TestLoader().loadTestsFromTestCase(MyTestCase)
    unittest.TextTestRunner().run(suite)


first = 'z'
second = ['a', 'b', 'c']
assert_in(first, second)
```
```bash
$ python script.py
F
======================================================================
FAIL: test (__main__.MyTestCase)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "script.py", line 7, in test
    self.assertIn(first, second)
AssertionError: 'z' not found in ['a', 'b', 'c']

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (failures=1)
```