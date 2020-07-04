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