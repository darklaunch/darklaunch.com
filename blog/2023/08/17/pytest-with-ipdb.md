# pytest with ipdb

Using `ipdb` with `pytest` requires the `-s` option.

```python
# thing_test.py

import unittest

class ThingTest(unittest.TestCase):
    def test_the_thing(self):
        """
        Tests the thing.
        """
        import ipdb
        ipdb.set_trace()

        self.assertTrue(False)
```

Breakpoint is not caught when running `pytest`:

```shell
$ pipenv run pytest
```

```
=================== short test summary info ===================
FAILED thing_test.py::ThingTest::test_the_thing - OSError: pytest: reading from stdin while output is captur...
====================== 1 failed in 0.38s ======================
```

The breakpoint is caught when running `pytest` with the `-s` option:

```shell
$ pipenv run pytest -s
```

```
===================== test session starts =====================
platform darwin -- Python 3.10.12, pytest-7.4.0, pluggy-1.2.0
rootdir: /tmp/example
collected 1 item                                              

thing_test.py > /tmp/example/thing_test.py(12)test_the_thing()
     10         ipdb.set_trace()
     11 
---> 12         self.assertTrue(False)

ipdb> 
```

---

Posted Aug 17, 2023.

https://www.darklaunch.com/2023/08/17/pytest-with-ipdb.html