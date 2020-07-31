```python
import datetime
import time

import mock

# Ensure constant time.
with mock.patch.object(datetime, 'datetime', mock.Mock(wraps=datetime.datetime)) as patched:
    patched.now.return_value = datetime.datetime(2020, 1, 1)

    print(datetime.datetime.now())
    time.sleep(3)
    print(datetime.datetime.now())
```

```bash
$ python run_test.py
2020-01-01 00:00:00
2020-01-01 00:00:00
```

---


Posted Mar 22, 2020.
https://www.darklaunch.com/2020/03/22/run-python-test-with-constant-time-using-mock.html