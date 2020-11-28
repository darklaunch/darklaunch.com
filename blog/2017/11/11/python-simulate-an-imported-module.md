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
                <p>As used in nltk:</p><p></p><p></p><p># Override missing methods on environments where it cannot be used like GAE.</p><p>import subprocess</p><p>if not hasattr(subprocess, 'PIPE'):</p><p>&nbsp;&nbsp;&nbsp;&nbsp;def _fake_PIPE(*args, **kwargs):</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;raise NotImplementedError('subprocess.PIPE is not supported.')</p><p>&nbsp;&nbsp;&nbsp;&nbsp;subprocess.PIPE = _fake_PIPE</p><p>if not hasattr(subprocess, 'Popen'):</p><p>&nbsp;&nbsp;&nbsp;&nbsp;def _fake_Popen(*args, **kwargs):</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;raise NotImplementedError('subprocess.Popen is not supported.')</p><p>&nbsp;&nbsp;&nbsp;&nbsp;subprocess.Popen = _fake_Popen</p><p></p><p></p><p><a href="https://github.com/nltk/nltk/blob/develop/nltk/__init__.py">https://github.com/nltk/nltk/blob/develop/nltk/__init__.py</a></p>
            </div>
        </div>
    </li>
</ol>
