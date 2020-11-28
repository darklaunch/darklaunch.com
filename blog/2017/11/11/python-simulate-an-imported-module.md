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

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Aug 2, 2018
            <div>
As used in nltk:

# Override missing methods on environments where it cannot be used like GAE.
import subprocess
if not hasattr(subprocess, 'PIPE'):
&nbsp;&nbsp;&nbsp;&nbsp;def _fake_PIPE(*args, **kwargs):
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;raise NotImplementedError('subprocess.PIPE is not supported.')
&nbsp;&nbsp;&nbsp;&nbsp;subprocess.PIPE = _fake_PIPE
if not hasattr(subprocess, 'Popen'):
&nbsp;&nbsp;&nbsp;&nbsp;def _fake_Popen(*args, **kwargs):
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;raise NotImplementedError('subprocess.Popen is not supported.')
&nbsp;&nbsp;&nbsp;&nbsp;subprocess.Popen = _fake_Popen

<a href="https://github.com/nltk/nltk/blob/develop/nltk/__init__.py">https://github.com/nltk/nltk/blob/develop/nltk/__init__.py</a>
            </div>
        </div>
    </li>
</ol>
