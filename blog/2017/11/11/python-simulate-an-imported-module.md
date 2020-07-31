Fake a module import by adding a fake module to sys.modules.

```python
import sys

class FakeModule(object):
    PIPE = None
    Popen = None
sys.modules['subprocess'] = FakeModule
```

Now the following python import from nltk will not fail on App Engine:

```python
from subprocess import PIPE, Popen
```

Fixes: "ImportError: cannot import name PIPE"

---


Posted Nov 11, 2017.
https://www.darklaunch.com/2017/11/11/python-simulate-an-imported-module.html