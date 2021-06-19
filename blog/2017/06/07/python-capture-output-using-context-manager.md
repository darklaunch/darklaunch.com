# Python capture output using context manager

Capture stdout output in python using a context manager.

```python
import cStringIO
import sys

class CaptureOutput(list):
    def __enter__(self):
        self._stdout = sys.stdout
        sys.stdout = self._stringio = cStringIO.StringIO()
        return self

    def __exit__(self, *args):
        self.extend(self._stringio.getvalue().splitlines())
        del self._stringio
        sys.stdout = self._stdout
```

Usage:

```python
def count_to_3():
    for i in range(1, 4):
        print(i)

with CaptureOutput() as lines:
    count_to_3()

print('done counting')

for line in lines:
    print('line: %s' % line)
```

Output:

```
done counting
line: 1
line: 2
line: 3
```

Capture stdout output in php.

```php
<?php
function count_to_3() {
    for ($i = 1; $i <= 3; $i++) {
        echo $i . "\n";
    }
}

ob_start();
count_to_3();
$lines = explode("\n", rtrim(ob_get_contents()));
ob_end_clean();

echo 'done counting' . "\n";

foreach ($lines as $line) {
    echo 'line: ' . $line . "\n";
}
```

Output:

```
done counting
line: 1
line: 2
line: 3
```

https://stackoverflow.com/questions/16571150/

---

Posted Jun 7, 2017.

https://www.darklaunch.com/2017/06/07/python-capture-output-using-context-manager.html